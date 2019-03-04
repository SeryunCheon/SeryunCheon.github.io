---
layout: post
Eng: true
title:  "Eng vid) Cleaning & Organizing My Life Together 😀 Self Care Routine-ish(Youtube)"
date:   2019-03-04
excerpt: "A youtube video from Rowena Tsai(Daily v-log's youtuber)
"
tag:
 - EnglishVideo
 - DailyVlog
 - 딕테이션&필사
comments: true
---
<iframe width="560" height="315" src="//www.youtube.com/embed/sDzNkWIqvww" frameborder="0"> </iframe>

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

Not sure if this only effects Kramdown or if it's an issue with Markdown in general. But adding YouTube video embeds causes errors when building your Jekyll site. To fix add a space between the `<iframe>` tags and remove `allowfullscreen`. Example below:

{% highlight html %}
<iframe width="560" height="315" src="//www.youtube.com/embed/SU3kYxJmWuQ" frameborder="0"> </iframe>
{% endhighlight %}
