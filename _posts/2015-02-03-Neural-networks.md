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
grViz(replace_in_spec("
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
{% endhighlight %}

<!--html_preserve--><div id="htmlwidget-1399" style="width:504px;height:504px;" class="grViz"></div>
<script type="application/json" data-for="htmlwidget-1399">{ "x": {
 "diagram": "\ndigraph a_nice_graph {\n\n# node definitions with substituted label text\nnode [fontname = Helvetica]\na [label = \"top\"]\nb [label = \"10\"]\nc [label = \"11\"]\nd [label = \"12\"]\ne [label = \"13\"]\nf [label = \"14\"]\ng [label = \"15\"]\nh [label = \"16\"]\ni [label = \"17\"]\nj [label = \"18\"]\n\n# edge definitions with the node IDs\na -> {b c d e f g h i j}\n}",
"config": {
 "engine": "dot",
"options": null 
} 
},"evals": [  ] }</script><!--/html_preserve-->




