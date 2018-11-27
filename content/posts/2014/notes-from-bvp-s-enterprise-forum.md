+++
date = "2014-11-17T22:12:59-08:00"
draft = true
tags = []
title = "Notes from BVP’s Enterprise Forum"

+++

[Bessemer Venture Partners](http://www.bvp.com/) invited me to join other product people from their portfolio companies for a mini-conference on product development for the enterprise. Here’s a rough pass at my takeaways, ranging from the obvious to the insightful:

Roadmapping:  
Always ask customers “What do you not like about what you do today?”

Voting on what to do next is not a great idea. It might be salvageable to vote on “will this feature move this needle”. Pandora’s model \[link\] may find the “things we absolutely have to do this quarter” but Pandora might be trapped in a competitive low margin space where they have things they must do, instead of building a product with a defensible moat where they are in control of what they want to do next.

Idea management is what PM does, it’s different from idea generation (which anyone can and should do). It’s up to PM to define the process & evaluation that an idea has to go through before its built and to put every new idea through its paces. There were several different processes discussed for how an idea gets into the product team’s funnel, some product teams actively solicit every last wisp of an idea (this is what PagerDuty does) other teams asked for business cases to be written up or presented internally to the product team. Everyone agreed that it’s important to market PM internally as the processors of the process not the single source of ideas.

Longtime PMs were impressed with the spreading acceptance that roadmaps will have broad dates rather than exact ones and that scope can change.

It’s important to understand what your customers want from dates on a roadmap, some PMs have found that large companies only want to understand when the next version is coming out so they can do release planning — so it’s better to release quarterly or twice a year with whatever functionality is ready. Other customer prefer the faster release cycle over the predictable dates. I was surprised at how many companies had slow release cadences (only me and one other PM in one discussion pushed to production daily).

Betas are exciting, bring customer excitement forward as much as possible, gather their feedback while there’s still time to use it.

There was not a lot of love for having a public roadmap. But take some chances to bring excitement forward.

Tracking Product Development:  
We spoke about how to measure product velocity, all the best techniques seem to track engineering velocity as a proxy (story points). Keep your story points representing the same type of thing (a function that does X) rather than representing a time period or you’ll never be able to measure engineering acceleration or deceleration.

One PM has a script generates a cheat sheet of what % of the user base uses each feature every week. We were all jealous of him, even if some features might be used by different personas on different schedules. It’s be awesome if that cheat sheet could be filtered by segment.

If customers want to be a part of beta programs, exchange that for a commitment to do regular NPS/feature surveys.

Does anyone make an invite only UserVoice? So that only confirmed customers can see the features, not competitors?

A PM makes a quarterly report that buckets each feature release by red/yellow/green according to his feel. Execs love it.

Does it ever make sense to filter feature requests through the account owner for a multi-user product?

Absolute NPS isn’t useful, but relative segmentation is: how do large accounts like us vs small, old vs new, etc.

Figuring out price elasticity is a hard problem, experiment according to your pricing model. Sales reps love price raises to clear the sales pipe (order now or the price goes up). Try to change your pricing independent of functionality so you can measure accurately.

Understand the budgeting process in your customers is valuable, if you sell 2 tools, one for sales and one for marketing bundling doesn’t make sense, they have separate budgets (so a bundled product is actually harder to buy).

Great quote: “Grandfathering old customers on pricing changes is necessary for our mental health to do pricing changes and research”

Resource Allocation:  
You can measure anything. Measuring a vibe or happiness team: median time to first employee referral.

Cycle through the person dedicated to maintenance. It can follow the on-call schedule, or rotate quarterly.

The goal is overall velocity, you optimize your maintenance around that.

Some orgs spend their maintenance time on bugs that don’t need PM involvement — how do they manage to find so many easy bugs in production, sounds like a failure of testing.

Dealing with tech debt, it’s engineering’s time with no questions asked but they should explain what they aim to fix before they do it.  
Bad: Change boring framework to new beta framework  
Good: optimize the slowest query/page/function, attack the bugs that alert the most often, one page tech proposals.

Bucket products and features into: create/build, grow, run, transform/deprecate in order of which ones have the brightest futures

“Me too” features: Are they table stakes now or can you ignore your competitor’s feature? Was it on your roadmap before, how does this change the timeline? Is the feature real or FUD? Try it out & arm your salespeople with the weaknesses. Launching it now is less exciting for marketing.

Categories: [product management](http://euri.ca/category/product-management/index.html) | Tags: [notes](http://euri.ca/tag/notes/index.html), [What I learned at PagerDuty](http://euri.ca/tag/what-i-learned-at-pagerduty/index.html) | [Permalink](http://euri.ca/2014/notes-from-bvps-enterprise-forum/index.html)