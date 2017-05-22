---
layout: post
title:  NPR News Headlines --- My CLI Data Gem Project
date:   2017-05-22 18:11:17 +0000
---


I toyed with several different ideas before I began my CLI Data Gem project, and eventually I decided to make an NPR News Headline scraper. 

The NPR News site is organized very cleanly, and the actual scraping of the relevant information wasn't too difficult. Luckily, even though not every headline displays teaser text of the actual article, the text is still available in the HTML, so there weren't any issues with display inconsistency between headlines. I did, however, encounter two major problems that I had to contend with. The first was that, when scraped, the teaser text that accompanied each headline began with a date, but luckily Stack Overflow came to my rescue, and I found a good RegEx that helped me remove the date and that I then edited slightly to also remove some leading whitespace. 

The second problem was entirely of my own making. Initially I thought I might push the headline information into a hash as it was iterated through, and so I had commas after each headline attribute assignment. When I moved on from the hash idea, I forgot to delete the commas. They didn't throw an error, and instead pushed all of the assigned attributes into an array under one of the attributes. Despite the fact that my css scraping selectors gave me the correct returns when I dropped into pry, I was convinced that something was wrong with the css selectors and it took me more time that I would have liked to figure out that my errant commas were causing the problem.

In terms of the structure of the program I one big decision to make: whether or not to scrape the news division headings. I suspect that these are fairly static, and scraping them in addition to scraping the headlines makes the program a little slower. Conversely, scraping them and then allowing division selection based on the number of divisions scraped also makes the program less brittle, because any change in the divisions can be automatically accommodated, so this is what I chose to do. 

As the project stands now, the user can choose a news division and then view the headlines in that division. The NPR News site also has subdivisions, which could be an avenue of future expansion for the program. And, of course, allowing the user to choose a headline and view the entire article would also expand the program's capacity, but essentially replicated the website as a CLI seems ethically dubious. 

I really enjoyed this project. In some ways it was harder to come up with an idea and make it a reality than it has been to respond to failed tests in a lab (although of course I could have tried to write my own tests), but it was also really satisfying. As a bonus, now I'm caught up on the news!
