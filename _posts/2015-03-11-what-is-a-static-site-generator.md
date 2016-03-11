---
layout: post
title: What is a Static-site Generator?
description: Explaining what a static-site generator is and how it help speed up the development process.
comments: true
category: programming
---

A static-site generator is a tool which allows you to create websites locally and 
quickly using techniques like templating. Instead of writing all the code yourself, these
tools generate the bulk of it. It's quite handy when you want to get a small website up
and running quickly. I'll be using Jekyll as the main example to explain the several
features of static-site generators.

What's [Jekyll](https://jekyllrb.com/)?
==============

Well, it's a static-site generator! But more importantly, it's what was used to build
this blog. It's a generator that can create blogs very quickly and painlessly.
It converts [Markdown](https://daringfireball.net/projects/markdown/) into HTML and renders 
[Liquid](https://github.com/Shopify/liquid/wiki)
nomenclature. In the end, you'll end up writing something like this:

    ---
    layout: page
    title: "{blog}"
    ---
    <ul class="list-posts">
        {% for post in site.posts %}
            <li class="post-teaser">
                <a href="{{ post.url | prepend: site.baseurl }}">
                    <span class="post-teaser__title">{{ post.title }}</span>
                    <span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span>
                </a>
            </li>
        {% endfor %}
    </ul>

Figure 1.1

This is the source code for the front page of this blog. The bit inbetween the dashes at the
start of the code block is YAML front matter. It's processed by Jekyll as a special file and
helps streamline the entire website. The "layout: page" refers to another template in the 
_layouts folder that helps mark up this page and adds more HTML. The general idea is that the more specific and
unique a page becomes, the more layouts will be linked to it. In this case, this template is
linked to the page layout, which is linked to the default layout.

The "title: "{blog}"" allows me to easily assign titles to all my pages. Jekyll renders them
all as `<h1>`'s at the top of the page and CSS takes over from there.

The stuff between the `<ul>` tags is actually the Liquid template engine doing its magic and
looks like this:

    % for post in site.posts %
        <li class="post-teaser">
            <a href="{ post.url | prepend: site.baseurl }">
                <span class="post-teaser__title">{ post.title }</span>
                <span class="post-teaser__date">{ post.date | date: "%d %B %Y" }}</span>
            </a>
        </li>
    % endfor %

Figure 1.2

For some reason, the Liquid engine was still rendering this code even though it was put in
a code block in this post. I left out specific brackets in the code just so it wouldn't render (I figure
there's a better way to do this, but I'm still learning too ^__^). Anyhow, the rendered
version can be seen in Figure 1.1 and the unrendered version is just above.

Within the first line, you'll find a for loop that loops over the /posts folder. This is really handy, because it links every
post that has been written so far. This saves me from manually having
to insert all the links myself and updating constantly. Combine this with the YAML front matter and I can easily
give the user the option to view posts by date, category, or description without having to create another handful of HTML pages.

The `<a>` tag in the third line uses YAML front matter to create the link to the post. The site. prefix in the `<a>` tag refers to the _config.yml YAML file that contains revelant site information (like the url it's looking for).

Lastly, the `<span>` tags fetch the post's YAML front matter to access the title and date. And Presto! What you see in Figure 1.1 is the rendered code.

You	can view the rest of the source code for the blog [here](https://github.com/dvrico/dvrico.github.io).

A Few More Benefits
===================

As you can see, getting a website up and running quickly is possible with Jekyll and
its templating system. The great thing is that Jekyll renders all of this into HTML.
This serves as a benefit because pure HTML will always load faster than any server-side 
HTML generator.

Other cool features that Jekyll has includes:

*   <p>A nifty local server to test and debug without having to push to your live site to see 
    each change.</p>
*   <p>Templates are generated in Jekyll, so no need for a database or CMS.</p>
*   <p>Speeds up the development process with templating and Liquid code (keep the code DRY!)</p>

Anyway, getting off the Jekyll train, here's a [reference](https://www.staticgen.com/) for
the top open source static-site generators. Happy coding! 

