---
title: How to use Git Submodule to manage Hexo themes
date: 2018-01-24 23:37:03
categories:
- Git
tags: 
- hexo
- git
- git submodule 
---
In the last blog [How to update Hexo and Hexo theme properly](https://dandyxu.me/Hexo/How-to-update-Hexo-and-Hexo-theme-properly/ "How to update Hexo and Hexo theme properly"), I manage both Hexo blog and Hexo themes as Git Repositories. However, I met a problem when I push everything to remote repo and tried to pull to another PC/Mac.

### Where is my theme?

<!--more-->

The image below you will probably see:

![Git Submodules](https://s3-eu-west-1.amazonaws.com/dandyxu.me.assets/images/Git_Submodules.png)

As you can see in the screenshot, both `edinburgh` and `next` are shown differently with `landscape`. If in this case, you pull the whole repo to another laptop, you will surprisely find these two themes are autually empty!

### What's going on?

I don't want to talk from the beginning about the concept of `Git Submodule`. Here is an article explained extremely great.

https://chrisjean.com/git-submodules-adding-using-removing-and-updating/

In this blog, I just want to show you how I use git submodules to update, manage Hexo themes.

### My personal workflow to manage Hexo themes

Because we still need to update themes by merging upstream from original theme repo, so it's better to keep themes folder as git repo.

If you go through the article I shared above, you will basically know `Git Submodule` is just kind of reference or path if there is git repo totally under another git repo. After adding git submodules, you will have a new file called - `.gitmodules`, which pointing out the path to the submodules.

So, if I do some changes in the theme file, for example, I update the theme or change some settings in the theme _config.yml file.

1. Navigate to theme folder, commit and push all changes. This step is just committed to theme repo;

2. Navigate back to the Hexo root folder, you will see changes for the theme folder, for example, `/themes/next`. In this case, you need to commit the theme folder, then push.

### Migrate to another environment

1. Clone Hexo git repo. But in this stage, you only find empty theme folders;

2. Navigate to theme folder, Initialize the submodule(s)

`$ git submodule init`

3. We need to run the update in order to pull down theme files and populate submodules

`$ git submodule update`

That's it. With all actions above, you're able to manage Hexo themes via submodules easier and smoother. Well, it took me a while to figure it out, I still remember that I spent nearly 3 days working on this issue (I thought it's something wrong with Git!).

Hope it will help you if you meet the same problem like me.

Have a good night!


