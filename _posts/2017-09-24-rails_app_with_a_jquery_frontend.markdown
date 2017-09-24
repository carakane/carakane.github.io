---
layout: post
title:  "Rails App with a jQuery Frontend"
date:   2017-09-24 20:38:02 +0000
---


Implementing a jQuery frontend on my [Volunteer Manager](https://github.com/carakane/volunteer_manager/tree/jquery) Rails application was in some ways a more complex undertaking than making the application to begin with. To start with, although I'm fairly comfortable with errors, there's a big difference between fixing something that's broken and breaking something that's working and then fixing it! I liked the flow of my application, and adding the jQuery frontend involved a lot of problem creation and then problem solving.

Absolutely the biggest problem I faced dealt with the location of the JavaScript files and how they would be accessed by the Rails views. Separation of concerns dictates that the JS files belong in the asset pipeline. In many ways it's so much easier in an application this size to just put the JS in script tags in the views---then the JS is only available to the correct view at the correct time. But I felt obligated to put everything in its place, which resulted in a lot of issues. The compilation of the JS into one file makes $(document).ready() functions conflict, for one. I ended up requiring each individual JS file and specifying its target by interpolating the controller and action into the JS include tags in the header.

This then caused its own set of issues, as a resource would load correctly the first time it was accessed but not after, which was a result of the functionality of the Turbolinks gem. Turbolinks allows parts of a site to be cached so that load times are shortened as users navigate from page to page. I tried to fix this conflict by specifying JS implementation on $(document).ready() and on $(document).on('turbolinks:load'), but this was ultimately unsuccessful because of when Turbolinks fires its load function, which is in between clicking on something that would load the next page and actually loading the page. Eventually I removed the Turbolinks gem and the JS loaded as expected. I'm certain there must be a way to keep Turbolinks and also utilize JS for frontend functionality without conflict, but unfortunately that was a failure of my project.
