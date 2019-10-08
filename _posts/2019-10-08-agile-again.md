---
layout: post
title:  "Why Developers Hate Agile: I guess I've been on some pretty good teams."
date:   2019-10-8 12:40:40
author: Zacharias
summary: Let's re-litigate agile a little, it's been a spell
---

In regards to [Why software developers (quite honestly) hate Agile](https://www.objectstyle.com/agile/why-developers-hate-agile)

Going over this, I think I see a common thread and would love to make a plea to the better angels of our nature against them. You don't see anything at all uncommon in these, let's call them ham-handed at best, implementations of agile and/or scrum. These complaints have been around for a while and I think that Ms. Krush did a good job of summing them up, and them summing up here sum in this tldr:

>Many developers have been voicing their concerns about Agile being broken lately. Among them are prominent figures like Robert C. Martin and Kent Beck – two of the people who charted the Agile Manifesto. Some of the most frequently-mentioned problems with Agile are: Agile ignores technical debt; frameworks like Scrum are just “red tape,” which they were never supposed to be; programmers are asked to commit to arbitrary estimates and deadlines and never get the time to think thoroughly about the features they’re creating. So if we can acknowledge and work on these problems, perhaps we can fix Agile.

I've been on five scrum teams in the last two years, and I don't think that any of them wasn't suffering from at least one of these reported symptoms. I want to relay my experience and talk about how high-performing teams are using these "bugs" as features. I want to give a little unsolistied advice to each of these kinds of developers in turn, and maybe appeal those angels of better nature.

>Highlight 1: Agile = arbitrary goals and unrealistic deadlines.

All software is made up. It's okay, everything else is made up too.

There's a lot you can do as a team member on a team to influence how deadlines work. In what I'll call my "standard" understanding of scrum, the team sized stories as part of a definition of ready and commits to a sprint's worth of work at a time.

Ultimately, the team is the arbiter of how large any given user story is by story point estimating[footnote1]. The team could and should say if any given user story is too big to do in a sprint or if the scope of the story makes is difficult to manage against a definition of ready (unprovable, vague, or literally impossible). Committments are made on a per-sprint basis, and if the user stories are well-factored, can give business stakeholders a fair amount of predictability about "feautre done by x" status.

As an aside, the vast majority of software projects do fail. Being down on yourself about blowing a deadline is a feeling I'm familiar with. Your ultimate responsibility as a software engineer is on outcomes and a well-executed scrum or other flavor of agile is about getting to the firstest, barest version of a solution as possible and elaborating it with the most time left. Getting functionality, in priority order, scoped to achievable increments means that I rarely worry about larger scale deadlines beyond a couple of week's worth at once. 

Respect your team's velocity with these cool tricks:

- If new work comes into the sprint, throw out an equivalent amount of work.
- Use a 3-5 sprint rolling average of velocity instead of that one "hero" sprint as a yardstick.

>Highlight 2: Agile = “red tape” and no room for developer creativity.

This is easy enough to take on in two parts.

>Agile = “red tape”

If you're not using your ceremonies, stop doing them. There's never enough conference rooms around here.

Especially when getting started, it does seem like the team's in a room either working and doing a meeting poorly or in a room not doing _super valuable_ typing on computers kind of all of the time. 

My short answer to this concern is that sofware development is maybe top 5 in terms of jobs in terms of complications. Making a software product with your buddies is really hard, making a software product with the average team is really, really, really hard.

High performing teams I was on would regularly shift around their ceremonies. There's about a bazillion different formats for retrospectives (but sailboat is the best). Do different stuff at different points in the sprint. The usual suspects: daily standup, backlog refinement (1-2 hours a week's worth), sprintly demo, and retrospective are likely approaching the smallest amount of ceremonies a team needs. If your team doesn't have one of these, try it, see if you can get value of of it. The worst process is the one that's static and doesn't respect the people that power it.

>no room for developer creativity

Write user stories around letting people do stuff. Do your best job. The hardest part is to evict as many implementation details from squatting in your user stories. Constraints can cause more creativity, too. A team should be working on expanding it's capabilities on a sprintly basis. If someone isn't figuring something out that we wanna collectively do sort of all the time it's a sign the team doesn't have enough capacity to get better at it's job. High performing teams take this part as given.

> Highlight 3: Agile = rushing developers to do their job.

If you don't rush the bosses will hip-check you out of your chair and type the program into the internet themselves.

[Why software developers (quite honestly) hate Agile](https://www.objectstyle.com/agile/why-developers-hate-agile)

footnote1: Of course, this is relying on a team using a "common" implemenation of scrum. I've heard of teams that are given work pre-estimated by architects, team leads, managers, and analysts who are not directly in charge of the implementation. This caveat feels like it's applicable for many kinds of practices. Terms and conditions may apply see your scrum master for details.