<p align="center" style="margin-bottom: 0;">
  <a href="https://github.com/doncabreraphone/victorhugo/">
    <img src="https://raw.githubusercontent.com/doncabreraphone/victorhugo/master/misc/victorhugo__logo.png" alt="Victor Hugo logo" width="260" height="254" style="margin-bottom: -10px;">
  </a>
</p>

<p align="center" style="margin:0 ; padding: 0;">
<img src="https://raw.githubusercontent.com/doncabreraphone/victorhugo/8946bd99f351d6c35b643eda497d0b21b1537a48/misc/vh_font.svg">
</p>

<p align="center">
  The first and only search engine optimization plug-in for the Hugo static site generator framework.<br>Victor Hugo helps you write good SEO content, the easy way.
  <br>
  <br>
  <a href="https://github.com/doncabreraphone/victorhugo/issues">Report bug</a>
    ·
  <a href="https://github.com/doncabreraphone/victorhugo/blob/master/misc/hugo-seo-snippets.md">Seo Snippets</a>
    ·
  <a href="#say-thanks">Say Thanks</a>
  
</p>

 <!-- <video style="width:100%; margin: 15px 0;" controls>
  <source src="https://i.imgur.com/2o0sjKY.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>  -->

## Overview

Victor Hugo is a SEO plugin for <a href="https://gohugo.io/">Hugo</a>, the world’s fastest framework for building websites. It audits your content as you write it and gives you an estimate based on best SEO practices, so you can improve your SERP (Search Engine Results Pages).

**Victor Hugo uses no browser extensions, no external services, no installs. It lives in a simple partial. One line of code and you are ready to write SEO-friendly content.**

<p style="text-align:center;border:1px solid #ccc;border-radius:4px;margin:6px 0;">
<img src="https://github.com/doncabreraphone/victorhugo/blob/master/misc/victorhugo_readme_img.jpg">
</p>

When writing a blog post, Victor Hugo will:
* Check for stop words in your page slug.
* Check for passive voice in your copy.
* Make sure you optimize your content for google and other search engines by using a keyword/keyphrase of your choosing.
* Help you write SEO friendly meta descriptions
* Run your copy through an included version of the <a href="https://en.wikipedia.org/wiki/Flesch%E2%80%93Kincaid_readability_tests" target="_blank">Flesch Reading Ease Test</a>, and give you an easy-to-read score.

...and more, much more, right in your browser, without having to subscribe to any extra tool. 

With Victor Hugo, you will write optimized SEO content from the get-go, so you don't have to do it later when your blog post is already online.


## Install

Being a Hugo partial template, **Victor Hugo is prepared to work with any Hugo theme**. Besides jQuery, Victor Hugo has no other dependencies; it makes no server-side calls, it doesn't run anything funny on the backend nor needs a database. 

In fact, with Victor Hugo, you only need one file: 

``
victorhugo.html
``

This file contains **everything you need** to run Victor Hugo in your project. <a href="https://github.com/doncabreraphone/victorhugo/releases/tag/v1.0-beta">Download the release</a>.

### Dependencies

Victor Hugo needs jQuery installed, but don't despair: if you don't have a jQuery version installed in your Theme Victor Hugo makes a call to the latest version from the official jQuery CDN and uses that one to work its magic. That means that, **if your Theme doesn't use jQuery, then you don't have to install it just to use Victor Hugo**.

On the other hand, if you use jQuery and don't want Victor Hugo using the official CDN, you can easily configure it not to do so.

### Safety First Approach
Thanks to the **.IsServer** directive, Victor Hugo will **never, ever get built into the public directory of your project**. The '.IsServer' directive makes sure Victor Hugo gets executed only when you are in Hugo's local built-in server.

You will never see a trace of Victor Hugo in your public folder and, since it is a standard Hugo partial template like any other, you can remove it anytime you want from your project by deleting it. 

## Getting Started
To use Victor Hugo, all you have to do is:
1. Place the **victorhugo.html** partial under your ``layouts/partials`` folder.
2. Call it with ``{{ partial "victorhugo.html" . }}`` somewhere before the ``</head>`` tag of your _article_ or _single page_ template.

That's about it. Simple, isn't it?

### Configure Victor Hugo
You need to add these two Params in the _front matter_ of any post you want Victor Hugo to run SEO checks.

```
Victor_Hugo: "true"
Focus_Keyword: ""
```

**VictorHugo:** accepts true or false. Without this Param, Victor Hugo won't work.

**Focus_Keyword:** the word or phrase Victor Hugo will use to run a check on your copy—including the SEO title, H1 tag, body copy, and images. This is the keyword or phrase that you want your post to be found for in search engines. Victor Hugo will let you know how well you have optimized your copy for this keyword or phrase.

### Examples
```
Focus_Keyword: "Yoast Plugin for WordPress"
```
Another example:
```
Focus_Keyword: "Free Bundle Magazine"
```
One more:
```
Focus_Keyword: "Writing Github Documentation"
```
Last one, proimise:
```
Focus_Keyword: "Gladiator"
```

Victor Hugo will help you write content that ranks with your Focus Keyword or Focus Keyphrase in mind.

That's it, you can now start using Victor Hugo and ranking like a champ!

## Say thanks
This plugin was put together by someone who doesn't code, at all. I am fiction writer, so those purists of you will excuse the clumsiness of my code. I put this project together in less than 48hs and had no time to go clean about it.

It is what it is. 

If you want to contribute to this project, by all means, feel free to do so from the Issues tab. 

If you feel like saying thanks, be a sport, buy one of my books:

* https://javiercabrerabooks.com/

Or subscribe / spread the word about **Free Bundle Magazine**, a Fantasy & Sci-Fi magazine I edit along with some very intersting people.

* https://thefreebundle.com/

You can also send me a Twitter message and more from here:

* https://t.co/ouXDeMGfcj?amp=1

Incidentally, I am also a game developer:

* https://cabrerabrothers.com/


## Status
<!-- https://shields.io/category/analysis -->
[![GitHub license](https://img.shields.io/github/license/doncabreraphone/victorhugo)](https://github.com/doncabreraphone/victorhugo/blob/master/LICENSE)



## License

Code and documentation under GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007. Read the LICENSE file included in this repository for the complete version.







