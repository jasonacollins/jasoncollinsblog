---
title: 'Deception in the human-AI interaction literature'
author: "Jason Collins"
date: 2025-11-14 09:00:00+11:00
draft: true
images: [""]
---

Experimental economists have a strong norm against deception in experiments. Here's one statement from [have asked for Andreas deception chapter from library]



The Journal of XXXX bans publication of experiments with deception.

That's not the norm in psychology and, as it tuns out, human-computer interaction research. Across the broad swathe of experimental literature I have traversed in the last year or two, deception 

The most common form of deception concerns the nature of the AI the experimental subject is interacting with. Often, there is no actual AI, but rather a set of responses hand crafted by the experimental participants.

Beyond that, it also seems common to tell the ocassional lie to generate thje desired reponse. Below are examples of each and a few questions in response.

## Synthetic-AI

If you want to run an experiment in which you gauge human responses to an AI, on face value you want an AI. But that's a challenge. For one, it requires

In economics, this typically means that the task is a statistical prediction task - 

These tasks have been a staple of 

Crafting an AI 


Let me give one example, a pa

Some people do go this extra yard - and full praise to them. As an example, Vivian Lai and friends developed neural architectur to classif Wikipe


## Straight-out porkie pies

I sympathise with the synthetic AI approach, albeit not being completely on board with it. Coming up with experimental tasks where the AI really is an AI performing the task you say it is is tough. In many cases this requires detailed model builds and software interfaces - and even then, one element is often not quite as stated.

But the deception tends not to stop there. It includes ...

Here's a rather extreme case from Rastogi et al (2022), who examined whether they could de-anchor . I reviewed this paper and the question of whether this even involves anchoring in [another post](ADDLINK).

The authors write:

> To induce anchoring bias, the participant was informed at the start of the training section that  the AI model was 85% accurate (we carefully chose the training trials to ensure that the AI was indeed 85% accurate over these trials), while the model’s actual accuracy is 70.8% over the entire training set and 66.5% over the test set. Since our goal is to induce anchoring bias and the training  time is short, we stated a high AI accuracy.

The training set they reference here is the data they trained the model on. The training trials are a set of 15 

Effectively, they told people the AI had an accuracy that it didn't. 


This disparity between stated accuracy (85%)  and true accuracy (70.8%) is realistic if there is a distribution shift between the training and the test

However, let's consider what they can infer from 15 trials. Suppose the AI actually had 85% accuracy. You are going to see, on average, 12.75 correct trials. A 70.8% correct AI will give 10.575 trials on average.

So let's suppose you see 12 correct trials. What should you infer about the AI accuracy? The 95% confidence interval is approximately \[70%, 90%\]. You can't tell the difference between a 70% and 85% accurate algorithm. And that's assuming they're counting accurately the number of correct and incorrect answers. 

They seek to defend the deception as follows:

> this disparity between stated accuracy (85%) and true accuracy (70.8%) is realistic if there is a distribution shift between the training and the test set, which would imply that the humans’ trust in AI is misplaced.

## Do participant's believe the AI is AI?

With generative AI, this is coming closer to being feasible. But looking at many experiments conducted through the last decade, I suspect many participants would not believe an AI 

## Do participants believe the human is human?

Even more so 

## Thoughts

I sense one reason people love experiments with LLMs is that it involves an actual AI! Although being a stochastic AI, one that is rather hard to control, that comes with a bunch of different costs.