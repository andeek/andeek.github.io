---
layout: post_ak
title: "Upgrading R - Have no fear!"
root: "../../../../"
comments: true
---



Hello faithful readeRs. Today I want to talk about something that may be worrying you: upgrading your version of R. Now readeRs, I understand your fear. I don't want to lose all my installed libraries either! That would require me remembering all their names and downloading them anew. Not ideal.

I have been working hard to solve this problem, but the solution was simple: backup a list of installed libraries!

Before you upgrade, run the following code:


{% highlight r %}
IP <- as.data.frame(installed.packages())
MyPkgs <- subset(IP, !Priority %in% c("base", "recommended"), select = Package)
save(MyPkgs, file = paste(getwd(), "/MyPkgs.Rdata", sep = ""))
{% endhighlight %}


First, IP is assigned as a list of all installed packages. This list is filtered down to just the name of your packages. Finally, the file MyPkgs. Rdata is saved in your working directory. All systems are go, upgrade your version of R.

After you have upgraded to the newest and coolest R ever, run the next block:


{% highlight r %}
load(paste(getwd(), "/MyPkgs.Rdata", sep = ""))
install.packages(as.vector(MyPkgs$Package), repos = "http://cran.r-project.org")
{% endhighlight %}


This will load your newly created backup file and install all those packages from the CRAN repository. Continue enjoying your old functions with all the added benefits of a new version! You're welcome.
