---
title: Noise
author: "Jason Collins"
date: 2018-05-09 09:00:07+00:00
draft: false
aliases:
  - /noise
---

Daniel Kahneman has a [new book in the pipeline](https://www.thebookseller.com/news/william-collins-scoops-kahnemans-book-7-figure-pre-empt-752276) called Noise. It is to be co-authored with Cass Sunstein and Olivier Sibony, and will focus on the "chance variability in human judgment", the "noise" of the book's title.

I hope the book is more Kahneman than Sunstein. For all [Thinking, Fast and Slow's faults](https://www.jasoncollins.blog/re-reading-kahnemans-thinking-fast-and-slow/), it is a great book. You can see the thought that went into constructing it.

Sunstein's recent books feel like research papers pulled together by a university student - which might not be too far from the truth given the fleet of research assistants at Sunstein's command. Part of the flatness of Sunstein's books might also come from his writing pace - he writes more than a book a year. (I count over 30 on his [Wikipedia](https://en.m.wikipedia.org/wiki/Cass_Sunstein) page since 2000, and 10 in the last five years.) Hopefully Kahneman will slow things down, although with a planned publication date of 2020, Noise will be a shorter project than Thinking, Fast and Slow.

**What is noise?**

Kahneman has already written about noise, most prominently with three colleagues in [Harvard Business Review](https://hbr.org/2016/10/noise). In that article they set out the case for examining noise in decision-making and how to address it.

Part of that article is spent distinguishing noise from bias. Your bathroom scale is biased if it always reads four kilograms too heavy. If it gives you a different reading each time you get on the scale, it is noisy. Decisions can be noisy, biased, or both. A biased but low noise decision will always be wrong. A biased but high noise decision will be all over the shop but might occasionally get lucky.

One piece of evidence for noise in decision-making is the degree to which people will contradict their own prior judgments. Pathologists assessing biopsy results had a [correlation of 0.63](https://doi.org/10.1037/h0037164) with their own judgment of severity when shown the same case twice (the HBR article states 0.61, but I read the referenced article as stating 0.63). Software programmers [differed by a median of 71%](https://doi.org/10.1016/j.jss.2007.03.001) in the estimates for the same project, with a correlation of 0.7 between their first and second effort. The lack of consistency in decision-making only grows once you start looking across people.

I find the concept of noise a useful way of thinking about decision-making. One of the main reasons why simple algorithms are typically superior to human decision makers is not because of bias or systematic errors by the humans, but rather the inconsistency of human judgment. We are often all over the place.

Noise is also a good way of identifying those domains where arguments about the power of human intuition and decision-making (which I often make) fall down. [Simple heuristics can make us smart](https://www.jasoncollins.blog/simple-heuristics-that-make-us-smart/). Developed in the right circumstances, [naturalistic decision-making](https://doi.org/10.1037/a0016755) can lead to good decisions. But where human decisions are inconsistent, or noisy, it is often unchallenging to identify better alternatives.

**Measuring noise**

One useful feature of noise is that you can measure it without knowing the correct or best decision. If you don't know your weight, it is hard to tell if the scale is biased. But the fact it differs in measurement as you get on, off, and on again points to the noise. If you have a decision for which there is a large lag before you know if it was the right one, this lag is an obstacle to measuring bias, but not for noise.

This ability to measure noise without knowing the right answer also avoids many of the debates about whether the human decisions are actually biased. Two inconsistent decisions cannot both be right.

You can measure noise in an organisation's decision-making processes by examining pairs of decision makers and calculating the relative deviation of their judgments from each other. If one decision maker recommends, say, a price of $200, and the other of $400, the noise is 66%. (They were $200 apart, with the average of the two being $300. 200/300=0.66). You average this noise score across all possible pairs to give you the noise score for that decision.

The noise score has an intuitive meaning. It is the expected relative difference if you picked any two decision makers at random.

In the HBR article, Kahneman and colleagues report on the noise measurements for ten decisions in two financial services organisations. The noise was between 34% to 62% for the six decisions in organisation A, with an average noise of 48%. Noise was between 46% and 70% for the four decisions in organisation B, with an average noise of 60%. This was substantially above the organisations' expectations. Experience of the decision makers did not appear to reduce noise.

**Reducing noise**

The main solution proposed by Kahneman and friends to reduce noise is replacing human judgement with algorithms. By returning the same decision every time, the algorithms are noise free.

Rather than suggesting a complex algorithm, Kahneman and friends propose what they call a "reasoned rule". Here are the five steps in developing a reasoned rule, with loan application assessment an example:
	
  1. Select six to eight variables that are distinct and obviously related to the predicted outcome. Assets and revenues (weighted positively) and liabilities (weighted negatively) would surely be included, along with a few other features of loan applications.

  2. Take the data from your set of cases (all the loan applications from the past year) and compute the mean and standard deviation of each variable in that set.

  3. For every case in the set, compute a “standard score” for each variable: the difference between the value in the case and the mean of the whole set, divided by the standard deviation. With standard scores, all variables are expressed on the same scale and can be compared and averaged.
	
  4. Compute a “summary score” for each case―the average of its variables’ standard scores. This is the output of the reasoned rule. The same formula will be used for new cases, using the mean and standard deviation of the original set and updating periodically.

  5. Order the cases in the set from high to low summary scores, and determine the appropriate actions for different ranges of scores. With loan applications, for instance, the actions might be “the top 10% of applicants will receive a discount” and “the bottom 30% will be turned down.”

The reliability of this reasoned rule - it returns the same outcome every time - gives it a large advantage over the human.

I suspect that most lenders are already using more sophisticated models than this, but the strength of a simple approach was shown in Robyn Dawes's classic article [The Robust Beauty of Improper Linear Models in Decision Making](http://psycnet.apa.org/doi/10.1037/0003-066X.34.7.571) ([ungated pdf](http://www.niaoren.info/pdf/Beauty/9.pdf)). You typically don't need a "proper" linear model, such as that produced by regression, to outperform human judgement.

As a bonus, improper linear models, as they are less prone to overfitting, often perform well compared to proper models (as per [Simple Heuristics That Make Us Smart](https://www.jasoncollins.blog/simple-heuristics-that-make-us-smart/)). Fear of the expense of developing a complex algorithm is not an excuse to leave the human decisions alone.

Ultimately the development of the reasoned rule cannot avoid the question of what the right answer to the problem is. It will take time to determine definitively whether it outperforms. But if the human decision is noisy, there is an excellent chance that it will hit closer to the mark, on average, that the scattered human decisions.
