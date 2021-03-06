---
layout: post_ak
title: "Reading: Statistical Analyses and Reproducible Research"
root: "../../../../"
comments: true
---
As part of the course [Stat 585X](http://dicook.github.io/stat585/) I am taking this semester, I will be posting a series of responses to assigned course readings. Mostly these will be my rambling thoughts as I skim papers.

****
This week we are reading ["Statistical Analyses and Reproducible Research"](http://biostats.bepress.com/bioconductor/paper2/) by Robert Gentleman and Duncan Temple Lang, a working paper for the Bioconductor Project from 2004. This paper introduces the fundamental ideas behind reproducible research and lays out the logic behind why it is so important. 

On a personal note, I truly enjoyed reading this paper. It reminded me of a dark time in my life, before I knew of the wonders of [knitr](http://yihui.name/knitr), and just how far my workflow has come.

### Compendium com**pandemonium**!
Gentleman and Temple Lang introduce the concept of a *compendium*, which is used as a container for elements that generate various different views or outputs such as a PDF document, code, or graphics. An easy way to think of this is as a master document that holds everything and can be used to create many different things. That's kind of vague, so an example is the document I wrote to create this blog post. In it, there are my words and any code I may choose to include in this post. Using a *transformation* software (**knitr**) I am able to make a markdown file. Alternatively I could create an HTML file. I could even make a LaTeX file if I wanted to and from there create a PDF. The options are vast, and they all stem from this one file, my *compendium*. 

### So what? I like CTRL-C and CTRL-V.
Said no one, ever. Using a dynamic document, like the proposed *compendium* removes the need to copy and paste results into a paper. It saves time and limits the amount of user error in creation of documents. Not only does a dynamic document help the document creater, but it can help the reader as well. By placing all the underlying code inside a document, the content becomes **reproducible**. This concept of **reproducible research** stems from a suggestion by Buckheit and Donoho in 1995. They proposed that "all published figures should be accompanied by the complete software environment necessary for generating those figures." The dynamic documents that we use today took this idea and extended it, not only including the software environment, but the code itself.

### Run with it
The authors sell the idea of a compendium in terms of flexibility for the reader. She should be able to choose whether she wants to read code behind figures or hide it. This got me thinking. The readers of my blog (Hi, Dad!) only have this choice if I send them the compendium itself. Otherwise, I choose which code they see and which code I want to hide (*bwahaha*, the power is ALL MINE). I would like to implement Gentleman and Temple Lang's compendium idea inside my blog. So, from now on you will have the power to choose to see all code if you like, or none at all. To toggle, click this button and hide or show how this pretty picture is made. 

<div id="clickme2">
  <span>
    <i class="fa fa-gear"></i>  
    Click here
  </span>
</div>

<script>
$( "#clickme2" ).click(function() {
  $( "code" ).toggle( "slow", function() {
    // Animation complete.
  });
  $( ".status" ).toggle( "slow", function() {
    // Animation complete.
  });
});
</script>

{% highlight r %}
# Generate data
library(reshape2) # for melt
library(ggplot2)
volcano3d <- melt(volcano)
names(volcano3d) <- c("x", "y", "z")

# Basic plot
v <- ggplot(volcano3d, aes(x, y, z = z))
v + geom_tile(aes(fill = z)) + stat_contour()
{% endhighlight %}

![center](../../../../../images/blog/2014-02-01-reproducible-research/unnamed-chunk-1-1.png)
From here on out, it will be a part of all future blog posts. Choose your own adventure guys!





