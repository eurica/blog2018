+++
date = "2015-02-23T21:51:17-08:00"
draft = true
tags = ["code", "pagerduty", "pdjs"]
title = "Manually triggering incidents in PagerDuty"

+++
The easiest way to allow people to manually trigger incidents in PagerDuty is to set up an email service and publish the address. You may want to set up filtering to only trigger on email from inside your organization:

![](/uploads/Internal_testing_-_PagerDuty-1024x427.png)

But if you want more control, you can easily use my JavaScript library [PDJS](https://github.com/eurica/pdjs) to create an embeddable button on your internal wiki or intranet that triggers PagerDuty incidents.

<input type="button" onclick="PDTrigger(prompt('Incident Description'))" value="Click here to trigger incident" style="font-size: 125%;">
<script type="170e2cfbfe0dae3d6f2984b6-text/javascript" src="http://eurica.github.io/pdjs/js/pdjs.js"></script><script type="170e2cfbfe0dae3d6f2984b6-text/javascript">$=jQuery; PDJS = new PDJSobj();function PDTrigger(description) {PDJS.trigger({service_key: "660ca1d238914a2e8cb26248687cba20",description: description,incident_key: "manual_incident_"+Math.random(),details: {language: "English",page: "http://euri.ca"}});alert("Creating PagerDuty alert");window.open("http://euri.ca/files/dashboard/dashboard.html")}</script>

You can see your manually created incident on [the dashboard we built](http://euri.ca/files/dashboard/dashboard.html) in the [last API column](http://euri.ca/2014/ask-a-pagerduty-api-expert-1-dashboards/index.html).

Here's the code:

{{< gist eurica f8c9089e167b79ecc381 >}}

Try #2
{{< highlight javascript >}}
/* This is the button I'm using to trigger the incident:
<input type="button" onclick="PDTrigger(prompt('Incident Description'))" value="Trigger Incident">
*/

// Set up the library
PDJS = new PDJSobj()

function PDTrigger(description) {
    // Trigger via the rest API
    PDJS.trigger({
        service_key: "660ca1d238914a2e8cb26248687cba20",
        description: description,
        incident_key: "manual_incident_"+Math.random(),
        details: {
            language: "English",
            page: "http://euri.ca"
        }
    })
}ht >}}