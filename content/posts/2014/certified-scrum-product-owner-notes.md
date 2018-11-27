+++
date = "2018-11-26T22:02:39-08:00"
draft = true
tags = ["agile", "notes", "product management"]
title = "Certified Scrum Product Owner notes"

+++
December 14, 2014 by dave

We sent a truckload of PMs and engineers to a 2 day Certified [Scrum](http://en.wikipedia.org/wiki/Scrum_%28software_development%29) Product Owner course from [Jeff McKenna](https://www.cprime.com/training/instructors-and-coaches/jeff-mckenna/). I was a little surprised to hear that Scrum trainers aren’t allowed to change their slides once they’ve been approved — switching between the powerpoint deck and the unsanctioned handouts was surprisingly distracting.

The class started off with an amusing bit of the [Dunning-Kruger effect](http://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect) when we sorted ourselves in order of agile experience. Since most of us at PagerDuty had done the reading already, I found myself listening a lot to the background patter:

> “I got out of coding because it’s always the same thing over and over.”
>
> “I wanted to be the manager so I could be the one giving the orders.”

If nothing else, taking part in training is a great chance to better understand the median software management process, but needless to say, doing the same thing over under orders is not something that excites me. There were a few good discussions of “doing agile” vs “being agile”

Here are my rough notes:

First up: You can’t improve what you can’t see, so we discussed a few variations of process control with 3 characteristics: You can see it, understand what it means and have the power to do something. We mentioned the Department of Defense’s [Capability Maturity Model](http://en.wikipedia.org/wiki/Capability_Maturity_Model)  
although in terms of military models, I prefer to think about how we can tighten John Boyd’s [OODA loop](http://en.wikipedia.org/wiki/OODA_loop).

A Scrum team should be

* 3-9 people working cohesively full time — that’s empowered to say no when they don’t think that they can deliver.
* The Product Owner is responsible for maximizing the value of the work being done.
* The ScrumMaster is in charge of optimizing the team’s velocity, this is distinct from the product owner’s role — which seems to be one of the lynchpins of Scrum.
* Part of the ScrumMaster’s role is to “Manage impediments” — in my mind, that’s a job the product owner shares heavily in, especially when those impediments have root causes in other stakeholders.

The entire team works on **one story at a time**, this seemed to me like an artifact of having large stories or inefficient deploy technologies. A team where one person can understand the whole of the team’s domain and uses modern deployment tools feels like it would cause more overhead — the 9-women-1-baby-1-month scenario.

The effort required to make a change should be proportional to: (the origin thought put in) multiplied by (the magnitude of current usage/dependencies).

When ordering projects projects by descending RoI, break ties in favour of doing the smaller ones first — the variance is lower, but also you can release them sooner. But don’t do small things to the exclusion of big things.

“Burndown charts don’t help during a sprint”

Story Points:   
Every story needs a value. 1 story point can be considered the minimum possible change, which is largely a measure of your overhead: a conversation, branching master, making a tiny change, running the tests, submitting a pull request, doing a code review. 0 points can be considered a story that can share the overhead with just about any other story — such as a text change to a part of the code that you’re already touching this sprint (conversely, a text change to a different part of the code, may require its own conversations and overhead). Targeting 40 story points per sprint is a good balance between generating too much detail and having enough stories to invoke the [Law of Large Numbers](http://en.wikipedia.org/wiki/Law_of_large_numbers) — “average of the results obtained from a large number of trials should be close to the expected value” — to generate relatively consistent sprint estimates. Personally, I prefer valuing stories 1, 2, 4, 8, 16 &c over the fibonnaci sequence, but the important thing is the delta between story sizes increases with the sizes (in fairness I really don’t understand the obsession with using powers of [1.618](http://en.wikipedia.org/wiki/Fibonacci_number#Relation_to_the_golden_ratio) over powers of 2).

A minimal story probably involves at least one branch statement. “I can enter my first name” and “I can enter my last name” don’t make for independent stories.

Estimate the future using [yesterday’s weather](http://martinfowler.com/bliki/YesterdaysWeather.html): you’ll get the same done next sprint as last sprint. This is in sharp contrast to the worst project I ever worked on: where every iteration, we predicted 40 points, and did 30 — so management would ask how we planned to do 50 points next sprint.

Don’t have a “done-done” state. The definition of done includes testing to the point where people can change the code in the future and not break any implied (and hence un-tested) assumptions. Otherwise you’ve made the code more fragile. I suspect the ideal level of testing isn’t measured by percent code coverage but rather having emotionless deploys — where even new employees can make changes, and if the tests pass, you’re completely comfortable deploying the changes. Code reviews then only serve to: enforce code cleanliness, confirm that the new code works and to ensure the same level of testing going forward. McKenna believes there’s too much tolerance of bugs in silicon valley today; I’m not sure how much I agree — there’s certainly a lot of crappy software being written, but when you’re writing something that benefits from network effects (Twitter, Facebook) rather than something where you are solving a particular problem that touches on revenue for businesses (PagerDuty, Salesforce.com) I can understand the urge to increase your feature velocity for 95% of your users rather than dot the i’s and cross the t’s for the remaining 5%.

The value of fixing technical debt is measured by its effect on velocity — don’t forget the estimated time to End-of-life-ing a particular piece of code. Technical improvements can address user stories too — performance is a feature. Everything worthwhile can be demoed to the right audience: these tests failed and now they pass, deploys take 40% less time, 4000 lines of code comply with our style guide, &c.

Long term planning involves documenting and socializing the “Approach” rather than the “plan”. Everything needs acceptance criteria, “3 people on the team have read and understood the approach” is a good one.

Dan Pink’s [Drive: The surprising truth about what motivates us](https://www.youtube.com/watch?v=u6XAPnuFjJc) raised an interesting point — paying people enough “not to think about it” is increasingly hard in San Francisco.

“10-20% of people shouldn’t do agile” (based on the description of those 10-20%, it sounds like they actually shouldn’t do software). Converting a Project Management Professional (PMP) to a ScrumMaster is a pathway to strife & conflict.

The Sprint Review involves a demo — the product owner encourages people to come.

“Buffer the promise, not the plan” — aim for accurate estimates, but don’t promise them, you’ll be over 50% of the time even in a perfect world.

Scaling scrum cross-team & remotely: Have a scrum of scrum where the people most exposed to cross-team issues check that no-one is blocking anyone else. Dependencies highlight problems in your team structure. Keep teams together, if the team has to be remote, leave the product owners at HQ.

If the house is on fire every week, it’s not a fire, you just live in a particularly hot house. Schedule a fire drill every week, make it a [0 point story](https://chrisgagne.com/1756/tracking-unexpected-requests-impediments/), and track how much time is spent on it.

One pseudo-strength of the waterfall method is you can document a huge pile of potential functionality that satisfies every stakeholder and then react with shock when most of it doesn’t get done — with agile, you can re-prioritize actual functionality every sprint, which can mean a lot more contact with stakeholders.

One thing that I disagreed with was verbiage around “Must do” vs “Should do”, “Could do” and “Won’t do”.

Ideally 100% of the time should be spent on “Should do”, since “Must do” generally arises when the product owner (or the stakeholders) missed something coming down the pipe. When the iPhone came out, RIM/Blackberry had a boatload of things that they needed to do — likely more than they could in a timeframe that mattered; it was up to the product team to tackle those things proactively. Sometimes an external actor can dump something on you without warning, the European Union could require your software to track users with actual homebaked gingerbread cookies; but those are rare — and if they are not in your sector, you should invest in lobbying and research.

“Should do” is another word for “Has a positive return on investment based on our velocity and market”. So a “Won’t do” can be promoted if the market or our velocity improves, and similarly a “Should do” can be demoted if we slow down or our market position weakens.

“Could do” is just a holding area — we make software, we could do just about anything. It’s up to the product team to understand the potential RoI, in whatever terms & accuracy your organization operates in. The “Could do” list will likely be longest list by far. Predicting that some fraction of the could’s will become should’s seems like a convoluted way of padding your estimates.

In the exercises we worked on, the class seemed far too eager to both accept that a feature was mandatory and that we should do some fixed fraction of the things that we _could_ do. Planning on doing half of all the things that we’ve put on the backlog to satisfy stakeholders seems like asking for trouble.

Other:  
Things to look in to: Agile portfolio planning, JIT Budgeting & [Beyond Budgeting](http://bbrt.org/), [Waltzing With Bears: Managing Risk on Software Projects](http://www.amazon.com/gp/product/0932633609/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=0932633609&linkCode=as2&tag=eurica0d-20&linkId=CCUMDYM526HQIIMM)

The class didn’t cover product discovery, which is the area that I’m most interested in. It was hard for me to charge in to some of the examples without doing a better job of justifying what we were trying to build.