# GigaSpaces XAP Documentation

This repository contains the markup files, html templates and javascript sources for the new [GigaSpaces XAP documentation portal](http://wiki.gigaspaces.com.s3-website-us-east-1.amazonaws.com). 
It's based on [Jekyll](http://jekyllrb.com/), a Ruby-based static site generator, and uses [Markdown]() as a markup language. It was originally ported from Atlassian Confluence, and therefore multiple useful Jekyll [plugins](#available-plugins) were defined. The plugins mimic the behavior of original Confluene macros to allow for easy migration from Confulence and provide content editor with useful markup extensions that are relevant to online documentation portals. 

## Help Us Improve! 
It's important for us to encourage your feedback and contribution. Contributing to this website is straightforward. Simply fork this repository, make your changes, test them with your locak Jekyll installation, and submit a pull request. We promise to review and comment on every pull request, and merge it if it makes sense.  

## Installing, Editing and Testing Locally 
To run and test the website locally, you should perform the following steps: 
* Install the latest version of Jekyll (you can find detailed directions [here](http://jekyllrb.com/docs/installation/)).
* If you intend to edit the docs, create a fork of this repo and clone it to your machine. 
```
git clone https://github.com/&lt;your github username&gt;/gigaspaces-wiki-jekyll.git
```

If you just want to run it locally, you can clone this repository: 
```
git clone https://github.com/Gigaspaces/gigaspaces-wiki-jekyll.git
```

* cd to the clone directory: 
```
cd gigaspaces-wiki-jekyll
```

* Make the required changes to the docs (if you need to).

* Run Jekyll in sever mode, and wait for the site generation to complete: 
```
jekyll serve
```
You should see the following output if everything was ok: 
```
Configuration file: /Users/uri1803/dev/gigaspaces-wiki-jekyll/_config.yml
            Source: /Users/uri1803/dev/gigaspaces-wiki-jekyll
       Destination: /Users/uri1803/dev/gigaspaces-wiki-jekyll/_site
      Generating... done.
    Server address: http://0.0.0.0:4000
  Server running... press ctrl-c to stop.
```

* Point your browser to [http://localhost:4000](). You should see the documentation portal home page, and verify that you're ok with your changes. 

* If you've forked the repository and updated documentation pages, you can submit a pull request. We will review, comment and merge the pull request after approving it. 

## Continuous Deployment 

This website is hosted on AWS S3. Every push to this reposiroty triggers a build process (currently we use the excellent [Circle CI](http://circleci.com) conitnuous integration service), at the end which the generated website is pushed to S3 using the [s3_website](https://github.com/laurilehmijoki/s3_website) library. The Circle CI configuration is located at in the file [`circle.yml`](circle.yml). 

## Authoring Guidelines 

* We use [Markdown](http://daringfireball.net/projects/markdown) as markup language for all the documentation pages. Please refer to [the markdown syntax guide](http://daringfireball.net/projects/markdown/syntax) for more details. That also means that all files should have the `.markdown` extension. 

* All pages should start with a [yaml front matter](http://jekyllrb.com/docs/frontmatter/), which basically looks like this (See one of the existing pages under xap97 or xap97net for a full example):

```
---
layout: post
title:  About Jini
...
---
```

 * `layout` refers to the page layout, which essentially determins the HTML elemenets that wrap the page content. The appropriate layout for every documentation page is `post`. 
 * `title` is the page title, as will appear in the page itself and the table of contents. 
 You don't need to refer to other elements if such exist. 

* XAP versions: each XAP version is placed under its own directory. For example, XAP 9.7 is placed under `xap97` and XAP.NET 9.7 is placed under `xap97net`. 

* Images and other attached files: all images should placed under the directory `attachement_files`. Images and files that are shared between version should be placed at the root of this folder, images specific to a certain version (that you don't expect to be relevant to future versions) should be placed under a directory that has the same name (e.g. `xap97`). 

* Special markup helpers (summary section, documentation links, code blocks, tabbed views, tips, info box, warning box, etc.) are described [below](#available-markup-helpers-jekyll-plugins). 

* Tables can be created using the following syntax: 

```
{: .table .table-bordered}
|Header1|Header2|Header3|
|:------|:------|:------|
|value1 |value2 |very long value in my table|
```
* HTML snippets: Markdown supports direct HTML injection, so you can always embed a complete html snippet to the page in case there's some formatting, markup or element that is not supported (e.g. embedding a slideshare deck). 

## Available Markup Helpers (Jekyll Plugins) 

The following table contains a list of available plugins and simple example for how to use each within markdown files. This is not an exhaustive list and contains only the main and most commonly used plugins, the entire set of plugins can be found in the [`_plugins`](_plugins) directory, and usage samples for all plugins can be found within the documentation pages. 

* `align`

* `anchor`

* `bgcolor`

* `children`

* `cloack`

* `color`

* `comment`

* `currentversion`

* `dotnetdoc`

* `exclamation`

* `fontsize`

* `indent`

* `info`

* `infosign`

* `javadoc`

* `lampoff`

* `latestxaprelease`

* `lampon`

* `learn`

* `lozenge`

* `minus`

* `next`

* `note`

* `oksign`

* `panel`

* `plus`

* `question`

* `quote`

* `redirect`

* `refer`

* `remove`

* `scaladoc`

* `section`

* `star`

* `summary`
Creates a summary section at the top of the page. The section will include the text in the markup help, and shotcut links to all h1 titles in the page (every title which is prefixed by a single `#` sign). 

 * __Usage__:   
```
{% summary %}This is a page summary.{% endsummary %}
```
 * __Parameters__: None

* `tabs`

* `tip`

* `warning`

* `wbr`

* `whr`













