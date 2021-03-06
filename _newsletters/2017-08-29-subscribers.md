---
layout: newsletter
slug: 2017-08-29-subscribers
---

Hello!

A shock collar to train your Roomba? Deep reinforcement learning allows agents to learn based on trial and error, reward and punishment. A new [review paper](https://arxiv.org/abs/1708.05866) recaps the achievements in the field.

![xkcd deep learning cartoon]({{ site.github.url }}/images/2017/08/drone_training-1503941734848.png)

##### XKCD aptly summarizes the promise of [deep reinforcement learning](https://arxiv.org/abs/1708.05866).

Not only for the fashion conscious engineer, it's time to retire the MNIST data. The fashion retailer Zalando open-sourced a [data set](https://github.com/zalandoresearch/fashion-mnist) to benchmark your machine learing algorithms; turns out MNIST has become too easy. 

Before we go on to our newsletter — with recommended reading on Bayesian inference and probabilistic programming, thoughts on AI and national security, and the enduring legacy of Zork — a quick announcement. 

---

## The Future of the Individual Subscribers Program

Thank you very much for signing up and providing thoughts for our Individual Subscribers beta program this summer - please do complete the feedback form [here](https://docs.google.com/forms/d/e/1FAIpQLScAil6KZ99nL457a32n_Hq5c8cfqaEbvvDXN6RHoeJQ7T0_sw/viewform); we’d love to get your ideas on how to help the program grow.

We will be continuing the program and opening up the individual subscription program open to the public next week!  Because of your beta participation you will receive 50% off pricing for the first year, and early access, beginning this coming Friday.  Stay tuned for an email from us with details on registration later this week!

---

## Bayesian Inference & Probabilistic programming: further reading

Bayesian inference allows you to encode expert opinion and rich domain knowledge into your models. In contrast to deep learning, it allows you to make use of small, disparate data, and naturally provides estimates of risk and uncertainty in your predictions (i.e., a measure of the confidence in your estimates), which is a superpower in industries like finance, insurance, and commerce (to name just a few of the [many advantages](http://blog.fastforwardlabs.com/2017/01/30/the-algorithms-behind-probabilistic-programming.html) of Bayesian inference).

Earlier this year, we launched a research report on [probabilistic programming](http://blog.fastforwardlabs.com/2017/01/18/new-research-on-probabilistic-programming.html), an emerging programming paradigm that makes it easier to construct and fit Bayesian models in code. It’s advanced statistics, simplified for data scientists looking to build models fast. 

If that sounds great to you, and you're looking to learn more, the first thing you can do is — check out our report in the [client portal](http://clients.fastforwardlabs.com/login/?next=/)! You might also enjoy this list of our favorite resources for learning how to do Bayesian inference and build probabilistic programming systems.

### Practical books
If you're just starting out then we recommend either [Doing Bayesian Data Analysis](https://sites.google.com/site/doingbayesiandataanalysis/) by John Kruschke, or [Probabilistic Programming and Bayesian Methods for Hackers](http://camdavidsonpilon.github.io/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/) by Cameron Davidson-Pilon. Krushke's book uses R and Stan (and a teaching language called JAGS). Davidson-Pilon uses Python and PyMC. Choose between these books based on your language preferences. If you don't have a language preference, we at Fast Forward Labs recommend Davidson-Pilon's book, and in particular [the free, online-only PyMC3 edition](https://github.com/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers) (there are some important differences between PyMC3 and previous versions).

### Theoretical books
The practical books above cover the basics of the theoretical and mathematical side, but if you'd like a deeper dive, we
recommend [Data Analysis: A Bayesian Tutorial](https://global.oup.com/academic/product/data-analysis-9780198568322?cc=us&lang=en&) by Sivia and Skilling. It's a short, extremely clear book. If your background is in economics or life sciences, you may prefer [Data Analysis Using
Regression and Multilevel/Hierarchical Models](http://www.stat.columbia.edu/~gelman/arm/) by Gelman and Hill. If your background is in physics or engineering, you may prefer [Principals of Data Analysis](http://www.physik.uzh.ch/~psaha/pda/) by Prasenjit Saha (which is available for free online).

### Research
If you'd like a reading list of research papers, there is no better place to start than the _excellent_ [annotated bibliography](https://psyarxiv.com/ph6sw/) published last year by Alexander Etz and colleagues. Etz's notes place the research in a historical and conceptual context, so this is in a sense the _least_ technical document in our list of next steps. If you're interested in the algorithmic cutting edge (Hamiltonian Monte Carlo, variational methods, etc.), then we have [a blog post that links to a selection of important papers](http://blog.fastforwardlabs.com/2017/01/30/the-algorithms-behind-probabilistic-programming.html).

### Tutorials and articles
Finally, here are a selection of shorter and/or use-case-specific practical articles we've found interesting and useful:

 - [Bayesian Survival Analysis in Python with PyMC3](http://austinrochford.com/posts/2015-10-05-bayes-survival.html), and
   indeed any of the [posts on Austin Rochford's blog](http://austinrochford.com/posts.html)
 - [Parameter estimation for text analysis](http://www.arbylon.net/publications/text-est.pdf) by Gregor Heinrich, which is first and foremost a great topic modeling tutorial, but almost accidentally a great introduction to Bayesian inference
 - [Data analysis recipes: Fitting a model to data](https://arxiv.org/abs/1008.4686) by Hogg and colleagues, a deep article about an extremely simple problem (linear regression) that somehow also manages to be funny!

---

## AI opportunities live outside the box

[AI Could Revolutionize War as Much as Nukes](www.wired.com/story/ai-could-revolutionize-war-as-much-as-nukes) -- a  Wired headline covering the recent [Artificial Intelligence and National Security Report](www.belfercenter.org/sites/default/files/files/publication/AI%20NatSec%20-%20final.pdf) by the Belfer Center for Science and International Affairs at Harvard's Kennedy School of Government.

The Belfer Center purports to comment on how AI growth is expected to affect military, information, and economic "superiority." However, the offered guidance is strictly focused on the traditional players in national security, DoD and the Intelligence Community (with brief nods to the State Department and NIST), and [areas](https://www.nytimes.com/2016/10/26/us/pentagon-artificial-intelligence-terminator.html) where these players are [already active](http://www.businessinsider.com/the-pentagon-wants-at-least-12-billion-to-fund-ai-weapon-technology-in-2017-2015-12). While the paper sets forth an admirable pathway for the government's traditional foreign policy elements to prepare for hostile, technology-driven, overt engagement, there is more room available to secure the country against the impacts, threats, and challenges of AI -- whether malicious and intentional or not -- by proactively supporting the US academic and commercial sectors, currently most directly engaged in the new "AI battle space."

The government could define policies regarding the in vivo testing of fully-automated surgical robotics systems, for example, [robot arms can be hacked](https://www.wired.com/2017/05/watch-hackers-sabotage-factory-robot-arm-afar/), with joint Department of Commerce/Health and Human Services SBIR grants for their development. Similarly, development of legal and financially focused document translation systems should be incentivized to help companies expand their offerings globally. The Department of Justice, again with Commerce, needs investment in ways to deal with the unprecedented scope and [scale]( https://www.bloomberg.com/news/articles/2017-08-08/china-to-spend-1-5-trillion-on-outbound-m-a-in-a-decade-report) of threats to data.

![undersea robot installing an internet cable]({{ site.github.url }}/images/2017/08/undersea_cable-1503941863405.jpeg)

##### Chinese tech presents risks for US cybersecurity, making its way into consumer products, but also exposing the vulnerabilities of the [infrastructure](www.usni.org/magazines/proceedings/2017-07/chinas-cyber-economic-warfare-threatens-us) US commerce depends on.

*"Most AI research advances are occurring in the private sector and academia,"* and to be sure, the government's technology development initiatives like the agile Intelligence Community investment arm, [In-Q-Tel](www.iqt.org), can lead in accessing emerging data, machine learning, and AI systems. However, the biggest players in AI today are private companies who have access to and can work with incredible volumes of data that allows them to build superior (data) products. In the US, [no public-sector entity can touch](https://research.googleblog.com/2017/07/revisiting-unreasonable-effectiveness.html) Facebook, Alphabet, Amazon, Microsoft; nor do they compare favorably with [Baidu](www.wired.com/story/how-baidu-will-win-chinas-ai-raceand-maybe-the-worlds), TenCent, and Alibaba in China, or with NTT in Japan.

The federal government should think well beyond DoD and traditional foreign policy elements and focus on how to best invest in and collaborate with existing players, academic and commercial, when considering the future security of the US.

---

## Zork's lessons

The MIT Technology Review has published a welcome [encomium](https://www.technologyreview.com/s/608670/the-enduring-legacy-of-zork/) to Zork, the text-based adventure game some of us fondly remember playing off of a 5.25-inch floppy disk, back in the day. Ahead of its time in many ways, even when paying homage to Tolkein or romanticizing Depression-era hydrological projects, Zork still offers lessons for working with natural language. Originally written in [ZIL](https://bitbucket.org/jmcgrew/zilf/wiki/Home) (Zork Implementation Language, based on LISP) and run on an MIT mainframe, Zork's designers developed their own rules-based text parser for game play. Rules-based natural language parsers, like the one used by Zork, were supplanted by [statistical parsers](https://nlp.stanford.edu/software/lex-parser.shtml) around the time that text-based games disappeared, but one lesson the authors of the article draw from Zork is the way game design played to the weaknesses of rule-based parsers.

![screen shot of Zork]({{ site.github.url }}/images/2017/08/zork_gameplay-1503941929278.jpeg)

##### Rich descriptions and context afforded players hints as to how to type commands that were more likely to be correctly parsed. Given the description, a player's options for interacting with the game become more clear ("go east", "climb tree"). 

Chatbot designers have taken these lessons to heart, bolding key action words in text responses and scaffolding interactions so that the interactions seem open, while options for the user are more easily discerned. One other interesting element of Zork's design: because it was originally played on that mainframe at MIT, the designers could actually watch players type commands in real-time. When they noticed a common command that the parser couldn't handle, they could update the parser with a synonym. Slower than adding to a corpus of training-data for a DNN, sure, but given they were leveraging a networked computing capability that only became possible again 20 years later, it's impressive.

Infocom open-sourced the game back in the early 90's, so now you can [play](https://classicreload.com/zork-i.html) a browser-based version!

---

## Jobs, Jobs, Jobs

Here are a couple of job opportunities for data scientists:

**Enigma** - Data Scientist ([job description](https://www.enigma.com/careers/data-scientist))
**Crisis Text Line** - Machine Learning Data Scientist ([job description](https://crisistextline.workable.com/j/6B5C231A62))

We're always happy to share opportunities we hear about; please let us know if you have any you'd like for us to pass along.

---

## FFL Updates

We're giving talks at some upcoming conferences:
- [Nexterday North 2017](http://www.businesswire.com/news/home/20170824005127/en/Nexterday-North-2017-Re-Invents-Core-Digital-Communications): September 20 **(Helsinki, Hilary)**
- [Strata Data Conference](https://conferences.oreilly.com/strata/strata-ny): September 28 **(New York, Hilary)**

We're also very excited about our upcoming webinar on Machine Learning and Interpretability; you can register [here](https://splashthat.com/sites/view/mlinterpretability.splashthat.com).

Thank you for reading.  We'd love to hear your thoughts! You can reach us anytime at subscribers@fastforwardlabs.com. 

— The Fast Forward Labs Team
