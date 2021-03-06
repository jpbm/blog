---
layout: newsletter
slug: 2018-02-22-subscribers
---

Hello, and happy Thursday!  In this week's newsletter, we discuss Quantum Computing and Deep Forests, and also share a few links to articles we've enjoyed reading.

---

## Quantum Computing
Quantum computing has the potential to solve problems that are intractable (read: take too long) for classical computers. Classical computing stores information using bits. Each bit can be in one of two states, 0 or 1. In quantum computing, information is encoded using qubits. One qubit can be a 0, 1, or both at once. This is known as the **superposition** property - with superposition, a qubit can be in a linear combination of state 0 and state 1 (hence, both at once). Qubits can also be **entangled**, meaning that the state of one qubit cannot be described independently of the state of the other, even when they are physically far away from each other. Entanglement allows multiple states to be acted on simultaneously and is responsible for much of quantum computing's extra power.                                                                                               
                                                                                                     
The classic algorithm used to illustrate the power of quantum computing is [Shor's algorithm for integer factorization](https://en.wikipedia.org/wiki/Shor%27s_algorithm). In the factorization problem, given an integer *N* = *p x q* for some prime numbers *p* and *q*, our task is to determine *p* and *q*. The best classical algorithm runs in exponential time while Shor's algorithm runs in polynomial time, substantially faster! Given that the widely used RSA public-key cryptosystem (to protect credit card information for example) relies on the hardness of integer factorization, Shor's algorithm suggests that large quantum computers can easily attack such a system. So, how far are we from this scenario?                                         
                                                                                                     
Quite far, it turns out. The largest number factored on a quantum device is [56153 using 4 qubits](https://arxiv.org/pdf/1411.6758.pdf) in 2014. In November 2017, IBM announced that it is releasing a 20 qubit quantum computer as a [cloud service](https://quantumexperience.ng.bluemix.net/qx/devices). This is in addition to the 5 qubit device released 18 months prior. IBM also announced that researchers have successfully built a 50 qubit prototype. 50 qubits is a significant milestone because that is beyond what can be simulated by brute force using the most powerful existing digital supercomputers. John Preskill coined the term ["NISQ(Noisy Intermediate-Scale Quantum)"](https://arxiv.org/abs/1801.00862) to describe this pivotal new era in quantum technology, where quantum computers with a number of qubits ranging from 50 to a few hundred will be available in the next few years. He also points out that a larger number of qubits imply more processing power, but these qubits also need to be of high quality. The best error rate now for two-qubits gates is around 0.1%; for circuits with more than 1000 gates, the noise will overwhelm the signal. In addition, because of the entanglement property, more qubits interacting together could result in even higher error rates! Quantum error correction can be used to scale up larger circuits, but it imposes a heavy overhead cost in number of qubits and number of gates and thus is less likely to be used in the NISQ era. It might be a long time before we have a fault-tolerant quantum computer solving hard problems, but huge strides are being made!                                                                 

---

## Deep Forests

For a long time, deep learning has dominated the machine learning world in terms
of its ability to do representational learning. In representational learning,
models learn new ways of encoding the data they are being shown into something that
fits the problem at hand better. So, for example, for image recognition we can
see that [convolutional
networks](https://ujjwalkarn.me/2016/08/11/intuitive-explanation-convnets/) are
learning to perform various types of corner and edge detection first, before attempting
to classify what it sees in the images.

However, the National Key Lab for Novel Software Technology from Nanjing
University has come out with an interesting way to bring this ability to other
types of models. ["Deep Forests"][1] is what they call their mechanism to learn
an ensemble of ensemble methods. They even provide an [open source package][4]
with a full implementation of the method.

The extremely simplified explanation of their method is that they take their
input data, feed it through many ensemble models, concatenate all the outputs of
those models with the original data and then feed _this_ to another group of
ensemble methods. The number of layers of this process grows with the algorithm's
ability to get better, which means that we don't need to spend time figuring out
how many layers we need (which is a general hardship with neural networks).

![](images/deepforests.png)

The result is a model with fewer hyper-parameters than its neural network
equivalent that can be trained in parallel. In the experiments shown in [their
paper][1], they even show better results than neural networks! It's interesting
to see this level of performance from a system that isn't differentiable, since 
[Stochastic gradient descent][3] has been such an important part of machine
learning for decades now, even outside of neural networks.

It remains to be seen how well this model performs on other datasets and what sort
of generalization it can produce. In addition, while neural networks can be a
pain to train, they are very fast to evaluate (especially given all of the
specialty hardware created especially for this), so it'll be interesting to see
how deep forests compare in that regard. Furthermore, we think that more work
needs to be done towards understanding how this model overfits, and how the potentially
unbounded growth in the number of parameters the model uses affects the results.

This is definitely an interesting model and one we'll be keeping an eye on!

[1]: https://arxiv.org/abs/1702.08835
[2]: https://ujjwalkarn.me/2016/08/11/intuitive-explanation-convnets/
[3]: https://en.wikipedia.org/wiki/Stochastic_gradient_descent
[4]: https://github.com/kingfengji/gcForest

---

## CFFL Recommended Reading

Be sure to check out this post on our blog:
* [Probabilistic Cookies!](http://blog.fastforwardlabs.com/2018/02/14/probabilistic-cookies.html)  
* as well as this post by Seth Hendrickson on Cloudera's Engineering Blog, [Production Recommendation Systems with Cloudera](http://blog.cloudera.com/blog/2018/02/production-recommendation-systems-with-cloudera/)

We love to read; here are a few of our (notably eclectic) favorite finds from this month:
* [A Code of Ethics for Data Science](https://medium.com/@dpatil/a-code-of-ethics-for-data-science-cda27d1fac1)
* [Quantum algorithms: an overview](https://blog.acolyer.org/2018/02/06/quantum-algorithms-an-overview/)
* [Quantum computing in the NISQ era and beyond](https://blog.acolyer.org/2018/02/05/quantum-computing-in-the-nisq-era-and-beyond/)
* [All The Cool Kids, How Do They Fit In?: Popularity and Demographic Biases in Recommender Evaluation and Effectiveness](http://proceedings.mlr.press/v81/ekstrand18b.html)
* [Datasette: instantly create and publish an API for your SQLite databases](https://simonwillison.net/2017/Nov/13/datasette/)
* [Candy Heart messages written by a neural network](http://aiweirdness.com/post/170685749687/candy-heart-messages-written-by-a-neural-network)
* and last, but not least, [Finally, Facial Recognition for Cows Is Here](https://gizmodo.com/finally-facial-recognition-for-cows-is-here-1822609005)!

![]({{ site.github.url }}/images/2018/02/b8bzwnjho4eyv0xk7vvi-1519303932664.png)
##### This is actually more useful than one might think. ([image source](https://gizmodo.com/finally-facial-recognition-for-cows-is-here-1822609005))

---

## Job Postings

Come work with us!  In addition to several other [open positions](https://www.cloudera.com/careers/careers-listing.html), **Cloudera** is hiring a **Director of Product Management, Data Science** ([job description](https://cloudera.wd5.myworkdayjobs.com/External_Career/job/USA--California--Palo-Alto/Director-Product-Management--Data-Science_180286)).

Here a couple of other positions we've heard about as well:
* **Silectis** - Data Engineer ([job description](https://www.silect.is/careers-data-engineer))
* **Silectis** - Platform Engineer ([job description](https://www.silect.is/careers-platform-engineer))

---

## CFFL Updates

* Hilary will be speaking on March 7th at the [Strata Data Conference](https://conferences.oreilly.com/strata/strata-ca/) in San José, and Mike will be presenting on [Interpretable Machine Learning Products](https://conferences.oreilly.com/strata/strata-ca/public/schedule/detail/63572) at Strata on March 7th, as well.

* Brian will be speaking at the [Cloudera Sessions](https://www.cloudera.com/more/events/sessions/sao-paulo.html) event in São Paulo on March 13th.

* Mike will be speaking on interpretability at [Qcon.ai](https://qcon.ai/) on April 11th in San Francisco.

* Also, be sure to catch Mike in conversation with Hugo Bowne-Anderson about interpretability on DataCamp's podcast, [DataFramed](https://soundcloud.com/dataframed/9-data-science-and-online-experiments-at-etsy#t=17:10), with another conversation about probabilistic programming coming soon, too!

As always, thank you for reading. We welcome your thoughts, feedback, and suggestions; please drop us a note anytime at clients@fastforwardlabs.com.

Until next week,

The Cloudera Fast Forward Labs Team
