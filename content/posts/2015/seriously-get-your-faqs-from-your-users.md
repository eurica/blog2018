+++
date = "2015-11-26T21:44:41-08:00"
draft = true
tags = ["pagerduty", "product management"]
title = "Seriously, get your FAQs from your users"

+++
Listening to [Kathy Sierra](http://www.amazon.com/gp/product/1491919019/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=1491919019&linkCode=as2&tag=eurica0d-20&linkId=QZNVT6RQMME46N5O) at [Mind the Product](http://www.mindtheproduct.com/), she makes the point that your users are not happy stock photos, that your product’s make it or break it moments are often when the user feels helpless.

She had a lot of good points, but when she mentioned that help & FAQs are usually written from exactly the wrong perspective it reminded me how easy this problem is to solve.

You should already have the data to make better help.  Here’s what we do at PagerDuty

* Track all the pain points you see in usability sessions.  Ideally you should fix the most common ones, but if you can’t: use the wording the user uses to express what they are doing and make it findable from the page that they get stumped.
* Track all the searches in your help docs and use that to prioritize help articles & FAQs.  Again it’s a great source of how the user words their issues.
* Quantify UX pain with metrics. We use KISSMetrics to track how many people get stumped in a task.  Some of them are obvious to fix: we saw too many people clicked on disabled page elements and so we made that clearer, other times we direct them to the right documentation for their integration.
* We have inline help with a person powered by Olark on every page. This is much more expensive, but it also gives you the chance to clarify and really understand the person’s question (as well as to solve it).
* And here’s a big one a lot of company ignore: help people who aren’t even asking.  One of the great thing about tools like Intercom (which we don’t use, we do this manually) is that you can identify groups of users having a degraded experience — and while it may be the wrong product call to change the UX for everyone, you can send them the information they need to succeed.  For us, one of these groups might be “people who use PagerDuty with physical pagers”, “people who send hundreds of alerts to the on-call person every day” or “people who people who have 10 contact methods”. Those are all very small groups (relatively) but they’re easily identified fro the data and we reach out to them proactively to improve their experience.

A great support team (seriously, [come join us](https://www.pagerduty.com/company/job-openings/?jobid=a0Kj000000261BREAY)) definitely helps, but they key element is getting into the frustrated customer’s mindset from the actual words they use and the actual frequency they use them.

[![If you want them to RTFM, make a better FM. - Kathy Sierra #mtpcon]](https://twitter.com/AmbassadorAwsum/status/606513949543133185)

{{< tweet 606513949543133185 >}}