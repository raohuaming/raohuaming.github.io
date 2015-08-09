---
layout: post
title: "Emerging Dynamics in Crowdfunding Campaigns"
date: 2014-03-21 00:15:38 +0800
comments: true
categories:  crowdfunding research
---

{% img center /images/sbp14/money.jpg %}

Recent research has shown that, in addition to the quality and representations of project ideas, dynamics of investment during a crowdfunding campaign also play an important role in determining its success.  To further understand the role of investment dynamics, we did an exploratory analysis by applying a decision tree model to train predictors over the time series of money pledges to campaigns in Kickstarter to investigate the extent to which simple inflows and first-order derivatives can predict the eventual success of campaigns.  

<!--more-->

{% img center # /images/sbp14/result1.png 1000 1000 "Figure 1: Prediction accuracies over time by using the values of money inflows and the selected significant time before cur- rent time" %}

The results based on the  the values of money inflows are shown in Figure 1:

* As expected, the performance of the predictors steadily improves.
* With only the first 15% of the money inflows, out predictor can achieve 84% accuracy.
* The most “active” periods could be around the first 10% as well as between the 40-60%.

{% img center # /images/sbp14/result2.png 1000 1000 "Figure 2: Prediction accuracies over time by using the derivative of money inflows and the selected significant time before current time" %}

The results based on the the derivative of money inflows are shown in Figure 2:

* The performance of the predictors does not increase much until the very last stage.
* The most important period also does not change until the end, jumping from 5% to 100%.

So according to the above results, we reach the conclusion:

* The periods around 10% and 40%-60% during a campaign had a stronger impact.
* “Seed money” (init 15% money inflow) may probably determine the final result of a campaign.
* Don’t give up and you can still make it at the very end of the campaign.

For more, please see our [full paper](http://link.springer.com/chapter/10.1007/978-3-319-05579-4_41).

Author List:

* [ Huaming Rao ](http://web.engr.illinois.edu/~huamingr/), Huaming Rao, Nanjing University of Science & Technology and University of Illinois at Urbana-Champaign.
* [ Anbang Xu ](http://web.engr.illinois.edu/~xu26/), University of Illinois at Urbana-Champaign.
* [ Xiao Yang](http://xiao-yang.me/),  Tsinghua University.
* [ Wai-Tat Fu ](http://www.cs.illinois.edu/homes/wfu/), University of Illinois at Urbana-Champaign.


