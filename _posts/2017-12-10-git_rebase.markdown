---
layout: post
title:      "git rebase"
date:       2017-12-10 17:05:48 +0000
permalink:  git_rebase
---


This week I went to a talk by [Catherine Meade](http://catheraaine.com/) of [Sparkbox](https://seesparkbox.com/), who discussed GitHub pulls and how to better engage and document GitHub pull requests when working on a team, especially a team that includes people who respond well to different kinds of thinking or information processing (e.g., visual vs. textual). Cat is an engaging speaker and offered a lot of useful resources that we might use to improve our communication and collaboration. She'll be offering the talk again at [CodeMash](http://www.codemash.org/) and [JSConf Iceland](https://2018.jsconf.is/), and if you're there you should check out her talk!

One of the topics that came up in the discussion after the talk was rebasing. I've heard of rebasing before but it's not something I've ever done, so I decided to learn more about it. The [GitHub documentation](https://help.github.com/articles/about-git-rebase/) (which is easier for a beginner to the topic than the [Git documentation](https://git-scm.com/docs/git-rebase)) says that ```git rebase``` is used to change the history of your commits---you can change the commit message, squash multiple commits into one commit, and remove or revert commits you no longer want.

At first blush, rebasing sounds antithetical to the essence of Git. Git seems to be about tracking every change and creating the history of a project. Rebasing allows us to change that history, and needless to say the internet is full of opinions about whether rebasing is a good idea.

I can imagine that there are potential pitfalls in using this in a production setting, and the dynamics of how your team works and the specific workflow of your project would have a large impact on which aspects of rebasing were useful to you as opposed to hazardous. That said, who among us has not wished to reword a commit? Or made a commit and then very quickly made another commit that could've just as easily been part of the first? If in some ways our commits are reflexive saves, ```git rebase``` allows us to restructure or edit our reflexiveness into something more coherent. In that sense, rebasing can help us tell a better story with our code, and then it's easy to see the upsides of using this in a team setting.
