---
layout: post
title: "How a Majority Vote Reward Scheme Can Improve Human Computation in a Spatial Location Identification Task"
date: 2014-01-15 18:25:12 +0800
comments: true
categories: research
---

(This post is originaly published in CrowdResearch.org, [ link ](http://crowdresearch.org/blog/?p=8186).)

{% img center # /images/hcomp13/SpLIT.png 1000 1000 "A spatial location identification task (SpLIT)" %}

We created a spatial location identification task (__SpLIT__), in which humans examine a 3D camera view of an environment to
infer its spatial location on a 2D schematic map (e.g. a floor plan). However, the SpLIT are often difficult to automate
because the identification of salient cues often requires semantic features that are challenging to recover from the
image and the map, especially when the cues are ambiguous or do not provide sufficient information to pinpoint the exact
location.

One natural question to ask is how one can leverage human computation to perform a typical SpLIT. In order to find the
answer, we designed a study using Amazon Mechanical Turk to investigate how turkers can perform the task in two kinds of
reward schemes: ground truth and majority vote, even when they were not familiar with the environment.

We carefully chose five pictures represent different levels of ambiguity, in terms of the extent to which workers could
use the pre-defined markers (cues) to infer the location of the camera view.

The results are listed below: <!--more-->

1. The accuracies of each task under both schemes drop as the level of ambiguity increases. This suggests that the lack
   of spatial cues did make the task harder. And it is obvious from the figure that performance in majority vote scheme
   was better than that in the ground truth reward scheme.

    {% img center # /images/hcomp13/correctness_of_points.png 1000 1000 "A spatial location identification task (SpLIT)" %}

2. We also calculated the accuracies of individual participants, it showed that there were more turkers that at least
   chose one correct location in the majority vote scheme than in the ground truth one. In addition, the percentage with
   high ac- curacies (0.8 and 1.0) in the majority vote scheme is also higher than that in the ground truth one.

    {% img center # /images/hcomp13/correctness_of_people.png 1000 1000 "A spatial location identification task (SpLIT)" %}
    
3. To summarize the results, we found that the majority vote reward scheme in general led to a higher level of precision
   and reliability in the answers provided by the workers.

    {% img center # /images/hcomp13/compare.png 1000 1000 "A spatial location identification task (SpLIT)" %}

Though there were not enough data to fully understand this result, the current study is clearly a first step towards
understanding how human computation can be incorporated into applications that support spatial tasks

For more, see our [ full paper ](http://www.aaai.org/ocs/index.php/HCOMP/HCOMP13/paper/view/7525).

Author List:

* [ Huaming Rao ](http://web.engr.illinois.edu/~huamingr/), Huaming Rao, Nanjing University of Science & Technology and University of Illinois at Urbana-Champaign.
* [ Shih-Wen Huang ](http://homes.cs.washington.edu/~wenhuang/index.html), University of Illinois at Urbana-Champaign.
* [ Wai-Tat Fu ](http://www.cs.illinois.edu/homes/wfu/), University of Illinois at Urbana-Champaign.
