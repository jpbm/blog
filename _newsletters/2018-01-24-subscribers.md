---
layout: newsletter
slug: 2018-01-24-subscribers
---

Hello!  In this week's newsletter, we discuss Gaussian processes, and the use of AI for social good.  We're also excited to share a little more about our new research report on Semantic Recommendations.

---

## Gaussian processes

Gaussian processes (GPs) are a powerful and flexible machine learning modeling
technique that learn a relationship between a continuous variable and an
observation. If the continuous variable is time, which it often is, [the data
being modeled is a time
series](http://rsta.royalsocietypublishing.org/content/371/1984/20110550.short).
Time series crop up all over the place (e.g. the weather, the price of a stock,
the number of visitors to a website, or the location of a robot's arm), so this
is a very powerful technique. GPs are so fundamental and powerful that the result of
applying them to the rate of births in the United States actually made the cover of
[one of the most famous textbooks in
statistics](http://www.stat.columbia.edu/~gelman/book/).

![]({{ site.github.url }}/images/2018/01/gp_births-1516741412077.png)
##### Births plot

In comparison to the zoo of traditional time series models popular in finance
and elsewhere ([ARIMA, GARCH, etc.](https://github.com/RJT1990/pyflux)), GPs
make few strong assumptions about the data; they are data driven. And perhaps
more importantly, the GP approach to modeling is probabilistic, which means
that its predictions come with estimates of uncertainties (the orange band in
the image is the GP prediction). [As we emphasized in _FF05:
Probabilistic
Programming_](http://blog.fastforwardlabs.com/2017/01/30/the-algorithms-behind-probabilistic-programming.html),
these uncertainties allow you to quantify risk, even when you have little
training data - and they're in
[scikit-learn](http://scikit-learn.org/stable/modules/gaussian_process.html)!

![]({{ site.github.url }}/images/2018/01/gp_sklearn-1516741529680.png)
##### GPs with scikit-learn

That's the good news. The bad news is that GPs are slow. Their exact and
general solution involves the inversion of a matrix, which is unavoidably (and
sometimes show-stoppingly) expensive (`O(n^3)` in computer science terms). But
if you're willing or able to relax the requirement that the solution be either
exact or general, new results mean that GPs become a practical modeling
approach for large datasets.

The current state-of-the-art inexact approach is [Variational Fourier Features
for Gaussian Processes](https://arxiv.org/abs/1611.06740)
([code](https://github.com/jameshensman/VFF)). The authors use a fast
approximation method very similar to the _variational_ methods we described as
the future in our [Probabilsitic Programming
report](http://blog.fastforwardlabs.com/2017/01/30/the-algorithms-behind-probabilistic-programming.html).
The speed-up is huge. On a well-known time series benchmarking dataset
describing [20 years of airline flight
delays](http://www.stat.purdue.edu/~sguha/rhipe/doc/html/airline.html), their
model finishes in under five minutes. (The previous record was 15 hours!)

For non-general solutions, there are lots of options. Most notably, if you're
dealing with 1D data (e.g. you're modeling a single stock rather than the
entire market) then the new and very well-documented
[Celerite](http://celerite.readthedocs.io/en/stable/) library is a great place
to start (and is being used right now to [learn about planets orbiting distant
stars](https://arxiv.org/abs/1706.05865))

![]({{ site.github.url }}/images/2018/01/gp_astro_alt-1516741587169.png)
##### GPs in astronomy

If your dataset is small (or you're just getting started with GPs), we
recommend [Chris Fonnesbeck's introductory
notebook](https://blog.dominodatalab.com/fitting-gaussian-process-models-python/).

---

## Artificial Intelligence for Social Good

As we mentioned in our newsletter last week, there can often be a bit of "hype" around AI, and sometimes that hype centers around what some might consider the "dangers" of ML/AI.  We will always agree that ethical considerations should be a priority in the development of new technology - but sometimes these conversations can feel a bit more "doom and gloom" than "exciting and hopeful."  That's why we were excited [to read about a new class](https://www.fastcodesign.com/90157255/you-can-now-take-a-class-on-how-to-make-ai-that-isnt-evil) that's being offered at CMU’s School of Computer Science this semester, "[Artificial Intelligence for Social Good](https://feifang.info/artificial-intelligence-methods-for-social-good-spring-2018/)," which aims to challenge students to think about how advanced AI and ML techniques could be used to solve practical world-wide problems.  There are a few example projects already up the [AI and Social Good website](https://sites.google.com/view/aiandsocialgood/), and we find them inspiring.  We hope more universities will consider adding classes like this to their machine learning curriculums.

On a somewhat related note, we came across a couple of really thought-provoking articles.  [This review](https://points.datasociety.net/beyond-the-rhetoric-of-algorithmic-solutionism-8e0f9cdada53) of a new book just released this week - [*Automating Inequality: How High-Tech Tools Profile, Police, and Punish the Poor*](https://www.amazon.com/exec/obidos/ASIN/1250074312/danah-20) - is a sobering reminder of how necessary it is that we continue the conversations around not just implementing automated solutions, but also around understanding the practical impact they will have. This is true in so many arenas - not just in social work, but also within the criminal justice system (for more on that, see [this article](http://www.sciencemag.org/news/2018/01/united-states-computers-help-decide-who-goes-jail-their-judgment-may-be-no-better-ours)) and in the issues surrounding the (sometimes inadvertent) [censorship of free speech](https://www.wired.com/story/free-speech-issue-tech-turmoil-new-censorship/) on social media platforms.

---

## Semantic Recommendations

Most recommendation systems do not understand what they are recommending. They work by i) finding users similar to you, ii) assuming you share the same item preferences, and iii) recommending to you the items that these users have liked.    

In our [latest blog post](http://blog.fastforwardlabs.com/2018/01/22/exploring-recommendation-systems.html) we share some challenges we encountered in building basic recommendation systems using two datasets (one from Flickr and one from Amazon). Both datasets contain historical rating information that users assigned to items (photos for Flicker and books for Amazon). Because each user only rates a small percentage of items available, historical interaction data is generally sparse. Our experiments show that basic recommendation systems which rely on this sparse data are unable to extract enough information to give good results. In addition, these systems are unable to recommend new items (this is known as the cold start problem) because they do not know who has interacted with them or the outcome of those interactions (as that information is not in the historical interaction data).     

![]({{ site.github.url }}/images/2018/01/recommendations-1516742153349.png)
                                                                                                     
Therefore, to make a better recommender, we built a system that understands what it is recommending by injecting content. (Please see [our blogpost](http://blog.fastforwardlabs.com/2018/01/22/exploring-recommendation-systems.html) for specific details.) This change not only resulted in a huge jump in performance, it also alleviated the cold start problem.

For more on building recommendation systems that can better understand content, be sure check out our new Semantic Recommendations report, which will be available shortly on [our client portal](https://clients.fastforwardlabs.com/)!           

--- 

## Job Postings

Here are a few job postings we've heard about recently: 

* **The Rockefeller Foundation** - Managing Director, Data Technology ([job description](https://www.rockefellerfoundation.org/about-us/careers/managing-director-data-technology/))
* **TD Ameritrade** - Senior Specialist, UI/UX Lead ([job description](https://jobs.tdameritrade.com/job/st-louis/senior-specialist-ui-ux-lead/1121/6333455))
* **Center for Court Innovation** - Project Manager, Technology ([job description](https://www.courtinnovation.org/careers/project-manager-technology))

We're always happy to share opportunities; please let us know if you have any you'd like for us to pass along.

---

## CFFL Updates

* The next Strata Data Conference is coming up in just a few short weeks in San Jose; Mike will be presenting on [Interpretable Machine Learning Products](https://conferences.oreilly.com/strata/strata-ca/public/schedule/detail/63572) on March 7th.
* Mike will also be speaking on interpretability at [Qcon.ai](https://qcon.ai/) on April 11th in San Francisco.
* Friederike was recently featured on [DataKind's blog](http://www.datakind.org/featured-volunteers/friederike-schuur) for her data science volunteer work.


As always, thank you for reading!  We welcome your thoughts, reactions, feedback, and suggestions anytime; just drop us a note at subscribers@fastforwardlabs.com.

Until next week,

The Cloudera Fast Forward Labs Team
