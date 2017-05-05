# Brown Institute Project Template

This showcase template was created to help Magic Grantees prepare for the Brown Institute fall showcase, and have a basic project website to document their project and process. The template is made from Jekyll, and is a modified version of the popular Hyde template.

In this README, we'll go through the process of setting up, editing and customizing this template for your project.

### Join our organization on Github

Before you get started, you'll need to make sure you are part of our team on Github. The Brown Institute has a [Github organization](https://github.com/browninstitute) where we will host the code for your showcase website. 

We will be granting you access to this organization, but if we have not added you yet, make sure you contact us for access.


### Set up the template

In order to use the template, go through the following steps.

1. Clone the repo

    Open a terminal window.
    
    On your command line, navigate to a folder where you'd like this project to live. If you want it to live in `Documents/BrownInstitute` then just type `cd Documents/BrownInstitute` on the command line then press `return`.

    Then, close the repository by pasting `git clone https://github.com/browninstitute/showcase-template.git` on your command line and pressing enter.
    
    Navigate into the cloned directory with `cd showcase-template`.
    
    Leave the terminal window open.

2. Create a new repository for your site within the Brown Institute's Github organization

    Go to our Github homepage at `https://github.com/browninstitute` and press the green `New` button on the right side of the screen.
    
    Name your repository with a hyphenated schema of `name of project` + `showcase` + `year`. So if we were making a repo for Open Contractors for the 2016 showcase, it would look like `open-contractors-showcase-2016`
    
    Make sure the repository will be public.
    
    Do *not* select `Initialize this repository with a README`
    
    Press `Create repository`
    
3. Add the template your new git respository

    Once you have initialized the repository, Github will provide you a repository link, like `https://github.com/browninstitute/open-contractors-showcase-2016.git`
    
    Go back to your terminal window. Copy and paste the following and press `return`.
    
    `git remote set-url https://github.com/browninstitute/YOUR-REPOSITORY-NAME`
    
    Now, add your files. On your command line:
      
      1. `git add .`
      
      2. `git commit -m 'adding files'`
      
      3. `git push origin master`
      
At this point all of your files should be added to your repository on Github. To make a visitable webpage out of this code, go to the `Settings` tab in your repository. Scroll down. Under the heading `Github pages` select `Master branch` under the dropdown menu and press `Save`. 

Wait a minute, then navigate to `browninstitute.github.io/YOUR-REPOSITORY-NAME` and a webpage should be there.
    
    





Hyde is a brazen two-column [Jekyll](http://jekyllrb.com) theme that pairs a prominent sidebar with uncomplicated content. It's based on [Poole](http://getpoole.com), the Jekyll butler.

![Hyde screenshot](https://f.cloud.github.com/assets/98681/1831228/42af6c6a-7384-11e3-98fb-e0b923ee0468.png)


## Contents

- [Usage](#usage)
- [Options](#options)
  - [Sidebar menu](#sidebar-menu)
  - [Sticky sidebar content](#sticky-sidebar-content)
  - [Themes](#themes)
  - [Reverse layout](#reverse-layout)
- [Development](#development)
- [Author](#author)
- [License](#license)


## Usage

Hyde is a theme built on top of [Poole](https://github.com/poole/poole), which provides a fully furnished Jekyll setup—just download and start the Jekyll server. See [the Poole usage guidelines](https://github.com/poole/poole#usage) for how to install and use Jekyll.


## Options

Hyde includes some customizable options, typically applied via classes on the `<body>` element.


### Sidebar menu

Create a list of nav links in the sidebar by assigning each Jekyll page the correct layout in the page's [front-matter](http://jekyllrb.com/docs/frontmatter/).

```
---
layout: page
title: About
---
```

**Why require a specific layout?** Jekyll will return *all* pages, including the `atom.xml`, and with an alphabetical sort order. To ensure the first link is *Home*, we exclude the `index.html` page from this list by specifying the `page` layout.


### Sticky sidebar content

By default Hyde ships with a sidebar that affixes it's content to the bottom of the sidebar. You can optionally disable this by removing the `.sidebar-sticky` class from the sidebar's `.container`. Sidebar content will then normally flow from top to bottom.

```html
<!-- Default sidebar -->
<div class="sidebar">
  <div class="container sidebar-sticky">
    ...
  </div>
</div>

<!-- Modified sidebar -->
<div class="sidebar">
  <div class="container">
    ...
  </div>
</div>
```


### Themes

Hyde ships with eight optional themes based on the [base16 color scheme](https://github.com/chriskempson/base16). Apply a theme to change the color scheme (mostly applies to sidebar and links).

![Hyde in red](https://f.cloud.github.com/assets/98681/1831229/42b0b354-7384-11e3-8462-31b8df193fe5.png)

There are eight themes available at this time.

![Hyde theme classes](https://f.cloud.github.com/assets/98681/1817044/e5b0ec06-6f68-11e3-83d7-acd1942797a1.png)

To use a theme, add anyone of the available theme classes to the `<body>` element in the `default.html` layout, like so:

```html
<body class="theme-base-08">
  ...
</body>
```

To create your own theme, look to the Themes section of [included CSS file](https://github.com/poole/hyde/blob/master/public/css/hyde.css). Copy any existing theme (they're only a few lines of CSS), rename it, and change the provided colors.

### Reverse layout

![Hyde with reverse layout](https://f.cloud.github.com/assets/98681/1831230/42b0d3ac-7384-11e3-8d54-2065afd03f9e.png)

Hyde's page orientation can be reversed with a single class.

```html
<body class="layout-reverse">
  ...
</body>
```


## Development

Hyde has two branches, but only one is used for active development.

- `master` for development.  **All pull requests should be submitted against `master`.**
- `gh-pages` for our hosted site, which includes our analytics tracking code. **Please avoid using this branch.**


## Author

**Mark Otto**
- <https://github.com/mdo>
- <https://twitter.com/mdo>


## License

Open sourced under the [MIT license](LICENSE.md).

<3
