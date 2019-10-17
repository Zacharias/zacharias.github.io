---
layout: post
title: "Some bulleted notes on devopsdays."
date:   2018-09-21 8:57:40
author: Zacharias
summary: "Some bulleted notes on  devopsdays."
---

I made some notes for the couple of keynotes I attended. Afterwards, I went through and spruced them up lightly.

### Gene Kim

Mr. Kim went through many of the topics that his book Accelerate covered. Accelerate can be considered a "State of Devops" report that's been to the gym and really bulked up on some statistics and more organizational and cultural material.

- kubernetes sidecars for crosscuts
- aspect oriented programming
- importing expertise
- locality in our code
- composability
- bad - integrated test environment
- authority should belong to teams

Stanley McChrystal's Team of Teams got a shoutout.

-  [The Operators by the late Michael Hastings](https://books.google.com/books/about/The_Operators.html?id=xD8dDgAAQBAJ&printsec=frontcover&source=kp_read_button#v=onepage&q&f=false) may be one of the best GWOT books every published.

Practices that enable "focus, flow, and joy"

- Immutablity is a thing that is nice about functional programming.
- Infrastructure immutability
- Git version control history is also immutable, we like that.
- What else is stateful? bash, yaml, updating dependencies

Platforms

- The job of platforms is to enable developers to solve business problems.
- Platforms enable developers to self-service with immediacy and fast feedback

Measuring success

- What is your lead time for changes?
- Usually read as "how long does committed code take to get to where the customer can realize the value"
- How long does it take to get a developer to realize a mistake in his code?
- Trunk based development
- improvement of daily work is more important the the daily work itself.
- learning organizations internalize that
- create as much feedback as possible 

daily workarounds are disruptive

- technical debt is insidious
- a book says 20% of cycles for tech debt reduction
- enabling greaeatness
- ideally, 3-5% of developers dedicated to impriving developer productity.
- google puts the BEST devs off of features and into improving dev productivity
- playing the "forever" game


Organizational and Cultural Features

- psychological safety is predictive of performance
- strongest signal for performance in the devops survey study
- google made the same findings in "project aristotle, oxygen, re:work"
great practices enabled


customer focus
fucntion silo managers priorotize silo goals over business goals
if it doesn't create competetive advantage we should get it out of our business and outsource it



Product value streams: decisions are made in the stream
    there is a cross cutting role that also is product valye stream thing jawn

intentional verus perfect
treat your delivery pipeline as a product
but 
you can't make it a silon on it's own
internal services shared frameworks should be their own product value stream
but make em wiki like

people dont resist change they resist loss

1. loss maps
2. eigineers worried about loss of culture being manged by non engineers
3. not being insulated

product is worried about being consumed
career path confusion

squads and crews, crews? is that what you call them here?

detailed career ladders for each kind of role in the value stream
who leads? 
should it be a product or engineering manager?
you need to overcompensate with the role that you dont have
communicate with executives

finance, sales executives
visiblity for all products

finance cares about extremely specific metrics
traditional

report on tech debt risk feature and bug kinds of work/stories all the way up to the board

lots of flow reports: type, efficiency, velocity

change management is hard
which is hard

balance teams' empowerment versus imposition
somehow empowering a team is off-putting to the team somehow


larry mac

developers need crediblity, make your own code
devops is the team being in charge of how the product works in production
developers need to own the problem. you can invest time and energy to help yourselves out.
security is typically designed around robust gatingthere
chaos engineering 
devops is about culture.
there is a devsecops manifesto
build in versus bolt on
implement secure features versus security features
few key practices deeply instead of super wide 
they publish out reusable concourse resources (i should go over them) - whitesource is on there, too.
