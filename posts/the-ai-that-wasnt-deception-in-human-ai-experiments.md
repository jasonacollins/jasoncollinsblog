---
title: "The AI that wasn't: Deception in human-AI experiments"
author: "Jason Collins"
date: 2025-11-14 09:00:00+11:00
draft: true
bibliography: references.bib
---

Experimental economists have a strong norm against deception in experiments. Here's Andreas @ortmann2019:

> I open with a statement of fact: deception in the form of acts of commission, while still widespread in (social) psychology and business sciences such as marketing, is factually banned in laboratory experimental economics. This ban is not legislated but, until recently, was a social norm that the community of experimental economists had been able to reasonably enforce.

For some experimental economics journals, deception is grounds for desk rejection.

There are a few reasons for this norm. An important one is that if participants suspect they are being deceived or provided incorrect information, they will alter their behavioural responses and undermine the experimental results. An example of this is the famous [Solomon Asch conformity experiments](https://en.wikipedia.org/wiki/Asch_conformity_experiments), in which those who believed they were being deceived were less likely to conform with the group.

There is also an externality from deception to other experiments. After being deceived in one experiment - as they often discover when promises aren't delivered or in experimental debriefs - participants will be less trusting in future experiments, again changing their behaviour. Today where many experiments are run with public subject pools of people who are completing many experiments and surveys, regular deception could shift their expectations.

There is no norm against deception in psychology. Deception is common and argued to be required for many experiments.

There is also no such norm in human-computer interaction research, as I have discovered the last couple of years. And by deception, I am not talking about deception by omission: not telling people everything about the experiment. Rather, the deception involves acts of commission such as telling people things that are not true.

One common form of deception concerns the AI the experimental subject is interacting with. Often, there is no actual AI. Rather, the participants are shown a set of hand-crafted responses. I have seen this called "synthetic AI".

It also seems common for experimenters to tell the occasional lie to generate the desired response. Below are examples of each and a few questions in response.

## Synthetic-AI

To run an experiment on human responses to an AI, on face value you want an AI. But that's a challenge. For one, you need to procure an AI, or develop an AI to train on the task or data. Depending on the nature of the AI, you might also design an interface. And apart from being a lot of work, there's no guarantee that your AI will have the features you desire, such as a certain error rate or error boundary.

In economics, this challenge has typically led to the use of statistical prediction tasks. Given a dataset about, say, student achievement, you develop a statistical model - which you call an AI - to predict achievement based on other features of the student. Apart from the easy availability of datasets to create these tasks (such as those available on [Kaggle](https://www.kaggle.com/datasets) or in repositories such as the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)), developing statistical models is a bread and butter task for an economist. You can often train a model on these relatively well-structured datasets in a few lines of code.

An interesting feature of these models is that they typically outperform human judgment (by a considerable margin). The optimal interaction is that the human hands off the decision to the AI. That makes these models great for algorithm aversion studies, but provides somewhat limited scope to examine collaborative decision making.

If you want a weaker model you might withhold data from the model (as one done in a recent paper [I posted about](is-following-ai-advice-anchoring-bias.qmd) on anchoring). This can introduce asymmetric information by giving the human something the model doesn't have. Ultimately, however, statistical prediction is only a subset of the space in which you might want to study human-AI interaction. That moves us into more complex domains where it's not so easy to develop a model.

In experiments coming from the human-computer interaction field, you do see statistical models, but often the experiments require a richer environment. And that's where they turn to deception via synthetic AI.

One example of synthetic AI is in work by @buçinca2021 on whether triggering slow thinking can increase engagement with explanations of AI recommendations. They created a task where participants were shown a picture of a meal and information on the main ingredients, and asked what ingredients to substitute to make it low-carb while maintaining the original flavour.

![@buçinca2021, Figure 1](img/the-ai-that-wasnt-deception-in-human-ai-experiments/bucinca-et-al-2021-fig-1.png){#fig-bucinca_et_al_2021_fig_1}

And how was this AI developed? They write:

> We designed a simulated AI for the experiment, which had 75% accuracy of correctly recognizing the ingredient with the highest carbohydrate impact in the image of the meal. Note that we did not train an actual machine learning model for this task because we wanted to have control over the type and prevalence of error the AI would make.

This is one of the more direct statements that they made the AI outputs up, but even where less explicitly stated, it is common practice.

The question is then: what do participants believe of this scenario? Do they believe that an AI is actually delivering these suggestions and associated explanations? To the extent they don't, does this affect their likelihood of following the AI recommendation?

Some people in the human-computer interaction field do go the extra yard of developing a more complex model - and full praise to them. As an example, @lai2022 developed neural architecture to classify Wikipedia comments and Reddit hate speech. The particular architecture they used allowed identification of the rationale, communicated through highlights of the relevant words in the text. It looks like a lot of effort, but they're not deceiving participants. It also looks like a more ecologically valid experimental setup. That would boost my confidence in the results.

![@lai2022, Table 1](img/the-ai-that-wasnt-deception-in-human-ai-experiments/lai-et-al-2022-table-1.png){#fig-lai_et_al_2022_table_1}

Sometimes to avoid deception, people come up with fairly creative ways to describe what is being provided to participants. @logg2019 wanted to test whether algorithm aversion was due to aversion to algorithms themselves or an aversion to external advice. As a result, they wanted to deliver identical predictions to experimental participants (to maintain experimental control) while being able to describe it as coming from either an algorithm or a human.

In experiment 1, 202 participants were asked to estimate the weight of a person in a photo. Everyone received advice, described as coming from either an algorithm or a person, that the person was 163lb, based on estimated of 415 people in another experiment. (The person weighted 164lb.) The precise wording was either:

> An algorithm ran calculations based on estimates of participants from a past study. The output that the algorithm computed as an estimate was: 163 pounds.

> The average estimate of participants from a past experiment was: 163 pounds.

Both of those statements are true, although the word "algorithm" is doing a lot of work there when the algorithm is averaging.

The word "algorithm" is stretched even more in Experiment 1C, a task to estimate a person's attractiveness from another person's perspective based on a text description of that person. The wording in each condition was:

> An algorithm estimated this (wo)man's attractiveness (humor/ enjoyableness) from Mike's (Julia’s) perspective. The algorithm's estimate was: X

> In another study, 48 people estimated this (wo)man's attractiveness (humor/enjoyableness) from Mike's (Julia’s) perspective. Their estimate was: X

@logg2019 described their choice of procedure as allowing them to avoid deception. For Experiment 1C, I am not convinced and I suspect experimental economists wouldn't agree. The word algorithm is triggering is likely quite different expectations than reality. If someone told me an algorithms was being used to estimate attractiveness, I would assume much more work was going on than averaging estimates from people. I'd likely assume a text analysis mode.

One ameliorating factor is that this experiment was run pre-ChatGPT in 2019, so participants might not immediately imagine some text analysis algorithm. Conversely, in 2025 I have no problem imagining a text-analysis algorithm and would be giving my preferences on that assumption. However, if participants couldn't picture a text analysis algorithm in 2019, what were they assuming?

An interesting element of the most recent literature is that we are seeing much more actual use of AI, in the form of ChatGPT and other LLM models. It's finally easy to get an "AI" for almost any task with low effort. The deception is fading away, but that is likely coming at the cost of control. I haven't seen many ChatGPT experiments that tell me something useful about human-AI interaction or that isn't already out of date by the time it is released. But that's a topic for a different post.

## Straight-out porkie pies

I sympathise with the synthetic AI approach, albeit not being completely on board with it. Coming up with experimental tasks where the AI really is an AI performing the task you say it is is tough. In many cases this requires detailed model builds and software interfaces - and even then, one element is often not quite as stated.

But the deception tends not to be limited to synthetic AI. The AI is often completely misrepresented.

Here's an example from Rastogi et al (2022), who examined whether they could de-anchor experimental participants from AI advice. I reviewed this paper and the question of whether this even involves anchoring in [a post last month](is-following-ai-advice-anchoring-bias.qmd).

The authors write:

> To induce anchoring bias, the participant was informed at the start of the training section that the AI model was 85% accurate (we carefully chose the training trials to ensure that the AI was indeed 85% accurate over these trials), while the model’s actual accuracy is 70.8% over the entire training set and 66.5% over the test set. Since our goal is to induce anchoring bias and the training time is short, we stated a high AI accuracy.

The training set they reference is the data they trained the model on. Effectively, they told people the AI had an accuracy that it didn't. The training trials would have affirmed this belief.

However, they go on to state:

> \[T\]his disparity between stated accuracy (85%) and true accuracy (70.8%) is realistic if there is a distribution shift between the training and the test set, which would imply that the humans’ trust in AI is misplaced. In addition to stating AI accuracy  at the beginning, we informed the participants about the AI prediction for each training trial after they have attempted it so that they can learn about AI’s performance first-hand.


## Thoughts

I sense one reason people love experiments with LLMs is that it involves an actual AI! Although being a stochastic AI, one that is rather hard to control, that comes with a bunch of different costs.