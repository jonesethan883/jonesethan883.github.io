---
notetype: feed
date: June 6th, 2022
---
In this tutorial I'll show you how to set up a website to publish directly from your [Obsidian](https://obsidian.md) vault using this theme, and how to use its features.

This theme is a fork of [Jekyll Garden](https://github.com/Jekyll-Garden/jekyll-garden.github.io), and this tutorial will cover much of the same ground as their [[how to::https://jekyll-garden.github.io/post/how-to]]

As a disclaimer this method is probably more suited to building a new website from scratch using Obsidian as your writing and publishing tool than just putting an existing vault online. You'll need to format your notes and store your assets a particular way. It wouldn't be difficult to copy notes over, but know that it will require a bit more manual work than using Obsidian Publish.

## Basic Installation

### Step 1: Copying the theme from GitHub
Your site is going to be hosted on GitHub pages, a free hosting service for simple websites. We're going to create a copy of the code for this theme, put it on your GitHub account, and then store a local version of the website on your computer and use the GitHub desktop app to sync between the local version and the one stored on GitHub. This will let you edit files locally using Obsidian and then "push" the changes to your website.
- Go to <https://github.com/signup> and create an account. 
- [[A GitHub repository is essentially just a folder full of code which is hosted on GitHub. When you use a template you're just making a copy of the folder and putting it on your account, like when you have to create a copy of a protected Google Doc before you can edit it.::rmn]]Then go to <https://github.com/jonesethan883/HyperGarden> and press the green "Use this template" button on the right. Name your new repository `myUsername.github.io`, substituting in your actual username for 'myUsername'. Make sure it matches exactly. I'll cover how to use a custom domain name later.
- In your new repo go to the 'settings' tab on the top, then the 'pages' tab on the left. Set the source to 'main'. Just leave the theme blank.

### Step 2: Create a local version and open it with Obsidian

- Download and install [Github Desktop](https://desktop.github.com)
- Sign in to your GitHub account on GitHub Desktop [[For more information on how to use GitHub desktop <a href="https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/overview/creating-your-first-repository-using-github-desktop">see here</a>::lmn]]
- In Github Desktop click 'File' > 'Clone Repository', then select the repository you created and press clone. You should be asked to select a path for your repository. By default it will go in your Documents folder but you can change it if you want.
- [[You can also open just the _notes subfolder. This will be less cluttered however adding images to your notes will be more work.::lmn]][[assets/img/hypergarden.png::rmn-ibw]][[Your file tree in Obsidian should look something like this. You probably won't need to worry about anything except the \_notes, \_posts, and assets folders::rmn]]Now you're going to open Obsidian and create a new vault from a folder. Select the repository you just created as your folder. 
- To create your first page first make a note in the \_notes/Public/ folder. 
- In order to make your note readable we'll need to add some YAML to it. YAML is a simple method of adding metadata to a note which won't be rendered in the final page. Put three dashes at the very beginning of the note to start the YAML, then define variables like `variable: value`. Once you've defined all the variables add another three dashes to end the YAML.
- We need to add a title, a date, and a note type. The title needs to be the same as the file name for the note, so if you have `Apples.md` it will be `title: Apples`. This is what lets notes link to each other properly. Adding this every time you create a note can be tedious, so I'll show you how to use templates to do it automatically later.
- 'notetype' controls whether or not the note is visible and on which index. To make it visible on the main feed set it to 'feed'
[[The date can be in a variety of formats. 2022-06-16,  would also work. ::lmn]]

```
---
title: Apples
notetype: feed
date: June 16th, 2022 
---

Apples are my favorite food.
```

- Now that you've created the note you need to push the changes to GitHub. Open GitHub desktop and 