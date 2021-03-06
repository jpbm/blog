---
layout: newsletter
slug: 2017-11-28-subscribers
---

Hello!

A free internet will always be filled with competing narratives. Data, research, and dialogue can help us cut through the online static and establish a shared truth. Jeff Kao used natural language processing to [analyze net neutrality comments](https://hackernoon.com/more-than-a-million-pro-repeal-net-neutrality-comments-were-likely-faked-e9f0e3ed36a6) submitted to the FCC from April to October 2017: less than 800,000 of the 22M+ comments can be considered truly unique (and more than 99% of the unique comments appear to be in favor of net neutrality).

Meanwhile, Bob Lutz, former vice chairman and head of product development at General Motors, muses about a future alongside and inside [mobility pods](http://www.autonews.com/article/20171105/INDUSTRY_REDESIGNED/171109944/bob-lutz:-kiss-the-good-times-goodbye), an imaginative piece shared widely over the last couple weeks, that makes us think of Rodney Brooks' excellent piece on the [Unexpected Consequences of Self Driving Cars](https://rodneybrooks.com/unexpected-consequences-of-self-driving-cars/). (Engineers think about edge cases.)

In this week's newsletter, we take an in-depth look at CNNs applied, not to images, but text. If neural networks can find new ways to be in the world, perhaps, so can we. In the second part of this newsletter, we add a note on creating a welcoming Slack for all. (We are determinedly hopeful.) And finally, we share what low-wattage light bulbs tell us about gentrification.

---

## Convolutional neural networks for natural language data

From self-driving cars to cancer detection, convolutional neural networks (CNNs) were responsible for major breakthroughs in the field of computer vision. A CNN is a neural network that uses (in place of general matrix multiplication), the bread and butter of neural networks: a convolution in at least one of its layers, often in conjunction with [pooling operations](http://ufldl.stanford.edu/tutorial/supervised/Pooling/). 

A convolution is a function that takes an input and maps it to an output. It acts like a sliding filter applied to a matrix with a set of trainable weights that, combined with the input, produces the output.

![]({{ site.github.url }}/images/2017/11/Convolution_schematic-1511385074732.gif)

##### A convolution with a 3 x 3 filter in action (Image Credit: http://deeplearning.stanford.edu/wiki/index.php/Feature_extraction_using_convolution).

Neural networks with convolutions are specialized for processing data with known grid-like topology. They are the go-to approach for image data: images are 2-D grids of pixels (3-D in case of color images). Recently, we have seen CNNs applied to text data.

A sentence is an ordered sequence of words: spoken or written language is data characterized by its *sequential nature*. Recurrent neural networks (RNNs), much like CNNs, are a specialized neural network for processing sequential data: a perfect fit for natural language data. 

So why do we see the application of CNNs to text?

A text document is an ordered sequence of sentences. A sentence is an ordered sequence of words. Using [word embeddings](https://blog.acolyer.org/2016/04/21/the-amazing-power-of-word-vectors/), we can represent each word as a vector, a sequence of numbers. For a 5-sentence document with 10 words per sentence and a 100 dimensional word embedding, we can construct a representation of the document with the dimensions 50 x 100, a grid-shaped input - our "image" for the CNN.

In computer vision, convolutions slide over local patches of the image. Applied to text documents, the size of the convolution is set such that it slides over full rows, i.e., entire words (each row is the word embedding of a single word). The size of the filter can vary; 2 to 5 words is typical. 

Since the weights of the convolution operation are learned during training, combined with max-pooling (an operation that selects the maximal value from the output of the convolution operation), the neural network learns which word combinations are the most useful for mastering a task at hand, e.g., document classification: CNNs automatically and flexibly determine which n-grams to use. 

Compared to n-grams (in traditional bag-of-word approaches), CNNs are efficient in their representation and compared to RNNs, CNNs are fast (i.e., easier to parallelize) and often easier to train. 

CNNs applied to text are promising. For an introduction, we recommend Denny Britz's post [Understanding Convolutional Neural Networks for NLP](http://www.wildml.com/2015/11/understanding-convolutional-neural-networks-for-nlp/) and his [TensorFlow CNN implementation for sentiment classification on movie review data](http://www.wildml.com/2015/12/implementing-a-cnn-for-text-classification-in-tensorflow/).

### The challenge of long-range dependencies in natural language

One of the challenges of working with natural language data is "long-range dependencies." For example:

*> I grew up in a small village on the coast of Italy in a large family, with three older brothers and one younger sister. I speak fluent ...*

While it is easy for a human to predict the final word of the sentence, algorithms struggle (there are 15 words in between 'Italy', the clue, and the missing word in question). There are two primary mechanisms for CNNs to cope with long-range dependencies:

 - Neural network depth
 - Dilated or atrous convolutions
 
#### Neural network depth

CNNs with many layers are able to learn more abstract features. At the same time, layers further removed from the input have a larger receptive field - that is, they have access to information across an image or different parts of a document (through the intermediate layers). (For the curious, we recommend [this guide for understanding and calculating receptive field size](https://medium.com/@nikasa1889/a-guide-to-receptive-field-arithmetic-for-convolutional-neural-networks-e0f514068807).)

Consequently, they can detect, utilize, and cope with long-range dependencies in language data. Take a look at the paper [Very Deep Convolutional Networks](https://arxiv.org/abs/1606.01781) for Text Classification by Conneau and colleagues, a CNN with 29 (!) convolutional layers. Related, to cope with the vanishing (or exploding) gradient problem that plagues very deep nets, we recommend the the post [ResNets, HighwayNets, and DenseNets, Oh My!](https://chatbotslife.com/resnets-highwaynets-and-densenets-oh-my-9bb15918ee32).

#### Dilated or atrous convolutions 

Dilated or atrous convolutions are convolutions with holes - another method for increasing receptive field size. 

![]({{ site.github.url }}/images/2017/11/atrous_conv-1511388987584.png)

##### A 3x3 convolution "filter" with a dilation of 1, 2, and 3 (left to right). Receptive field size increases from left to right. (Image taken from [Tal Perry's excellent post on CNNs for text](https://medium.com/@TalPerry/convolutional-methods-for-text-d5260fd5675f).)

There are many more tricks in the CNN bag for natural language - too many to cover in this newsletter. CNN vs. RNN: in the end, it still depends on the task you're looking to solve, as [this paper demonstrates](https://arxiv.org/abs/1702.01923). 

CNNs: no longer only for image data.

---

## A note on effective, efficient, well-functioning teams and sexist Slack

Diverse teams produce [better results](https://www.scientificamerican.com/article/how-diversity-makes-us-smarter/): being around people who are different from us makes us more creative, more diligent, and harder-working. Consequently, we should all be striving towards creating and actively maintaining diverse teams. 

Some behavior patterns that discourage minorities from becoming, feeling part of, and feeling comfortable contributing to teams are subtle, hard to detect, and pernicious. 

In the article [Your company's Slack is probably sexist](https://work.qz.com/1128150/your-companys-slack-is-probably-sexist/) by Leah Fessler, the author analyzes interactions on the popular messaging platform Slack. We found it to be a good read (and confrontational in a very postive way) that hopefully can help bring to light, and then eradicate, some of the behavior patterns that currently are, in part, responsible for under-performing teams.

![]({{ site.github.url }}/images/2017/11/unconcious_bias1-1511390001877.jpg)

##### A conversation between Alix and M(an). Reading this exchange, you might not notice anything wrong. That’s how unconscious biases and microaggressions work. (Taken from Quartz article on [sexist communication patterns in Slack](https://work.qz.com/1128150/your-companys-slack-is-probably-sexist/).)

Diversity is in *everybody's* best interest. (Probably a good reminder: also follow the ["no asshole rule"](https://hbr.org/2007/03/why-i-wrote-the-no-asshole-rule) (a technical term and therefore entirely workplace appropriate) or - in "tech speak" - the ["no brilliant jerks in engineering" rule](http://www.brendangregg.com/blog/2017-11-13/brilliant-jerks.html).)

---

## Surprising correlates

Where there is money, there are vintage light bulbs. Most Westeners expect dim lights in fashionable restaurants, according to [City Lab](https://www.citylab.com/). *Solid-state Edison bulbs epitomize our tangled obsessions with both technology and an imagined urban past.*

Consequently, the presence of vintage light bulbs is a surprisingly [good proxy for measuring gentrification](https://www.citylab.com/design/2017/10/mapping-the-edison-bulbs-of-brooklyn/543738/).

![]({{ site.github.url }}/images/2017/11/vintage_light_bulbs_gentrification-1511390625830.png)

##### Image Credit: [City Labs](https://www.citylab.com/design/2017/10/mapping-the-edison-bulbs-of-brooklyn/543738/).

---

## Jobs, Jobs, Jobs

Come work with us!  We're hiring a Research Engineer ([job description](https://cloudera.wd5.myworkdayjobs.com/External_Career/job/USNew-YorkBrooklyn/Research-Engineer_171058))

And here are a few other jobs we've heard about:

* **NYC Mayor's Office of Operations** - Chief Analytics Officer ([job description](http://www1.nyc.gov/assets/operations/downloads/pdf/employment-opportunities/chief-analytics-officer-job-description-vf.pdf))
* **Elucd** - Data Scientist ([job description](https://jobs.lever.co/elucd/7a251473-f3a7-40f6-b97c-c10c8838d316))
* **USA for UNHCR** - Data Scientist ([job description](https://www.linkedin.com/jobs/view/503624429/))
* **Dark Sky** - Data Scientist ([job description](https://darksky.net/jobs))

---

## CFFL Updates

* Friederike will be on a panel at [NIPS](https://nips.cc/) next week (on 12/6), discussing "Applied AI careers in industry" (alongside representatives from Google Brain and Salesforce Einstein); if you'd like an invitation to a reception following the panel, please do [reach out](mailto: friederike@cloudera.com).

* Brian will be presenting at the [Cloudera Sessions](http://go.cloudera.com/cloudera-sessions-2017-london) in London on 12/12, as well.

Thank you for reading!  We'd love to hear your thoughts - please feel free to reach out any time to subscribers@fastforwardlabs.com.

-- The Cloudera Fast Forward Labs Team
