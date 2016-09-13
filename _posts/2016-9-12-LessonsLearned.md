---
layout: post
title: Under Construction
---

If you are seeing this, then I apologize. I am in the process of migrating relabit to a static-site and got a little ahead myself. I don't expect many visitors during this time, but sometimes things happen and now you are here... The content will be restored shortly.

TEst

{% highlight ruby %}
def show
  @widget = Widget(params[:id])
  respond_to do |format|
    format.html # show.html.erb
    format.json { render json: @widget }
  end
end
{% endhighlight %}
