---
layout: post
title: Reading Mr. Money Mustach The Mustachian Way
excerpt_separator: <!--more-->
---
"Imagine that you are floating comfortably above an alien planet observing the really insane species that lives there. 
We’ll call these beings Sheeple, because their incredible tendency to follow the herd even if it is running right off a 
cliff is quite similar to the behavior we see in sheep here on Earth. Almost everything an individual of this species 
does is heavily influenced by the Sheeple around it. Despite the potential for incredible intelligence, they rarely 
stop to evaluate why they are doing what they do each day." - Mr. Money Mustache
<!--more--> 

As I was reading all of the incredible ways to save money on Mr. Money Mustache's blog a realization hit my thinky 
thing like a tuple of bits. Why am I using my own valuable bandwidth to read these articles when I could be using 
someone else's?

After intense and extremely precise calculations I realized I was using at least 1MB of bandwidth per blog post. 
If I read a thousand Mr. Money Mustache blog posts in total, that's a whopping 1GB of valuable bandwidth I've used. 
It would not be very Mustachian of me to not consider bits spent while subsequently reading about my cents spent. 

So I did what any devout Mustachian would do and wrote a PHP script to run on an online PHP sandbox. The script 
retrieves all of the blog posts from the Mr. Money Mustache site and spits them out in chronological order. 

{% highlight php %}
<?php
require "simple_html_dom.php";

function getPost($postURL){
	$post = $postURL;
	$html = file_get_html($post);
	$postTitle = $html->find('h1.headline');
	$postContent = $html->find('div.post_content');
	return $postTitle[0] . '<br />' . $postContent[0] . '<br />';
}
$html = file_get_html("http://www.mrmoneymustache.com/all-the-posts-since-the-beginning-of-time/");
$allPosts = array();
foreach($html->find('ul.history') as $ul){
	foreach($ul->find("li") as $li){
		foreach($li->find('a') as $link){
			$allPosts[] = $link->href;
		} 
	}
}
echo '*** Found ' . count($allPosts) . ' blog posts. ***';
$firstFew = array_slice(array_reverse($allPosts), 0, 5);
foreach($firstFew as $post){
	$contents = getPost($post);
	echo $contents;
}
?>
{% endhighlight %}

Because it runs on the PHP sandbox server, using their bandwidth to retrieve the blog posts instead of my own, 
I end up saving quite a few bits. It's absolutely ingenious and I'm certain I'll be a retired millionaire any day now. 

![PHPFiddle Home Bandwidth](/assets/money-mustache/phpFiddleHome.png "PHPFiddle Home Bandwidth")  
 
 
The PHP sandbox I'm using is [PHPFiddle](http://www.phpfiddle.org) and it takes approximately 400KB to load the homescreen. 
It takes another 500KB to get the results from the script. So we'll be extremely precise and say it's 1MB total to execute 
the script on PHPFiddle and get the results we want. So the total amount of bandwidth we save is $$1GB - 1MB = 999MB$$. 
That's almost a whole gigabyte saved!

![PHPFiddle Money Mustache](/assets/money-mustache/phpFiddleResult.png "PHPFiddle Money Mustache Results")  

Comcast Xfinity has a data cap of 200GB, so that saves $$\frac{1}{200}$$ of my bandwidth. By not actually loading the 
Mr. Money Mustache blog myself, I am saving roughly 10 cents per month. If I invest this money with an interest rate of 
7% compounded yearly over 10 years, I can save $19.67! 

$$A = P(1 + {\frac{r}{n}})^{nt}$$ 
 
$$A = .10(1+{\frac{.07}{1}})^{(1)(10)}$$ 
 
$$A = 19.67$$ 

 That's almost $20 whole real dollars saved over 10 years. I can smell the yacht already... I mean, uh, the savings.. yea.. the savings. 
 And retirement.

*This was a parody article written for the sole purpose of entertainment. It is neither accurate nor honest. 
Please visit [Mr. Money Mustach's blog](http://www.mrmoneymustach.com) if you want to read all of his excellent 
advice on saving. It really is invaluable.*
