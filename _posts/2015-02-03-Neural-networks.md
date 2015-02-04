---
title: "Reading: Neural networks"
layout: "post_ak"
comments: yes
root: ../../../../
---

As part of the course [Stat 503](http://streaming.stat.iastate.edu/~dicook/EDA.and.datamining/) I am taking this semester, I will be posting a series of responses to assigned course readings. Mostly these will be my rambling thoughts as I skim papers.

****

This week we are watching some videos on neural networks from Andrew Ng, as well as Trevor Hastie and Robert Tibshirani ([video 1](https://class.coursera.org/ml-005/lecture/43) [video 2](https://class.coursera.org/ml-005/lecture/44) [video 3](https://class.coursera.org/ml-005/lecture/45) [video4](https://class.coursera.org/ml-005/lecture/46) [video 5](https://www.youtube.com/watch?v=31Q5FGRnxt4) [video 6](https://www.youtube.com/watch?v=MpX8rVv_u4E)). These videos give a good introduction to the concepts behind neural networks, including the model representaion, motivation behind, and a detailed explanation of logistic regression.

###A neural what what?
The term "neural network" for me evokes images of an incredibly complex model that is fit with some unknown blackbox procedure, probably in the cloud. Something like this.

<img src="{{ page.root }}images/blog/2015-02-03-Neural-networks/big_data.jpg" alt="http://bigdatapix.tumblr.com/" style="width: 500px;"/>

In reality, a neural network is a highly flexible non-linear model that can be used for classification. The model uses multiple layers that are related to each other through sigmoid functions. Hence, a neural network is something like a hierarchical logistic regression. We can make a simplified cartoon of the model to get a better understanding.


{% highlight r %}
diagram <- grViz(replace_in_spec("
digraph a_nice_graph {

# node definitions with substituted label text
node [fontname = Helvetica]
a [label = '@@1']
b [label = '@@2-1']
c [label = '@@2-2']
d [label = '@@2-3']
e [label = '@@2-4']
f [label = '@@2-5']
g [label = '@@2-6']
h [label = '@@2-7']
i [label = '@@2-8']
j [label = '@@2-9']

# edge definitions with the node IDs
a -> {b c d e f g h i j}
}

[1]: 'top'
[2]: 10:20
"))

cat(as.character(grVizOutput(diagram)[[1]]))
{% endhighlight %}

<div id="list(diagram = &quot;\ndigraph a_nice_graph {\n\n# node definitions with substituted label text\nnode [fontname = Helvetica]\na [label = \&quot;top\&quot;]\nb [label = \&quot;10\&quot;]\nc [label = \&quot;11\&quot;]\nd [label = \&quot;12\&quot;]\ne [label = \&quot;13\&quot;]\nf [label = \&quot;14\&quot;]\ng [label = \&quot;15\&quot;]\nh [label = \&quot;16\&quot;]\ni [label = \&quot;17\&quot;]\nj [label = \&quot;18\&quot;]\n\n# edge definitions with the node IDs\na -&gt; {b c d e f g h i j}\n}&quot;, config = list(engine = &quot;dot&quot;, options = NULL))" id="NULL" id="NULL" id="list(defaultWidth = NULL, defaultHeight = NULL, padding = NULL, viewer = list(defaultWidth = NULL, defaultHeight = NULL, padding = NULL, fill = TRUE, suppress = TRUE, paneHeight = NULL), browser = list(defaultWidth = NULL, defaultHeight = NULL, padding = NULL, fill = FALSE), knitr = list(defaultWidth = NULL, defaultHeight = NULL, figure = TRUE))" id="NULL" id="NULL" style="width:100%; height:400px" class="grViz html-widget html-widget-output"></div>




