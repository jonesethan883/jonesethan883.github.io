---
title: How to use this theme
notetype: unfeed
date: June 6th, 2022
---

Go [here](https://purposeofasystem.com/notes/Lipsum) see a lipsum page showing some of the features of this theme.

In this tutorial I'll show you how to set up a website to publish directly from your [Obsidian](https://obsidian.md) vault using this theme, and how to use its features.

This theme is a fork of [Jekyll Garden](https://github.com/Jekyll-Garden/jekyll-garden.github.io), and this tutorial will cover much of the same ground as their [[how to::https://jekyll-garden.github.io/post/how-to]]. Jekyll Garden is a fork of [Simply Jekyll](https://simply-jekyll.netlify.app) so a lot of Raghuveer S.' excellent documentation also applies to this theme.
* TOC
{:toc}

As a disclaimer this method is probably more suited to building a new website from scratch using Obsidian as your writing and publishing tool than just putting an existing vault online. You'll need to format your notes and store your assets a particular way. It wouldn't be difficult to copy notes over, but know that it will require a bit more manual work than using Obsidian Publish.

## Basic Installation

### Step 1: Copying the theme from GitHub
Your site is going to be hosted on GitHub pages, a free hosting service for simple websites. We're going to create a copy of the code for this theme, put it on your GitHub account, and then store a local version of the website on your computer and use the GitHub desktop app to sync between the local version and the one stored on GitHub. This will let you edit files locally using Obsidian and then "push" the changes to your website.
- Go to <https://github.com/signup> and create an account. 
- [[A GitHub repository is essentially just a folder full of code which is hosted on GitHub. When you use a template you're just making a copy of the folder and putting it on your account, like when you have to create a copy of a protected Google Doc before you can edit it.::rmn]]Then go to <https://github.com/jonesethan883/HyperGarden> and press the green "Use this template" button on the right. Name your new repository `yourUsername.github.io`, substituting in your actual username for '`yourUsername`'. Make sure it matches exactly. I'll cover how to use a custom domain name later.
- In your new repo go to the 'settings' tab on the top, then the 'pages' tab on the left. Set the source to 'main'. Just leave the theme blank.
- Go to `yourUsername.github.io` in a browser. You should see your website. Now you're ready to start making changes to it.
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

- Now that you've created the note you need to publish your changes. Open GitHub desktop and in the bottom left you should see a 'Commit to main' button. You'll need to write a commit summary before you can press it, just write something like "Made my first note". Once you've commited the changes you can press the "Push origin" button at the top right to send the changes to GitHub. It will take a few minutes for GitHub to update your site, but once it has you can go to `yourUsername.github.io/feed` and you should see the note you just wrote. Click on it to open it.

## Customizing your site

### Config
To customize the site you'll need to edit the `_config.yml` folder in your repository. Open it using Notepad or TextEdit. You edit in the same way you did the YAML, `variable: value`. Simply jekyll has a [page](https://simply-jekyll.netlify.app/posts/customizable) going into detail on all the config options which you can look through, some of the features have been removed though so not everything will apply. For now just change `url: ` to `url: "yourUsername.github.io"`, making sure to include the quotation marks. Also change `heading: ` to the name of your website, again with quotation marks.

### Homepage

To change your homepage you can open `_includes/Homepage.html` again using Notepad or TextEdit. The homepage is written in HTML instead of markdown, however HTML is very simple, you shouldn't have any trouble editing it. HTML is based on 'tags' which describe the content being written. An opening tag looks like `<tag>` and a closing tag looks like `</tag>`. An opening tag can also have attributes like `<tag attribute="value">`So to create a paragraph we write `<p> The text of my paragraph goes here </p>`. To create a link we use `<a href="https://www.example.com">Link Text</a>` which will show up as [Link Text](https://www.example.com). You can also put tags inside tags like `<p> Welcome to my website about apples. You can click <a href="https://en.wikipedia.org/wiki/Apple">here</a> to learn what an apple is </p>`

The current homepage has a bit of more complex HTML, but don't worry about it too much. You're just going to edit the text inside the `<h1>`[[`<h1>` is short for level 1 header. `<h1>Text</h1>` is the equivalent of `# Text` in markdown, and `<h2>` for `## Text` and so on.::rsn]] tag on line 6. Right now it says "Hyper Garden" but you can change that to whatever you want, like the name of your site.

You can add some content between the `<div class="content">` and `</div>` tags. This is the page that will first display when someone opens your site, so you migth want to explain what the site is about and link to some parts of it. To add links to other parts of your site you don't need to write out the full URL, just add a forward slash at the beginning and write the subpath. For example if I want to link to my note about apples I would write `<a href="/notes/Apples">Click to see my note about apples</a>`

### Header

The Header, also called the navbar, is the box that shows up at the top of every page in a website with links to different sections of the website. On most sites it's a row at the top but in this theme it's offset to the left. If you want to change what links are included open `_includes/Header.html`. On lines 35-39 you should see a list of links. Change the URLs and text to what you need.

### Comments

Because this is a simple static site we need to use a third party to add commenting. There are several different choices.

By default this theme is set up to use [Cusdis](https://cusdis.com). Go to the Cusdis site and sign up for an account. From your dashboard add a new website. When you click on the website your url should be something like `https://cusdis.com/dashboard/project/[long string of numbers and letters]`. Copy just the end of the url, the string of numbers and letters, and open your `_config.yml` file. Paste it in quotation marks on line 58 after `cusdis_id: `. Now set `enabled: ` on line 57 to `true`. Cusdis comments can be sent anonymously and are manually approved before being shown on the site.

Cusdis is a free service and might shut down in the future. In that case you'll need to use an alternative such as [Commento](https://commento.io)($10/mo or $99/year) or [Disqus](https://disqus.com) (Free). Once you've signed up these services will give you a block of HTML code. Copy this code and open `_layouts/Post.html`. On line 102-118 you'll see this block of code

```HTML
103             <br>
104             <br>
105             <hr>
106             <h2>Comments</h2>
107             <div id="cusdis_thread"
108   data-host="https://cusdis.com"
109   data-app-id= "{{ site.preferences.comments.cusdis_id  }}"
110   data-page-id="{{ page.title }}"
111   data-page-url="{{ page.url }}"
112   data-page-title="{{ page.title }}"
113 ></div>
114 <script async defer src="https://cusdis.com/js/cusdis.es.js"></script>
115             { % - endif - % }
116
117                         </div>
```


(The numbers on the left are just line numbers, not part of the actual HTML code.)

Cut out everything from `<div id="cusdis thread">` to `</script>`

```HTML
102             { % - if site.preferences.comments.enabled and page.content-type != "post" - % }
103             <br>
104             <br>
105             <hr>
106             <h2>Comments</h2>
107             { % - endif - % }
108
109                         </div>
```

Now paste the code that you got from Commento or Disqus on a new line below `<h2>Comments</h2>`. 

Remember that If you use a comments script other than Cusdis you'll still need to enable comments in the \_config.yml

### Using a custom URL
- First you'll need to buy the domain name you want from a domain name registrar. [Cloudflare](https://www.cloudflare.com/products/registrar/) is good. Whatever you choose the price should be around $8-$15 a year. 
- Next open your repository on Github.com and go to settings > pages again. Add the domain name you purchased to the 'custom domain' box and save.
- This next step will vary depending on your registrar, but somewhere in the settings of the website you bought your domain from, possibly under a DNS tab, you should see the ability to create an AAAA record. Create a new AAAA record with the GitHub Pages IP addresses
```shell
2606:50c0:8000::153
2606:50c0:8001::153
2606:50c0:8002::153
2606:50c0:8003::153
```


## Creating Posts

### Posts and Notes
There are two types of pages you can create in this theme. 'Notes' and 'Posts'. A list of notes can be accessed from `yourURL.com/notes` and a list of posts from `yourURL.com/posts`. How you use these two types is up to you, personally I use 'posts' for standalone stuff that I plan to be continually updating, like a list of interesting links, and 'notes' for more finished writing. Some features, like backlinks, won't work for posts. 

To create a note use the YAML described earlier
```
---
title: Apples
notetype: feed
date: June 16th, 2022 
---
Apples are my favorite food.
```
notes should be made in the `_notes/Public` folder. If you want to write private notes create a `_notes/Private` folder. All notes that aren't in the private folder will be uploaded to github even if they aren't directly accessible on your website.

To create a post make a note in the `_posts/` folder with `notetype: post` and `title:`. Instead of adding the date in the YAML you'll need to add it to the beginning of the name of the file in the format `YYYY-MM-DD-title`. So an about page would be called `2022-05-16-about` and the frontmatter would look like
```
---
title: About this Site
notetype: post
---
This is a website
```


### Links

When linking to a note either from a post or from another note you can just use the title of the note between double brackets as you would in any Obsidian vault. To use alt-text use write `alt-text::title` again in between double brackets.

When linking to a post from a note you should use the regular markdown notation and use the absolute path of the URL of the article.  So if you want to link to a post located at `yourURL.com/posts/about` you write `[About](/posts/about)`. Make sure to include the leading `/`. 

### Sidenotes and Margin Notes

To create a margin note we use the same notation as an internal link with alt-text, but in place of the URL we indicate the type of note. E.g.
[[assets/img/Sidenote.png::ibw]]
places a sidenote on the left. 

The types of notes are as follows. Sidenotes have a number reference, margin notes do not.

|URL|Type|
|---|---|
|lsn| Left side note|
|rsn| Right side note|
|lmn| Left margin note|
|rmn| Right margin note|
|lmn-img| Left margin image|
|lmn-ibw| Left margin image invertible|
|lsn-img| Left sidenote image|
|lsn-ibw| Left sidenote image invertible|
|rmn-img| Right margin image|
|rmn-ibw| Right margin invertible|
|rsn-img| Right sidenote image|
|rsn-ibw| Right sidenote invertible|

Sidenotes that exceed 500 characters will automatically be made expandable and truncated to the first 50 words.

### Images and Assets

Images are currently a bit fussy. They're liable to break if you don't add them in a very particular way. Images and other assets should be saved in the `assets` folder. You can create subfolders, and by default Obsidian should save images to `assets/img/`. There are two notations to add an image. [[Make sure you don't accidentally link to `\_site/assets/img/ImageName.jpeg`::rmn]]

[[assets/img/images.png::ibw]]

The first one works better with Obsidian's autocomplete. I can type `[[Imag` + `Enter` and it will automatically fill in the rest of the file name. Make sure that in the Obsidian settings 'Files & Links' > 'New Link Format' is set to 'Shortest path when possible'. Unfortunately it doesn't render properly in Obsidian so you won't be able to preview your images in the document.

The second method works with both Obsidian and the website, but it requires you to manually type out the full file path. It is also the only method that will work for an external link.

Note that the default obsidian image notation of an exclamation mark before a double bracket link does not work. 

[[assets/img/defImage.png::ibw]]

As you can probably tell from the use of screenshots, backlash as an escape character also does not work as you would expect it to. The custom markdown needs to be handled in a somewhat hackish way so you'll need to watch out for edge cases whenever using it.

If an image is invertible you can use `url::ibw` instead of `url::img`. This will make it so that when dark mode is toggled the image will invert, which is useful for diagrams with white backgrounds. It will also adjust the white of the background to match the color of the background of the light mode theme, which is useful to avoid contrast from a true white next laid over an off-white. To achieve this affect for external images you need to add ?b&w to the end of the URL. 

### Misc
- In the YAML use `permalink: ` to assign a particular URL to a note. For example I have my about page located at `/about` instead of `/posts/about`
- use `mathjax: true` to enable MathJax LaTeX rendering.
- The \<mark\> tag will turn text inside red as a way of highlighting it.

