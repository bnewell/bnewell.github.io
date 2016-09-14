---
layout: post
title: Markdown helps you KISS
---
Writing articles and blog posts has never been so easy. Using the markup language "Markdown", I'm able to write structured articles using a few simple annotations without having to worry about any formatting or closing tags.

I think I may have been one of the last people on Earth still writing articles directly in HTML. I knew it was inefficient but I wanted that control that writing HTML gives you. And it does give you absolute control, but it is also absolutely time consuming. 

Markdown is nothing new. It's been around for a little over 10 years but it wasn't until I switched to Jekyll a few days ago that I realized how convenient it *really* is. I have previous experience using Markdown through Github, Reddit, and a few other sites, but until now it was just a nuisance. 

After spending some time formatting various pages and posts on my new blog it finally clicked. Markdown is much faster to write simply because you don't have to worry about formatting and matching up tags.

For example, I wrote my [Is Diet Coke Bad For You?](http://www.relabit.com/diet-coke.html) directly in HTML. This is what the ingredients list looks like in HTML:

{% highlight html %}
<p>
    <ul>
	    <li>Carbonated water</li>
		<li>Caramel Color</li>
		<li>Aspartame
		<li>Phosphoric Acid</li>
		<li>Potassium Benzoate</li>
		<li>Caffeine</li> 
		<li>Citric Acid</li> 
		<li>Natural Flavor</li>
	</ul>
</p>
{% endhighlight %}

Which looks like this when rendered through a browser:

* Carbonated water
* Caramel Color	
* Aspartame		
* Phosphoric Acid	
* Potassium Benzoate
* Caffeine
* Citric Acid
* Natural Flavor

A unordered list in HTML uses a lot of tags for something so simple, doesn't it? Now let's look at the same list in Markdown:

{% highlight markdown %}
* Carbonated water
* Caramel Color	
* Aspartame		
* Phosphoric Acid	
* Potassium Benzoate
* Caffeine
* Citric Acid
* Natural Flavor
{% endhighlight %}

This Markdown renders exactly the same list as the HTML above and it used 131 less characters to do it. If you apply this over an entire article, it's clear that an enormous amount of time can be saved by writing in Markdown.

I'm a little ashamed and embarrassed that it took me this long to realize how convenient blogging in Markdown can be. But I guess I should be happy with my new found speed and blogging power. In the future I will do better and adopt simple solutions sooner. Markdown really does make you KISS (Keep It Simple Stupid) better.

Also, if you got this far and are also still writing articles in HTML, then I highly recommend switching over to Markdown. There are a bunch free online tools that will convert your Markdown in realtime to help you visualize and learn the tags quickly. One of the converters I've used with success is [Dillinger](http://dillinger.io).
