---
title: How to update Hexo and Hexo theme properly
date: 2018-01-23 21:20:53
categories:
- Hexo
tags:
- hexo
- hexo theme
---
In the previous blog, I introduced how to update Hexo and Hexo theme - `NexT`. However, since Hexo 3.0, it's recommended to install `hexo-cli`, which is command line interface for hexo.

<!--more-->
### Install Hexo

`$ npm install hexo-cli -g`

which install `hexo-cli` globally

### Update Hexo

Because Hexo is managed by npm, so the update command should be:

1. Change into blog directory with `package.json` file
2. Run `npm update`

### Update Hexo theme - NexT

The current theme I'm using for this blog is `NexT`. It's originally developed by a Chinese developer - `Vi`. However, in Dec.2017, for some reasons, it switched to a Russian developer to manage and maintain. The theme is rebased to Version 6.0.0 and moved to an entire new Git repo.

Original Repo:
https://github.com/iissnan/hexo-theme-next

New Repo:
https://github.com/theme-next/hexo-theme-next

From what I can see, it seems this Russian developer is very keen on the NexT, which is really great. He's working with other Chinese developers, building the new official website for NexT theme and keep fixing bugs, adding features etc.

New Link: https://theme-next.org/

There are 3 days left to be launched. Personally I'm really looking forward to the new website and hope in some stage, I can get involved in this great project.

Back to the topic, because installing the Hexo theme is actually clone the theme repo and enable it in the Hexo root _config.yml file. So, to update the theme, it's just `git pull` from original theme repo and it will fetch and merge automatically (if no conflicts happened, finger crossed!). 

The command will be:

`$ git pull`

There are two situations I would like to emphasize:

1. If you forked the theme to your own Repo, you need to add original Repo as upstream remote Repo.

    Step 1: `$ git remote add upstream {remote Repo link}`
    
    Step 2: `$ git remote -v` to check whether added

    Step 3: `$ git fetch upstream`

    Step 4: `$ git checkout master`

    Step 5: `$ git merge upstream/master`

2. Git Submodule topic (I will talk about it tomorrow)

That's all today. I will talk about `git submodule` this concept and how I use Git Submodule feature in the workflow of building and maintaining this blog.

See you tomorrow.



