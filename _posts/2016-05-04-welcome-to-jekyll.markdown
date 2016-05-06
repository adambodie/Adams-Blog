---
layout: post
title:  "Welcome to Adam's Blog 2.0 - The Rise of Jekyll"
date:   2016-05-04
categories: jekyll update
author: Adam Bodie
permalink: welcome-to-adams-blog-2
image: mthood.jpg
alt: Adam's Blog
intro: "Learning new ways to make blog posts or any developing tools in general is something I have always enjoyed.  It's something encouraged by IBM, the parent company I work for.  With that said, I am revamping my blog post as its own entity, rather than part of the Express framework I'm using for Bodie Web Design."
---
<div class="article">
<div class="blog-pic" style="float: left">
		<img src="/img/mthood.jpg" data-toggle="tooltip" title="Mt. Hood" class="image block img-responsive">
		<h4>Mt. Hood</h4>
</div>
<p>{{page.intro}}</p>

<p>What are the advantages of doing this, you ask?  Let me explain the ways to you in the most simplistic ways.  This new blog engine is powered by Jekyll, a static website generator powered by Ruby.  With it, I have more flexibility as to how I can layout my blog.  Gone are the days of sticking to one layout as I have been doing with my Jade-JSON backed blog posts.  Now I can use markdown files, which translates raw text to HTML.  For example, I would have to make parse my blogs with JSON, like in the first example below, then would retrieve those values with the Jade templating language, as seen in the second example below to convert them into html.</p>

{% highlight javascript %}
{
	"Example": {
        "title": "Example",
        "date": "May 4, 2016",
        "description": [{
                "paragraph": "Hello World, I'm a paragraph in JSON!"
            }, {
                "paragraph": "Hi Foobar, I'm another paragraph in JSON!"
            }
        ],
        "image": [{
                "name": "/img/image.jpg",
                "caption": "I'm a caption!"
            }]
    }
}
{% endhighlight %}

{% highlight jade %}
.article
	- for (var x = 0; x < post.description.length; x++)
   - var y = x / 3       
   	if post.description[x].paragraph !== undefined
      	p #{post.description[x].paragraph}
      	p I'm Jade!
         
{% endhighlight %}

<p>Though this got me thinking code and algorithms, it also limited my flexibility, having to follow a set pattern for each post I made.  Not to mention the quotation marks for each piece of JSON code.  Enough to drive you mad.  JSON is easier to read than XML, but the quotation marks are maddening.  But with Jekyll, I can make my posts with pure raw text in markdown files, which are converted to HTML.  Now I can have the freedom to add additional content in my posts without having to write code in the html files being outputed from the markdown files.  Want to add a random h4 header?  All I got to do is this:</p>
<h4> I'm an H4 header </h4>

<p> Want to make an H4 header green, I can do this:</p>
<h4 style="color: green"> Now I'm a green H4 header</h4>
<p> And all I did was add html to my markdown file, rather than make some funky rule in my Jade Template to apply for one instance, check this out:</p>
{% highlight html %}
<h4 style="color: green"> Now I'm a green H4 header</h4>   
{% endhighlight %}
<p>Another big change you'll see right off the bat is that my blog is now paginated.  Instead of everything on one page, it is now broken off to 10 posts per page.  At the time of this post, that's 4 pages of blog posts.  Much easier to navigate, less code to load, and a better, faster experience.</p>
<p>The possibilites are endless with Jekyll, and expect to see more power with my blogs and posts.</p>
</div>