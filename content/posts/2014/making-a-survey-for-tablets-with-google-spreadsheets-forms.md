+++
date = "2014-08-28T22:18:58-08:00"
draft = true
tags = []
title = "Making a survey for tablets with Google Spreadsheets/forms"

+++

[Google forms](http://www.google.com/google-d-s/createforms.html) are a great tool to throw together quick feedback forms – [we](http://www.pagerduty.com/) use an iPad with a form in the lunchroom to rate our caterer.

Great idea, poor execution. Most of them end up looking awful.

We can do better. Take [this form](https://docs.google.com/a/pagerduty.com/forms/d/1V6pF3NGpEev0Pl8p22V2fmfHtx-09UtF0bnyAuFoN5E/viewform) for instance. We can convince just about anyone to click on a form optimized for an iPad: [Live demo](http://euri.ca/files/meetup.html)

The great news, is that the form is just HTML that you can muck around with that goes straight into a [Google spreadsheet](https://docs.google.com/a/euri.ca/spreadsheets/d/1d3BpNFRzovbvZ98YoEA2VUYT41RvQveEZ7WLIzBUn-4/edit#gid=856404457). Open up your form and view the source. You only need 2 values: the form’s action URL and what the input’s name is:

[![where to find values](http://euri.ca/wp-content/uploads/2014/08/view-source_https___docs_google_com_a_pagerduty_com_forms_d_1V6pF3NGpEev0Pl8p22V2fmfHtx-09UtF0bnyAuFoN5E_viewform-1024x490.png =620x296)](http://euri.ca/wp-content/uploads/2014/08/view-source_https___docs_google_com_a_pagerduty_com_forms_d_1V6pF3NGpEev0Pl8p22V2fmfHtx-09UtF0bnyAuFoN5E_viewform.png)

Then stick them in this HTML (and probably tweak the CSS). The text in the DIVs

| --- | --- |
|  | <html> |
|  | <head> |
|  |   <meta name="viewport" |
|  |         content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" /> |
|  |          |
|  | <script src="https://code.jquery.com/jquery-2.1.1.min.js"></script> |
|  | <script> |
|  |  |
|  | // Step 1. Put the URL from <form action="URL"> here: |
|  | var form_url = "https://docs.google.com/a/euri.ca/forms/d/1V6pF3NGpEev0Pl8p22V2fmfHtx-09UtF0bnyAuFoN5E/formResponse" |
|  | // Step 2. Put the name from <input type="radio" name="entry.123"> here: |
|  | var radio_button_name = "entry.1511256644" |
|  | // Step 3. Fill in the options in the divs below: |
|  |  |
|  | clickon = function(e) { |
|  |   me = $(e) |
|  |   me.addClass( "clicked_on" ) |
|  |   form_data = {} |
|  |   form_data\[radio_button_name\]=me.text() |
|  |   $.post( form_url, form_data, function( data ) { |
|  |     console.log( data ); |
|  |   }).always(function() { |
|  |     $(e).removeClass( "clicked_on" ) |
|  |   }); |
|  |  |
|  | } |
|  | </script> |
|  |   |
|  |   |
|  | <style> |
|  | * { |
|  |   transition:all .3s ease; |
|  |   color: #1F293A; |
|  |   text-align: center; |
|  | } |
|  | .clicked_on { |
|  |     background-color:#1962FF; |
|  |     color: white; |
|  | } |
|  | .option { |
|  |   border: 2px solid #1962FF; |
|  |   padding: 50px 30px; |
|  |    |
|  |   border-radius: 25px; |
|  |   font-size: 20pt; |
|  |   margin: 8px; |
|  | } |
|  | iframe { |
|  |   width:100%; |
|  | } |
|  | </style> |
|  | </head> |
|  | <body> |
|  | <h1>How was the meetup?</h1> |
|  | <!-- change these values to be the answers to your survey: --> |
|  | <div class="option" onclick="clickon(this)">Great!</div> |
|  | <div class="option" onclick="clickon(this)">Too long</div> |
|  | <div class="option" onclick="clickon(this)">Too short</div> |
|  | <div class="option" onclick="clickon(this)">Not technical enough</div> |
|  | <div class="option" onclick="clickon(this)">Too technical</div> |
|  | <div class="option" onclick="clickon(this)">Not enough food</div> |
|  | </body> |
|  | </html> |

[**view raw**](https://gist.github.com/eurica/618c704578adacfbbca0/raw/81195c6d8da81057daf3960a90570be346a47baf/survey.html)[**survey.html**](https://gist.github.com/eurica/618c704578adacfbbca0#file-survey-html) hosted with ❤ by [**GitHub**](https://github.com/)

Categories: [programming](http://euri.ca/category/programming/index.html) | Tags: [design](http://euri.ca/tag/design/index.html), [ux](http://euri.ca/tag/ux/index.html) | [Permalink](http://euri.ca/2014/making-a-survey-for-tablets-with-google-spreadsheets-forms/index.html)