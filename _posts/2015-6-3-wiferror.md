---
layout: post
title:  "Solved - Error WIF10201 with ADFS 3.0 and MVC 5"
date:   2015-6-3 16:17:40
author: Zacharias
---

<div class='alert alert-warning'>
	*This article may contain wsFederation-specific information*<br>
	Ensure that your STS implementation is of the "passive" variety, or adjust your fix accordingly.
</div>

### A difficult-to-search-for WIF error

I ran across this error using a STS in an ASP.Identity (a passive federation) scenario:

`WIF10201: No valid key mapping found for securityToken: System.IdentityModel.Tokens.X509SecurityToken and issurer http://*/adfs/ls/`

If you are having this problem with a worked-yesterday application, there's a good chance that the issuer is using a novel certificate, according to your identity configuration.

You can identify the expected certificate "thumbprint" (hash value) in the context of ASP.NET/MVC applications, this can be found in a `web.config`section in the following XML path: system.identityModel -> identityConfiguration -> issuerNameRegistry -> authority -> keys[1]. 

### The source of the error what you'd expect when crypto hashes disagree.

Since the token isn't matching up to your configuration's value, there isn't any token handling services to deal with tokens that are signed not in the way you'd expect. So, in the context of when I saw this error in the wild, the error is my MVC application[2] saying:

> I totally understand how to deal with `4EA792F77D11E00E181AC5A347ABC7354E957443` tokens, heck, it only takes me 6ms to do it! Nobody's told me what to do with a `231BAC6EEB5349E31A743B180A6B2309C70C162C` token!

The next time your ADFS as STS-backed application starts throwing errors exactly 15 days before your non-renewing self-signed token-signing certificate expires, you'll know why.

### Grace periods, self-signing, et al.

There is are two certificate organizational models that can be used with ADFS 2.0+ [argued for or against online](http://blog.kloud.com.au/2013/07/17/ad-fs-and-self-signed-token-signing-certificates-3/), either self-signing or using a CA's certificate. The defaults (if I recally correctly) is to self-sign the token-signing certificate, and expiration in one year.

The real lesson I took away from this episode is that security isn't a static thing that is "set it and forget it."

### So, if all of that stuff is true, here's the checklist to fix it.

* Find the current token thumbprint in the application's `web.config`file (under the path of system.identityModel -> identityConfiguration -> issuerNameRegistry -> authority -> keys, probably) under the `issuerNameRegistry` or `tokenhandler` sections.
* Find your STS metadata xml (typically in ADFS, this can be found at https://*/FederationMetadata/2007-06/FederationMetadata.xml.) and look for the similarly-formatted value. These don't match? 
* Check your ADFS token-signing primary certificate for expiration. It's 15 days from when when this error came up?
* Depending on your certificate strategy[3], update the primary and secondary token-signing certificates.
* You'll find that the thumbprint is probably the secondary certificate's thumbprint, meaning ADFS switched to the secondary based on [grace period rules](https://technet.microsoft.com/en-us/library/jj933264.aspx) 15 days before the actual expiration of your primary certificate.
* To mitigate this taking all day in the future, either [automate the certificate's thumbprint in your configuration](http://serverfault.com/a/670407) or set a timely reminder (perhaps 20 days out?) to make the change ahead of when ADFS does it for you.
* If you are like me, then write a blog post about it to try and save some poor sod the work of chasing this error down in the future.

<hr />

1. Officially, this specific `<issuerNameRegistry>` configuration has [been deprecated](https://msdn.microsoft.com/en-us/library/hh568637(v=vs.110).aspx) (check the information under the shaded *important* box), most examples of ADFS 2.0 and 3.0 configurations use this style. This style is the configuration that the "Organizational Accounts" option in Visual Studio 2013 generates for you. Current-er config can be found in VS2015 and [there is an example on MSDN](https://msdn.microsoft.com/en-us/library/hh568638(v=vs.110).aspx) as well.

2. As a percentage of effort, trying to find the computer to blame for federated login failures is half the fight.

3. Or your organizations'. You *do* have a strategy, right?
