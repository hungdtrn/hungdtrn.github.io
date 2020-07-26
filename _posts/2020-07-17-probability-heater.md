---
layout: post
title: Probability made easy - How I chose a new heater in the middle of the pandemic
mathjax: true
---

People around the world may be enjoying the beautiful sunny of June summer, but for us in Australia, Winter is coming!. And like those people in Game of Throne, we expect this Winter to be one of the coldest. Lucky us, we are not invaded by the mighty Night King and his Night Walker army, but we know that we ain't safe either: the deadly Coronavirus has appeared out of the blue, and it has been hitting us so hard. Unfortunately, my heater has broken in the middle of the pandemic, and I need a new one. In this situation, going out to the shopping center is not a wise choice that I think I should better ordering the heater online. After spending time looking around, this is the one that I want to buy:

![Image heater](/images/2020-07-17-probability-heater/heater.png)

But here is the problem: there are lots of junk and garbages in Amazon these days, how could we know which is the right one to buy? One common thing that most people (including me) usually do before buying something online is finding what other people think about the product. However, reviews and ratings are not always accurate since we have different views and emotions about the same thing.

![Amazon comments](/images/2020-07-17-probability-heater/amazon.png)

As numbers are more reliable than feelings, there should be a numerical way that I could use to choose the new heater for embracing myself for the coldest Winter to come, and that is probability

### Probability: the logic of uncertainty

Specifically, let's denote the event that we are uncertain about, whether the heater is decent or not, as A. Then $$P(A)$$ is a number indicating my degree of belief in such event, which ranges from 0 (this heater is definitely crap) to 1 (this heater is definitely a decent heater).We want to somehow compute this number from the comments and feedback from online users on Amazon. Using the law of total probability, we have:
$$P(A)=P(A|positive feedback)P(positive feedback) + P(A|negative feedback)P(negative feedback),$$
Where P(positive feedback) and P(negative feedback) are the probability of positive and negative feedbacks on the product website, we have $$P(positive feedback) + P(negative feedback) = 1$$. Given a feedback on amazon, how can we decide if it is positive or negative?. There is a whole line of research called sentimental analysis that aim to answer such question. However, for simplicity, a feedback is considered positive if it has at least 3 in 5 stars and negative otherwise. 

![Amazon stars](/images/2020-07-17-probability-heater/stars.png)

From the website, we have $$P(positive feedback)=P(5 stars) + P(4 stars) + P(3 stars)=89%$$, $$P(negative feedback)=1 - 89% = 11%$$. Hence, we have

$$P(A)=P(A|positive feedback) \cdot 0.89 + P(A|negative feedback) * 0.11$$

The remaning part of the formula, P(A|positive feedback) and P(A|negative feedback) are conditional probabilities, the perfect tool that we use to update our probability number. Specifically.