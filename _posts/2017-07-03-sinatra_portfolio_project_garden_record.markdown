---
layout: post
title:  "Sinatra Portfolio Project: Garden Record"
date:   2017-07-03 18:00:04 +0000
---


For my Sinatra portfolio project I made a garden record, which tracks plants and planting locations. Once a user has made a password-protected account, they can create custom planting locations and plants, and then associate those and view them all or individually. Reflecting on this project, I have three primary thoughts.

First, it strikes me again how different it is to program without tests. The lab format, which has us write code to pass specific tests, drives your program forward. You might have trouble figuring out how to make a test pass, but the nature of the tests is that your next objective is clear. Without tests, it's easy to feel like you're out in the wilderness without a map. In lieu of tests I used a checklist to keep track of the main responsibilities of my program as well as bugs that showed up along the way. Although at times it felt like the checklist would expand forever, in the end it turned out to be a manageable way to guide my work.

My second thought is about what it takes to prevent users from seeing data they shouldn't see. Even for a program as small as this one, it was surprising how much code was required to ensure that a user couldn't access another user's homepage, plants, and planting locations. It's likely, of course, that my code could be refactored, but it was still an eye-opener to see how many routes need to be protected.

The last thing I'd like to mention is that it's also very striking how many decisions the programmer must make, even in a relatively simple program. Relationship models seem like straightforward concepts, but implementing them in a way that makes sense for the program isn't always as straightforward. Although, as with all of these points, I'm sure that will get easier with practice!
