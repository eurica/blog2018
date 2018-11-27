+++
date = "2014-11-15T22:13:35-08:00"
draft = true
tags = []
title = "Ask a PagerDuty API expert: #1 Dashboards"

+++
Background: I’m writing examples against the [PagerDuty API](http://developer.pagerduty.com/) for our developer evangelism team, here’s a sneak preview:

A dashboard of recent incidents 

[![PagerDuty_Dashboard_Example](http://euri.ca/wp-content/uploads/2014/11/PagerDuty_Dashboard_Example-300x210.png =300x210)](http://euri.ca/wp-content/uploads/2014/11/PagerDuty_Dashboard_Example.png)Some of our users have been using browser plugins to refresh the dashboard more frequently, there are some great tools that work with PagerDuty to do that: [StatusPage.io](https://www.statuspage.io/), [Geckoboard](https://www.geckoboard.com/integrations/pager-duty/), along with open source projects like [pagerduty-dashing](https://github.com/thegreenrobot/pagerduty_dashing) and [Brainiac](https://github.com/cmonty/brainiac).

But I reached out to some of those accounts, and they wanted something that:

* Can be displayed on a monitor like a status board
* Gives at-a-glance awareness of the volume and distribution of incidents to non-responders

Let’s do that with our API directly. Here are [the most recent incidents grouped by when they happened](http://euri.ca/files/dashboard/dashboard.html)including the state and who’s currently assigned.

Or, if you want to get started right away, it’s also easily configurable from the URL by passing in your subdomain and an  
[API key](https://support.pagerduty.com/hc/en-us/articles/202829310-Generating-an-API-Key). Put in your own values to generate your status page:

Subdomain:   
Your API key: 

How does it work:

Like all of my examples, this uses my JavaScript library [PDJS](https://github.com/eurica/pdjs) to do the authentication and handle the nitty-gritty aspects of the API.

See the source code

If you view the source, you’ll see it’s just one function “loadIncidents” which is run once the page loads and hits the [incidents API](http://developer.pagerduty.dev/documentation/rest/incidents) then loops through them for display, and finally schedules itself to run again in 30 seconds (Not the most efficient solution but it’s the easiest to explain). Here’s the important part in a little more detail:

| --- | --- |
|  | // Initiate PDJS: |
|  | PDJS = new PDJSobj({ |
|  |     subdomain: config\["subdomain"\], |
|  |     token: config\["token"\], |
|  | }) |
|  |   |
|  | loadIncidents = function () { |
|  |   //Hit the incidents API: |
|  |   PDJS.api({ |
|  |       res: "incidents", |
|  |       data: { |
|  |           sort_by: "created_on:desc" // get the most recent incidents |
|  |       }, |
|  |       //Once we've gotten new incidents display them: |
|  |       success: function (json) { |
|  |            |
|  |           //Throw away the last incidents: |
|  |           $("#mytimeline").html("") |
|  |            |
|  |           //Update the title to the current time |
|  |           t = moment(new Date()); |
|  |           $("#title").html("PagerDuty incidents as of "+t.format("dddd, MMMM Do YYYY, h:mm:ss a")+":") |
|  |            |
|  |           // Round the current time down (for the spacing) |
|  |           t.seconds(0).milliseconds(0).subtract(t.minutes()%config\["minuteblocks"\], "minutes") |
|  |   |
|  |           //iterate over each incident |
|  |           $.each(json\["incidents"\], function (n, i) { |
|  |             created_at = moment(i.created_on) |
|  |              |
|  |             // Format a pretty incident |
|  |             html = "<div class='incident "+i.status+"'>" |
|  |             html += "<span class='service'>"+i.service.name+"</span>" |
|  |             // ... Format the incidents.  This code is neither pretty nor complicated. |
|  |             html += "<div>" |
|  |              |
|  |             //Loop over however many breaks happened after this incident |
|  |             while(t>created_at) { |
|  |               $("#mytimeline").append("<div class='hour'>"+t.format("h:mm a")+"</div>") |
|  |               t.subtract(config\["minuteblocks"\], 'minutes') |
|  |             } |
|  |              |
|  |             //print this incident |
|  |             $("#mytimeline").append(html) |
|  |           }) |
|  |   |
|  |           // Refresh the list after a timeout |
|  |           window.setTimeout(loadIncidents, config\["refresh"\]*1000) |
|  |       }, |
|  |   }) |
|  | } |
|  |   |
|  | // Run once the window has loaded |
|  | $(window).load(function(){ |
|  |   loadIncidents() |
|  | }); |

[**view raw**](https://gist.github.com/eurica/9d772d15cc1e8be12157/raw/6f2d61538ba527cd463e87d37cd7683131cc9d71/dashboard.pseudocode.js)[**dashboard.pseudocode.js**](https://gist.github.com/eurica/9d772d15cc1e8be12157#file-dashboard-pseudocode-js) hosted with ❤ by [**GitHub**](https://github.com/)

## Further information

There are some other ingredients to this example:

* I wrote some CSS quickly, please feel free to take this code and make it much prettier — let us know what you build:
* There is also some code to parse query and hash parameters so that anyone could use this example. I’m a little proud of that last bit since anything after the #  
  [is not sent to the server](http://en.wikipedia.org/wiki/Fragment_identifier)
* [Moment.js](http://momentjs.com/) is being used to format and manipulate times.
* [jQuery](http://jquery.com/) (as always) is being used for some semantic neatness in the JavaScript.

## Bonus question: List everyone in an account by escalation policy

I’ve also been asked to list all user by which escalation policy they’re on. It’s not as visually appealing as the status page, but a pretty easy snippet nonetheless:

[http://jsfiddle.net/eurica/y9ojs7nx/](http://jsfiddle.net/eurica/y9ojs7nx/ "http://jsfiddle.net/eurica/y9ojs7nx/")

| --- | --- |
|  | // As always configure PDJS with your subdomain and api-key |
|  | PDJS = new PDJSobj({ |
|  |   subdomain: "webdemo", |
|  |   token: "CkNpsqH9i6yTGus8VDzA", |
|  | }) |
|  |   |
|  | // Here's the minimum possible UI: |
|  | printf = function (str) { |
|  |   console.log(str) |
|  |   $("#output").append(str) |
|  | } |
|  |   |
|  | //In case we have more than 100 escalation policies, I'll use PDJS's api_all helper function: |
|  | PDJS.api_all({ |
|  |   res: "escalation_policies", |
|  |   final_success: function (json) { |
|  |     //Once we've loaded all the EP's, clear the "loading..." message: |
|  |     $("#output").html("") |
|  |     console.log(json) |
|  |      |
|  |     //use jQuery to iterate over eac EP |
|  |     $.each(json.escalation_policies, function (i, ep) { |
|  |       printf("<h1>" + ep.name + "</h1>") |
|  |       //Within each EP, loop over the escalation rules: |
|  |       $.each(ep.escalation_rules, function (i, er) { |
|  |         printf("<h2>Level "+(i+1)+"</h2>") |
|  |         // Each escalation rule can have up to 10 targets (users or schedules): |
|  |         $.each(er.targets, function (i, t) { |
|  |           if (t.type == 'user') printf("<p><a class='user' href='http://" + PDJS.subdomain + ".pagerduty.com/users/" + t.id + "'>" + t.name + "</a>") |
|  |           if (t.type == 'schedule') { |
|  |             printf("<p><a class='schedule' href='http://" + PDJS.subdomain + ".pagerduty.com/schedules/" + t.id + "'>" + t.name + "</a>: <span class='" + t.id + "'>loading users...</span>") |
|  |             // If it's a schedule, user schedule/users to find who's on that schedule |
|  |             PDJS.api({ |
|  |               res: "schedules/" + t.id + "/users", |
|  |               success: function (json) { |
|  |                 console.log(json) |
|  |                 var users = "" |
|  |                 $.each(json.users, function (i, u) { |
|  |                   users += "<a class='user' href='http://" + PDJS.subdomain + ".pagerduty.com/users/" + u.id + "'>"+u.name+"</a>, " |
|  |                 }) |
|  |                 // Update all instances of this schedule with the users  |
|  |                 // note: this inefficient, if a calendar is use 3 times, it will be updated 3 times |
|  |                 $("."+t.id).html(users)  |
|  |               } |
|  |             }) |
|  |           } |
|  |         }) |
|  |       }) |
|  |     }) |
|  |   }, |
|  | }) |
|  |   |

[**view raw**](https://gist.github.com/eurica/b33e517bd7f74e6a703c/raw/ad9fe87bf31a4991b1dd65989f73bbf70d07dd5d/all_users_by_ep.js)[**all_users_by_ep.js**](https://gist.github.com/eurica/b33e517bd7f74e6a703c#file-all_users_by_ep-js) hosted with ❤ by [**GitHub**](https://github.com/)

Categories: [programming](http://euri.ca/category/programming/index.html) | Tags: [code](http://euri.ca/tag/code/index.html), [javascript](http://euri.ca/tag/javascript/index.html), [pagerduty](http://euri.ca/tag/pagerduty/index.html), [pdjs](http://euri.ca/tag/pdjs/index.html) | [Permalink](http://euri.ca/2014/ask-a-pagerduty-api-expert-1-dashboards/index.html)