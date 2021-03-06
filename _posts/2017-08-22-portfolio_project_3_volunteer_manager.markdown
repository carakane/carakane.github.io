---
layout: post
title:  "Portfolio Project 3: Volunteer Manager"
date:   2017-08-22 13:25:31 +0000
---


Our third Flatiron portfolio project is a complete Rails application. My project, [Volunteer Manager](https://github.com/carakane/volunteer_manager), is an application that allows users to assign volunteers to volunteer opportunities at their organizations. From a user's perspective, the app is fairly straightforward: they are able to create a password-protected account or sign in via Facebook. They then add to their account the organizations under their purview and the opportunities available at those organizations. The opportunities use days of the week as a basic availability measure. Volunteers can be added to a sitewide database and share the same availability measure. Users can view all the volunteers and can then assign one available on the same day as their opportunity.

From my perspective as the developer, this project required a lot of thoughtfulness. Imagining the application as a real-world tool helped me hypothesize what a user would need it to accomplish, although I suspect a real-world user would ultimately benefit from quite a bit more functionality in terms of availability specificity, a change that would create a ripple effect in the database. In the real-world a user would probably also want to be able to keep records about the skills and personalities of the volunteers and have automatic notification functionality, volunteers would need their own accounts, and the list goes on! It's easy to see how a project that seems simple requires quite a bit of functionality.

There were many aspects of this project that I found really satisfying: getting Devise and OmniAuth working correctly, rendering partials, and writing and using Class scope methods, to name a few. And I've only recently started seeding databases myself, but using Faker makes it enjoyable. Although this application is unlikely to ever be implemented in the real world, I really appreciate creating something that has the skeleton of an application that could be a real-world application with more work.
