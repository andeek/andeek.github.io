---
title: "Reading: Telling a story with data"
layout: "post_ak"
comments: yes
root: ../../../../
---

As part of the course [Stat 503](http://streaming.stat.iastate.edu/~dicook/EDA.and.datamining/) I am taking this semester, I will be posting a series of responses to assigned course readings. Mostly these will be my rambling thoughts as I skim papers.

****

This week we are reading multiple blogs (["Naomi Robbins' Forces blog"](http://www.forbes.com/sites/naomirobbins/) and ["Beautiful Data"](http://beautifuldata.net/)), as well as an ["interview with Hadley Wickham"](http://statr.me/2013/09/a-conversation-with-hadley-wickham/), Wickham, Swayne, and Poole's ["Bay Area Blues"](http://vita.had.co.nz/papers/bay-area-blues.pdf) and a business ["blog post"](http://www.processexcellencenetwork.com/lean-six-sigma-business-transformation/columns/varitian-bites-deming-s-sopk-part-iii) on variation. These readings are meant to give us muliple perspectives of how we can learn from data.

# Defining a narrative
I think the most important string that ties all the readings together this week is using data to define a narrative. We have multiple sources explaining why defining a narrative with data is a good idea, specifically the blog post from Process Excellence Network, and ["this post"](http://beautifuldata.net/2015/01/data-storytelling-stepwise-abstraction-from-raw-data/) on data storytelling from Beautiful Data. Additionally, we have a great example of telling a story with data from the Bay Area Blues chapter, demonstrating the power of data storytelling when done right. I really enjoyed reading both the articles on why storytelling is important, but the idea was really hammered home with the example.

# Why tell a story?
We all want to "let the data speak", but what if the audience is speaking a different language? In the blog post on the Process Excellence Network, entitled "Variation, So Meaningful Yet So Misunderstood", six examples are given that show the dangers of managers misunderstanding their data. This is a powerful message, especially as someone who spent some time explaining data to VP-level execs. It seems fairly common in my experience for an audience to misinterpret their variation as a change, rather than potentially random noise. This is why someone that understands data and variation (like an analyst, or these days a "data scientist") to interpret what the data is saying into something that their audience can understand. 

The act of guiding a user through a story told by data can help ensure that the point is received, rather than misinterpreted. One of the ways this guiding is done is by enhancing the current data with other sources, to present a context to interesting bits of data that fall out through analysis. In the case study of Bay Area housing by Wickham, Swayne, and Poole, this was accomplished by tying geocodes to each address in their dataset. This additional amount of information greatly enhanced the story they were telling and was able to hook readers' interest by making the analysis so easily accessible.

# Drill down
Another excellent way to tell a story with data is by examining increasingly fine levels of granularity in the data, or "drilling down". By starting with a general approach and filtering down into the most interesting pieces found, the user is sucked in to the story and can relate fully to the information presented. This process of drilling down is even more meaningful if the user can drive it themselves. Through the interview with Hadley, he highlighted some tools he has created that help make this easier to provide to a user, *dplyr* and *ggvis*. These two innovations are currently making it easier for the audience to write their own stories with data, and communicate their findings with graphics.
