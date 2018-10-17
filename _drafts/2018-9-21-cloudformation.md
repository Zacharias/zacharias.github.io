---
layout: post
title:  "Create a secure S3 website with Terraform"
date:   2018-09-21 8:57:40
author: Zacharias
summary: "Keeping a lid on a S3 bucket doesn't have to be a manual process"
---

<div class="row">
    <div class="col-md-12">
        <p>Proving that your new or changed cloud assets is usually pretty straightforward: someone can eyeball (let's say in the AWS console), in order to see that the S3 bucket is configured for proper access. This kind of acceptance testing is in what I have to imagine is most team's process, but how do you prove it works that way _forever_ from the prying eyes on the rest of the internet?</p>
    </div>
    <div class="col-md-9">
        <h3> Let's make a S3 environment!</h3>
        <p>I'm drafting off of some good Terraform code i found on the internet for a basic setup for a S3 Bucket, CloudFormation distribution, and </p>


    </div>

    <div class="col-md-3">
    <h4 style="padding-bottom:.5em">Securing S3 is harder than it looks</h4>

    <p class="lead"><a href="https://www.securityweek.com/amazon-s3-bucket-exposed-godaddy-server-information)">Amazon S3 Bucket Exposed GoDaddy Server Information</a></p>

    <blockquote class="blockquote">The bucket in question was created by an AWS salesperson to store prospective AWS pricing scenarios while working with a customer. No GoDaddy customer information was in the bucket that was exposed. While Amazon S3 is secure by default and bucket access is locked down to just the account owner and root administrator under default configurations, the salesperson did not follow AWS best practices with this particular bucket,” Amazon said, responding to a SecurityWeek inquiry.</blockquote>

    <p class="lead"><a href="https://www.securityweek.com/robocalling-firm-exposes-us-voter-records">Robocalling Firm Exposes U.S. Voter Records</a></p>
    
    <blockquote class="blockquote">More importantly, the Amazon S3 bucket contained a large amount of voter data (in the form of *.csv, *.xls files): full name, suffix, prefix; phone numbers (cell and landlines); address with house, street, city, state, zip, precinct; age and birth year; and gender.</blockquote>

    <p class="lead"><a href="https://www.securityweek.com/data-aggregator-localblox-exposes-48-million-records">Data Aggregator LocalBlox Exposes 48 Million Records</a></p>
    <blockquote class="blockquote">The file was found to contain 48 million records, each in json format and separated by new lines. The security researchers also discovered that the real estate site Zillow was used in the data gathering process, “with information being somehow blended from the service's listings into the larger data pool.”</blockquote>
    </div>
</div>


