---
title: "The AI that wasn't: deception in human-AI experiments"
author: "Jason Collins"
date: 2025-11-14 09:00:00+11:00
draft: true
bibliography: references.bib
---

Experimental economists have a strong norm against deception in experiments. Here's Andreas @ortmann2019:

> I open with a statement of fact: deception in the form of acts of commission, while still widespread in (social) psychology and business sciences such as marketing, is factually banned in laboratory experimental economics. This ban is not legislated but, until recently, was a social norm that the community of experimental economists had been able to reasonably enforce.

For some experimental economics journals, deception is grounds for desk rejection.

There are a few reasons for this norm. One is that if participants suspect they are being deceived, they will alter their behaviour and undermine the experimental results. An example of this is the famous [Solomon Asch conformity experiments](https://en.wikipedia.org/wiki/Asch_conformity_experiments), in which those who believed they were being deceived were less likely to conform with the group.

There is also an externality from deception to other experiments. After being deceived in one experiment - as they discover when promises aren't kept or in experimental debriefs - participants will be less trusting in future experiments, again changing their behaviour. With public subject pools of people who are completing many experiments and surveys, regular deception could shift their expectations.

There is no norm against deception in psychology. Deception is common and argued to be required for many experiments.

There is also no such norm in human-computer interaction research, as I have discovered the last couple of years. I am not talking about deception by omission: not telling people everything about the experiment. Rather, I mean acts of commission, such as telling people things that are not true.

One common form of deception is that there is no actual AI. Rather, the participants are shown hand-crafted responses. I have seen this called "synthetic AI".

It also seems common for experimenters to tell the occasional lie to generate the desired response. 

Below are examples of each and a few questions in response. I don't have a firm view on some of this deception except for having a general queasiness and desire to reduce this, so the below is more observations than hardened views or argument.

## Synthetic-AI

To run an experiment on human responses to an AI, you want an AI. But that's a challenge. You need to procure or develop an AI to train on the task or data. Depending on the nature of the AI, you might also design an interface. Beyond the work involved, there's no guarantee that your AI will have the features you desire, such as a certain error rate or error boundary.

In economics, this challenge typically leads to the use of statistical prediction tasks. Given a dataset about, say, student achievement, you develop a statistical model (called an AI) to predict achievement based on other features of the student. With readily available datasets to create these tasks (such as those available on [Kaggle](https://www.kaggle.com/datasets) or in repositories such as the [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/)), developing statistical models is a bread and butter task for an economist. You can train a model on these well-structured datasets in a few lines of code.

These models typically outperform human judgement by a considerable margin. The optimal interaction is the human hands off the decision to the AI. That makes these models great for algorithm aversion studies, but provides limited scope to examine collaborative decision making.

If you want a weaker model you might withhold data from the model (as done in a recent paper [I posted about](is-following-ai-advice-anchoring-bias.qmd) on anchoring). This gives the human information the model doesn't have. Ultimately, however, statistical prediction is only a subset of the space in which you might want to study human-AI interaction. That moves us into more complex domains where it's not so easy to develop a model.

In experiments coming from the human-computer interaction field, you do see statistical models, but often the experiments require a richer environment. And that's where they turn to deception via synthetic AI.

One example of synthetic AI is in work by @buçinca2021 on whether triggering slow thinking can increase engagement with explanations of AI recommendations. They created a task where participants were shown a picture of a meal and information on the main ingredients, and asked what ingredients to substitute to make it low-carb while maintaining the original flavour.

![@buçinca2021, Figure 1](img/the-ai-that-wasnt-deception-in-human-ai-experiments/bucinca-et-al-2021-fig-1.png){#fig-bucinca_et_al_2021_fig_1}

And how was this AI developed? They write:

> We designed a simulated AI for the experiment, which had 75% accuracy of correctly recognizing the ingredient with the highest carbohydrate impact in the image of the meal. Note that we did not train an actual machine learning model for this task because we wanted to have control over the type and prevalence of error the AI would make.

This is one of the more direct statements that the AI was fabricated, but even where less explicitly stated, it is common practice.

The question is then: what do participants believe of this scenario? Do they believe that an AI is actually delivering these suggestions and associated explanations? To the extent they don't, does this affect their likelihood of following the AI recommendation?

Some people in the human-computer interaction field do go the extra yard of developing a more complex model - and full praise to them. As an example, @lai2022 developed neural architecture to classify Wikipedia comments and Reddit hate speech. The particular architecture they used allowed identification of the rationale, communicated through highlights of the relevant words in the text. It looks like a lot of effort, but they're not deceiving participants. It also looks like a more ecologically valid experimental setup. That would boost my confidence in the results.

![@lai2022, Table 1](img/the-ai-that-wasnt-deception-in-human-ai-experiments/lai-et-al-2022-table-1.png){#fig-lai_et_al_2022_table_1}

To avoid deception, some researchers get creative. @logg2019 wanted to test whether algorithm aversion was due to aversion to algorithms themselves or an aversion to external advice. They needed to deliver identical predictions to experimental participants (to maintain experimental control) while being able to describe it as coming from either an algorithm or a human.

In experiment 1, 202 participants were asked to estimate the weight of a person in a photo. Everyone received advice, described as coming from either an algorithm or a person, that the person was 163lb, based on estimates of 415 people in another experiment. (The person weighed 164lb.) The precise wording was either:

> An algorithm ran calculations based on estimates of participants from a past study. The output that the algorithm computed as an estimate was: 163 pounds.

> The average estimate of participants from a past experiment was: 163 pounds.

Both statements are technically true, though calling averaging an algorithm is generous.

The word "algorithm" is stretched even more in Experiment 1C, a task to estimate a person's attractiveness from another person's perspective based on a text description of that person. The wording in each condition was:

> An algorithm estimated this (wo)man's attractiveness (humor/ enjoyableness) from Mike's (Julia’s) perspective. The algorithm's estimate was: X

> In another study, 48 people estimated this (wo)man's attractiveness (humor/enjoyableness) from Mike's (Julia’s) perspective. Their estimate was: X

@logg2019 described their choice of procedure as allowing them to avoid deception. I am not convinced and I suspect experimental economists wouldn't agree.

The word "algorithm" triggers expectations that don't match reality. If someone told me an algorithm was estimating attractiveness, I would assume something more sophisticated than averaging estimates from humans. I'd likely assume a text analysis model.

One ameliorating factor is that this experiment ran pre-ChatGPT in 2019. Participants might not immediately imagine a text analysis algorithm. But in 2025 I'd assume exactly that and would respond based on that assumption. This raises the question: if participants couldn't picture a text analysis algorithm in 2019, what were they assuming?

Much recent literature actually use of AI, in the form of ChatGPT and other LLM models. It's finally easy to get an "AI" for almost any task. The deception is fading away, but that comes at the cost of control. I haven't seen many ChatGPT experiments that tell me something useful about human-AI interaction or that isn't already outdated on publication. But that's a topic for a different post.

## Straight-out porkie pies

I sympathise with synthetic AI, but I'm not comfortable with it. Creating tasks with actual AI doing what you claim is tough. For many specific questions, it's beyond the technical capability of the experimenters.

But the deception isn't limited to synthetic AI. The AI is often completely misrepresented.

Here's an example from Rastogi et al (2022), who examined whether they could de-anchor experimental participants from AI advice. I [posted about this paper last month](is-following-ai-advice-anchoring-bias.qmd).

The authors write:

> To induce anchoring bias, the participant was informed at the start of the training section that the AI model was 85% accurate (we carefully chose the training trials to ensure that the AI was indeed 85% accurate over these trials), while the model’s actual accuracy is 70.8% over the entire training set and 66.5% over the test set. Since our goal is to induce anchoring bias and the training time is short, we stated a high AI accuracy.

The training set they reference is the data they trained the model on. Effectively, they told people the AI had an accuracy that it didn't. The training trials would have affirmed this belief.

However, they go on to state:

> \[T\]his disparity between stated accuracy (85%) and true accuracy (70.8%) is realistic if there is a distribution shift between the training and the test set, which would imply that the humans’ trust in AI is misplaced. In addition to stating AI accuracy at the beginning, we informed the participants about the AI prediction for each training trial after they have attempted it so that they can learn about AI’s performance first-hand.

Deception of this nature undermines the experiment. The "anchoring" here is justified given what they were told and observed. You can't study anchoring bias when you've deliberately created the conditions for justified trust.

Here are a few more examples. @yin2024 told participants that responses came from either a human or AI, irrespective of the actual source, in their analysis of whether people "feel heard". @longoni2023 used articles on AI failures to create news stories in which either an AI or a human caused the problem. @khadpe2020 used human workers to simulate chatbots, with participants told that these "AI" workers were modelled on one of a toddler, middle schooler, young student, recent graduate or trained professional.

In each case you're relying on there being no AI or human "smell" to the responses that doesn't match the purported communication. You're relying on them believing your statement even when the evidence in front of them might point elsewhere (or worse, treating their trust in you as an error).

There is also little thought given to contamination of the subject pool. The participants in most of these studies come from panels such as Amazon Turk, who spend their day doing studies like these. How many times do they read an experimental debrief that the wool has been pulled over their eyes? What does that do to their future interactions?

I don't know the answers, but these deceptive practices introduce another layer of doubt as to whether we should trust these results (beyond the poor experimental practices I've discussed).

## What to do?

The human-computer / human-AI literature is shaky. As I noted [elsewhere](why-i-dont-trust-most-human-ai-interaction-experimental-research.md), experimental practices look like those in psychology circa 2005: small sample sizes, no pre-registration, no data openness. All the hallmarks of a replication crisis.

At the same time, the field is flooded. My alerts and literature searches deliver dozens of papers every week, and I'm not even catching all of them. Most are trivial, and even when they have an interesting or useful hypothesis, I typically don't trust them.

As a result, researchers should slow down, invest in their experimental designs and AIs, and make them as robust as possible. Most of the deception could be eliminated with a bit of thought and work and we'd get a much more valuable literature.