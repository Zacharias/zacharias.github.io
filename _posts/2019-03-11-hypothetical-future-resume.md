---
layout: post
title:  "Desired State Configuration for Your Career"
date:   2019-3-11 13:17:40
author: Zacharias
---

<style>
	h2,h3 { margin-bottom: .5em; }
</style>

<div class="container">

<div class="row">
<div class="col-12">
<p class="lead" style="padding-top:1em;">A short conversation with some of my peers lead me to believe that it's rather atypical to do explicit career planning activities once someone lands a job in the role they're after. Even though I work with smart and handsome people and professional lives can very and change very quickly, I propose using desired state configuration to inform decision making between here and the next "there".</p>
	</div>
</div>

<div class="row">
<div class="col-12">

<h3>Impertative vs. Declarative Approaches to Configuration Management in a nutshell</h3>

<p>I'm going to start by comparing Chef and Terraform. Both of these tools can be used to create and manage servers and the associated infrastructure in a/the cloud. Those hipper to the relative scope of these tools like understand they're not used exactly for the same thing, or in place of each other. That's alright here, since I'm really interested in talking about the modalities of how they get the job done.</p>

<p>Let's take on the problem of making sure that a particular database table for products exist. Maybe in some copies of the database, there isn't a description for the product. This can mess up consumers that expect products to always have this information (even if it's empty). The approach that someone using Chef could take would boil down to this:</p>

<ul>
    <li>Check if the target environment has a database table called `products`</li>
    <li>If it does not exist,</li>
    <li>Make a new table called `products` with columns `productId` and `ProductDescription`</li>
    <li>If it does exist,</li>
    <li>Try to create columns on the table called `productId` and `ProductDescription`</li>
    <li>If that worked,</li>
    <li>Tell everyone "things worked great"</li>
    <li>Otherwise,</li>
    <li>Tell the operator that "things didn't go great"</li>
</ul>

<p>This way of working is can be called the _imperative_ approach to configuration management. A lot of applications take this approach: react appropiately to things either existing or not existing, or behave differently for a certain kind of requestor or certain kind of request. This kind of programming is very conductive to taking an iterative approach, doing more and more things against a wider and wider array of situations.</p>

<p>Where things get a little more fraught, of course, is that situations and actions end up being *multiplicativly* complicated over time. This already rather-long script can end up accounting for lots of not-exactly-germane situations or, heaven forbid, someone borrows this to handle something that really isn't this script's problem in the first place.</p>

<p>In comparison, other tools are declarative. Declarative tools ask us to describe how things would be awesome to us, and let's the computer leg it through the not awesome world the stuff exists in to arrive at the shining future. Trying to solve the same problem in a declarative tool like Terraform would look like this:</p>

<ul>
    <li>I want a products database table</li>
    <li>This products database table has a column called `productId`</li>
    <li>This products database table has a column called `productDescription`</li>
</ul>

<p>When you go to run this script against the same kind of environment that the Chef script was designed for, Terraform does all sorts of state calculations: figuring out how things were/are, if they've been fiddled with since the last time it ran. It then makes an execution plan that lists the changes it needs to make to get the database table with the right columns.</p>

<p>We get out of the business of caring exactly what is there already: if there's a halfway-okay setup, we can add in the new stuff and get it there. If there's something already there that is so bad and out of whack we can't change it, we're given the option of blowing up the one that's already there and make a new guy from scratch. If we have scratch, make up the right thing. If we have the right thing, we don't have to do anything. We get out of the business of caring about all the sometimes-arcane or fiddly steps of change and get what we want: the desired state.</p>

<h3>How this applies to career planning</h3>

<p>When we think we're about to get fired, or get to feeling wanderlust, or our wife gets accepted into astronaut training and you need to move to Houston, we think about getting around to updating that oft-neglected document: our resumes. The working definition of resume I'm going to use here looks like this:</p>

<blockquote>A resume is a document that describes an individual's skills, responsibilities, and accomplishments with businesses _at the time of writing_.</blockquote>

<p>The resume is a state: where we've been and are presently in time/space, professionally-speaking. I think resumes' detail-light, always optimistic tone make them prefect planning documents. We can take a couple of approaches to get there, just like we can in cloud configuration management.</p>

<p>You could take the imperative approach: based on your current stuff, find a next step in the direction of some sort of personal mission or vision statement. This kind of methodical approach of skills-experience-accomplishment gathering can work over the long term, if you have the dicipline to burn to make yourself think about growing your career pretty frequently. If that's you, I applaud your thoughtful approach in making your own hopes an dreams come true.</p>

<p class="lead">Since I'm lazy, here's what I do: I write a resume against desired state. Picking a time horizon, 2-3 years seems good, what awesome stuff will be on my resume that isn't there? What neat stuff will be be accomplished? What neat stuff will I have learned about? Will that title change happen in this company or the next?</p>

<p>By creating the desired state you'd like to be in, you now get the yeoman's work of making it a reality. This is where everything comes together: when you're looking at doing day to day decision making, you now have the next set of horizons sketched out. And if you're in a creative field or have a lot of automony of projects overall, you now know the kinds of work you need to be taking on to make that fabrication, that McGuffin, a real document. If you have people in your life who you trust to help you professionally, you have a clear roadmap to describe your near-and-medium-going-on-long term goals.</p>

</div>
</div>