---
layout: post
title:  How To Make My Website
date: 2016-01-11
categories: technology
author: Adam Bodie
image: lincoln.jpg
alt: Making websites is fun!
intro: "After the official launch of Bodie Web Design 2.0 (as I call it), I received a lot of nice compliments from those who checked it.  Thank you all for your nice words.  One comment from my wonderful Auntie Sheri was that she loved it, and that she could make this web page too.  So with those comments, here is how I made Bodie Web Design 2 and how you could too."
---

<div class="article">
<p>{{page.intro}}</p>

<div class="blog-pic">
		<img src="/img/lincoln.jpg" data-toggle="tooltip" title="Making websites is fun!" class="image block img-responsive">
	<h4>Making websites is fun!</h4>
</div>

<p>First up is the prerequisites programs needed to run the website.  Node.js, the popular server-side JavaScript runtime environment, is used here.  Everything that runs my website is setup through a few lines of code that Node.js interprets and runs the code.</p>

<p>Another program needed is closely associated with Node.js, which is NPM, it's package manager.  Once this is downloaded, you can access all the dependencies needed for your website, whether it be the use of a templating language such as Jade, or a task-runner like Gulp which can manage your tasks so they are easier to perform than manually doing it yourself.</p>

<p>Once NPM is installed, now you can download the Express package, which is the framework I used for making this site.  You can either install it manually or use Express-Generator (the easier way) which creates a skeleton of your project.  </p>

<p>Now that all the prerequisites are installed, you can actually start working on your project.  The first thing to do is to set up your routes.  This is important as it tells your program which page to go and what to do when you reach that page.  Start by using express itself, which can be done by setting a variable, like so:  var express = require('express');.  Now you can use express and all its methods, primarily the express method.  Set another variable equal to this method like so: var app = express();.  Now you can use the get() method to set your routes, which takes two parameters, the route it's going to as the first, and an anonymous function as the second parameter, which contains everything that route is supposed to have.</p>

<p>After the routing is done, you can start working on your templates, which consists of the views to be used.  With Jade, you can you partial templates, extend other templates into templates, all in accordance to DRY (Don't Repeat Yourself).  Of course, to use Jade, you can use the app.set() method to set the view engine as Jade (view engine is the first parameter, jade is the second).  Now it's ready to use, whether you want to extend the main layout template, or include a partial template not meant to be used by itself.</p>

<p>Now you can add all of your static files; images, CSS, JavaScript, jQuery plugins, etc. Like everything else, it needs to be added to the main js file that keeps all of our basic in's and out's for our web page.  Not surprisingly, you can't use static files until it's set up in the main js file, which the app.use() method is also used for, which contains the express.static() method as its second parameter that sets the path to the static files.</p>

<p>Install any other dependencies needed.  I used Gulp, a task runner which let me set my own tasks to make certain parts of development easier.  For example, minifying your JavaScript code, which makes it smaller and easier to run, can be a pain to do manually, but with Gulp, all I have to do is run a task and it will automatically minify the file and place it into the correct folder based on the task.</p>

<p>When you're done with the web page, you can upload it on-line to get it up in the real-life world of the Internet.  I chose Amazon Web Services to upload my project, using  Elastic Beanstalk to upload and manage my web application.  After getting your project uploaded to GitHub, a new Beanstalk project needs to be created and configured for Express.  Once that is done, deploy your GitHub zip file that is compiled with your most recent commit to your repository, and your website is up and running like mine is!</p>
</div>