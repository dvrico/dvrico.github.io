
Goal: To explain static-site generation using Jekyll as the example.

Key points I want to cover:
===========================

* Define Jekyll
* Explain what Jekyll can do (generate web pages)
* Explain the generation of web pages via bad analogy
* Compare Jekyll to other frameworks like Express and Flask/Django
* Wrap up with the moral of the story: learning general underlying principles
is useful to web development as it lets you pick up various technologies quickly. 

What is a static-site generator?

Consider the printing-press. It was a machine so revolutionary that historians
agree that it ushered in the age of modernity.(some more stuff?)

Aside from the awesomeness of the printing press, I wanted to try and make a bad
analogy between it and static-site generation. I figured I'd use Jekyll as the
main example because this blog was built using Jekyll, and it's a pretty 
awesome static-site generator.

Static-site generation is like the printing press because it affords more content
in less time. It's simply more efficient.

Why? Because of templates. If you're familiar with coding web pages manually, you've
definitely experienced how long it take. Writing and rewriting html may have proved
useful in the classroom, but it soon became a pain to do when you wanted up
and running quickly. CSS already has a sort of 'generator' built into it with the ability
for you to link muliple pages to it. You only have to write one CSS file. Why, then
should you write so many HTML files?

Enter the static-site generator. Or more specifically, Jekyll. Write up a generic HTML
template, describing what features each page will have, write up some code in the middle
of the template, and presto!, Jekyll injects your posts in the middle of the template.
All you have to do is focus on the content.

Jekyll uses YAML front matter block to set pre-defined variables at the beginning of your
files so you can set up a lot redundant elements on the page. For example, the titles of all
the posts on this site are located in the front-matter. Jekyll takes these titles and displays
them as h1's where appropiate. All my files are no more than a handful lines long. You can 
see the source [here](https://github.io/dvrico)(?).

Now this is slightly different than generating dynamic pages via server-side code, because
Jekyll renders all of this into HTML. This serves as a benefit because pure HTML will always
load faster than any server-side HTML generator.

Other cool features that Jekyll has:
    * Nifty local server to test and debug without having to push to your live site to see 
    each change.
    * Templates are generated in Jekyll, so no need for a database or CMS.
    *Speeds up the development process with templating and Liquid code (keep the code DRY!)

The top open-source static-site generators can be find [here](https://www.staticgen.com/).




