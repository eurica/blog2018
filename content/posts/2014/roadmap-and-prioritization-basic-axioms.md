+++
date = "2014-10-28T22:14:23-08:00"
draft = true
tags = []
title = "Roadmap and prioritization basic axioms"

+++

_This is part of an_ [_ongoing series to document what I learned_](http://euri.ca/tag/what-i-learned-at-pagerduty/index.html) _growing_ [_PagerDuty_](http://www.pagerduty.com/) _from 6 people to over 100 in 3+ years._

There are 4 necessary ingredients every roadmap needs to be a successful:

1. Benefits
2. Costs
3. Hopes and dreams
4. A defined process for horse-trading

The MVP for a roadmap is a list of features. The size of each of the items on the list depend on how much your organization struggles with prioritization, but the list needs these basic characteristics:

Costs & Benefits  
These are your basic ingredients for every item. There are a lot of flavors of each to choose from, but they’ll both need to be represented.

In cases of uncertainty, round cost up and benefits down. For the top items on the list, it’s up to the product team to tidy up the benefits and engineering to narrow the estimates on the cost to the point where your comfortable starting work.

Breaking down the benefits:  
Granularity gives better estimates; in terms of breaking down benefits, I like the following:

* Immediate customer benefit: when we launch this feature, how much of a splash will it make with current customers and sales that we can close because of this.
* Urgency: how much better it would be to launch this feature now vs in the future.
* Strategic impact: how much this contributes to our long term vision.
* Unfair advantage: why we should launch this feature.

The first 3 items are very similar to User-Business Value, Time Criticality and Risk Reduction/Opportunity Enablement Value from agile development’s [Weighted Shortest Job First](http://scaledagileframework.com/wsjf/) ordering. Your unfair advantage is described well in the [Lean Canvas](http://leanstack.com/), but can also be thought of as building vs partnering.

I also like to call out the the top requests, e.g. the #1 support request, the #1 chance to learn, the most used feature, etc. to give those features bonus points.

Costs  
There are several types of costs:

* The raw effort in terms of resources
* Future ongoing maintenance this feature will cause
* The criticality of resources used relative to you
* How much institutional overhead you’ll need to navigate with this feature; this also includes how much effort changing the plan would be, especially if you’ve made external commitments to partners.

Costs aren’t always going to be fungible, so you may not be able to pursue all equally costed items interchangably.

Hopes and Dreams  
The list should have at least twice as many things as you can get to. The bar to being on the roadmap is very low — things on the bottom of roadmap will be very vague, and come at the cost of writing a sentence.

There is no upper limit on how many things that you won’t do.

Process for re-prioritization  
However you do it, there needs to be a regular and inclusive process to re-visit the roadmap. There are many valid possibilities:

* Give each department some number of votes and do the items with the highest vote/cost ratio. This has the benefit of making explicit the relative weightings of e.g. Sales vs Customer Support in the organization.
* Stakeholders can get into a room for [planning poker](http://en.wikipedia.org/wiki/Planning_poker)
* The product team can re-evaluate each row on a schedule
* A benevolent dictator can look at the data and pick what they want

Engineering can be asked to generate detailed plans for features or approximate costs with a gut check but engineering needs to be heavily involved in generating costs.

For one’s sanity, just accept that there’s going to be an emergency entrance at the front of the queue and work to minimize it. There should be one person’s job to protect this queue and evaluate all queue jumpers (and reject most of them).

And then everything else…  
A list of features is necessary, but it may be a long way from sufficient. It doesn’t convey a strategy or a vision, but it does help to get everyone pointed in the same direction.

Categories: [product management](http://euri.ca/category/product-management/index.html) | Tags: [What I learned at PagerDuty](http://euri.ca/tag/what-i-learned-at-pagerduty/index.html) | [Permalink](http://euri.ca/2014/roadmap-and-prioritization-basic-axioms/index.html)