---
layout: post
title:  "ACL in Berlin"
date:   2016-08-20 14:55:35 -0700
categories: jekyll update
---

The ACL this year was great. Though there were too many parallel sessions at times and though I had to spend some time preparing/changing my own talk, I still managed to attend some really great talks.

Overarching themes: Distributional semantics was a big thing this year. This could be subjective, based on the sessions and talks I attended.

Finally, this ACL was a strong indicator that the community is thinking about gender diversity. We’re lucky as NLP researchers to have more women interested, but there are still milestones to achieve. ACL encouraged a lot of women speakers. I met a lot of great women in NLP - Sharon Goldwater, Emily Bender, Animashree Anandkumar and had one of the best brainstorming sessions with Yejin Choi. Personally, it makes a big difference to me when I see these great women, because I can relate to them and it reaffirms my faith in my own decision to join this field. It was so fun watching them nerd out about their favorite topics(something I kind of miss about CMU, everyone is always nerding  it out).

---

## Day 1 : 8th Aug

### Keynote Talk 1: Amber Boydstun

Framing in politics and statistical analysis of change in public opinion based on agenda-driven speech. The challenge presented to the NLP audience was the following: can we automatically detect these trends? Got me thinking - we are barely scratching the surface of what can be potentially useful applications for humanity as a whole. So much potential for NLP, yay for the future.

### Session 1

* [Noise reduction and targeted exploration in imitation learning for Abstract Meaning Representation parsing](https://aclweb.org/anthology/P/P16/P16-1001.pdf)
    - James Goodman, Andreas Vlachos and Jason Naradowsky

    Explained the concepts behind roll-in and roll-out. Glad they selected AMR parsing. SEARN and DAgger-style algorithms for doing similar kinds of search during training and testing.

* [Generalized Transition-based Dependency Parsing via Control Parameters](https://www.aclweb.org/anthology/P/P16/P16-1015.pdf)
    - Bernd Bohnet, Ryan McDonald, Emily Pitler and Ji Ma

    Completely blanking out on this talk. //todo: read abstract and possibly the paper to summarize.

* [Learning the Curriculum with Bayesian Optimization for Task-Specific Word Representation Learning](https://www.aclweb.org/anthology/P/P16/P16-1013.pdf)
    - Yulia Tsvetkov, Manaal Faruqui, Wang Ling, Brian MacWhinney and Chris Dyer

    Instead of having a random order of examples, learn the best order from samples provided. This is curriculum learning, where the curriculum is controlled by specific hyper parameters, which are learnt using Bayesian optimization. They demonstrate results on multiple tasks, including parsing, which is cool and not seen so often.

* [Named Entity Recognition with Bidirectional LSTM-CNNs](http://arxiv.org/abs/1511.08308) (TACL)
    - Jason P.C. Chiu and Eric Nichols

    Boring.

### Session 2

- [Active Learning for Dependency Parsing with Partial Annotation](http://www.aclweb.org/anthology/P/P16/P16-1033.pdf)
    * Zhenghua Li, Min Zhang, Yue Zhang, Zhanyi Liu, Wenliang Chen, Hua Wu and Haifeng Wang

    Blanking out on this one.

- [Morpho-syntactic Lexicon Generation Using Graph-based Semi-supervised Learning]() (TACL)
    * Manaal Faruqui, Ryan McDonald and Radu Soricut

    Started with a small sample lexicon and extended it to a large corpus using projection. Seems practically useful.

- [News Citation Recommendation with Implicit and Explicit Semantics](http://www.aclweb.org/anthology/P/P16/P16-1037.pdf)
    * Hao Peng, Jing Liu and Chin-Yew Lin

    Went to check out the newest ARK member, he seems to be doing very well, he’s prepared for what’s to come!

- [Document-level Sentiment Inference with Social, Faction, and Discourse Context](http://www.aclweb.org/anthology/P/P16/P16-1029.pdf)
    * Eunsol Choi, Hannah Rashkin, Luke Zettlemoyer and Yejin Choi

    Theories about relationships between entities, like friends of enemies are enemies, were empirically justified from text data. Involved complex annotation schemes and guidelines (I annotated!)

### Session 3

- [Multilingual Projection for Parsing Truly Low-Resource Languages]() (TACL)
    * Željko Agić, Anders Johannsen, Barbara Plank, Héctor Martínez Alonso, Natalie Schluter and Anders Søgaard


    Same style of projection as was used by Dipanjan and others at Google.

- [Combining Natural Logic and Shallow Reasoning for Question Answering](http://www.aclweb.org/anthology/P/P16/P16-1042.pdf)
    * Gabor Angeli, Neha Nayak and Christopher D. Manning


    clever trick which he proved using a sample logic puzzle, nice talk

- [Many Languages, One Parser]() (TACL)
    * Waleed Ammar, George Mulcaire, Miguel Ballesteros, Chris Dyer and Noah A. Smith

    may be not really low resource, as per Emily Bender

- [Unsupervised Part-Of-Speech Tagging with Anchor Hidden Markov Models]() (TACL)
    * Karl Stratos, Michael Collins and Daniel Hsu

    anchor HMMs, good but do the properties generalize?

- [Multi-lingual dependency parsing evaluation: a large-scale analysis of word order properties using artificial datai]() (TACL)
    * Kristina Gulordava and Paola Merlo

    the talk was painful to watch

---

## Day 2 : 9th Aug

### Keynote talk 2: Mark Steedman

Collocational vs denotational paradigms of distributional semantics.

Collocational semantics is what word vectors are all about.
Denotational semantics equates to logical semantics, building knowledge graphs, etc.

---

## Day 3 : 10th Aug

### Outstanding Papers Session I and II

- [A Thorough Examination of the CNN/Daily Mail Reading Comprehension Task](http://www.aclweb.org/anthology/P/P16/P16-1223.pdf)
    * Danqi Chen, Jason Bolton and Christopher D. Manning

    Simple methods for reading comprehension work, so the work involved detailed analysis of the dataset to show patterns in the data that kind of undermine the task.

- [Learning Language Games through Interaction](http://www.aclweb.org/anthology/P/P16/P16-1224.pdf)
    * Sida I. Wang, Percy Liang and Christopher D. Manning

    Learn from interaction rather than supervision. Outlined the necessity of better user interaction to teach machines well, the users who gave consistent commands taught the systems better, even if it was not in a real language.

- [Finding Non-Arbitrary Form-Meaning Systematicity Using String-Metric Learning for Kernel Regression](http://www.aclweb.org/anthology/P/P16/P16-1225.pdf)
    * E.Dario Gutierrez, Roger Levy and Benjamin Bergen {WON best paper award}

    Correlations between word meaning and word form. These seem arbitrary at first glance, but actually follow patterns in the corpus. Specially interesting are phonaesthemes. Used distributional models to confirm local phono semantic hypotheses. The mapping is found using supervised learning, non-parametric kernel regression, in particular.

- [On-line Active Reward Learning for Policy Optimisation in Spoken Dialogue Systems](https://www.aclweb.org/anthology/P/P16/P16-1230.pdf)
    * Pei-Hao Su, Milica Gasic, Nikola Mrkšić, Lina M. Rojas Barahona, Stefan Ultes, David Vandyke, Tsung-Hsien Wen and Steve Young {WON best student paper award}

    Instead of just awarding static rewards, learn the rewards to associate with different methods.

- [Globally Normalized Transition-Based Neural Networks](https://www.aclweb.org/anthology/P/P16/P16-1231.pdf)
    * Daniel Andor, Chris Alberti, David Weiss, Aliaksei Severyn, Alessandro Presta, Kuzman Ganchev, Slav Petrov and Michael Collins

    Feed-forward nets with global normalization obviate the need for looking forward into the rest of the sentence(dump the buffer).

### Life-time Achievement Award : Joan Bresnan

She invented Lexical Functional Grammars. Used a garden - bush analogy, not my favorite, but whatever! Cutely nerded out about Bantu languages. Garden to bush- not my favorite analogy, but anyway. Answered a question saying “I don’t know” - so much easier to admit than to go around the bush. Snubbed Jason Eisner, it was hilarious. Her talk outlined how statistical methods became mainstream in linguistics

---

## Day 4 : 10th Aug

### Representation Learning Workshop 

Snuck into this one for the excellent line-up of keynote talks

### Keynote Talk 3: Katrin Erk

### Keynote Talk 4: Tensor decompositions to learn sentence embeddings
[Animashree Anandkumar]

Properties which do not hold in two dimensions, hold in three. Non-convex optimization.

### Keynote Talk 5: Learning representations
[Hal Daumé III]

### CoNLL

The actual thing I was supposed to attend.

### Keynote Talk 6: Disfluency detection by humans
[Fernanda Ferreira]

Fascinating talk. I’m a big sucker for anything involving language and human psychology - so I was on the edge of the seat for this one. I even managed to embarrass myself - I went up to the speaker after her talk and started rambling about how this could be an argument in favor of left to right parsers

---

## Day 5: 11th Aug

### Keynote Talk 7: RNNaissance
[Jürgen Schmidhuber]

Grand talk, started with a history of neural nets and the LSTM, cited a lot of previous work and ended with grand promises of artificial intelligence leading to singularity 😃 Interestingly, the name long short-term memory comes from biological short-term memories.

<!--
- [Exploring Prediction Uncertainty in Machine Translation Quality Estimation]()
    * Daniel Beck, Lucia Specia, Trevor Cohn

    This was a good one, but I was nervous, so I barely understood.

- [Learning when to trust distant supervision: An application to low-resource POS tagging using cross-lingual projection]()
    * Meng Fang and Trevor Cohn

    Apparently LSTMs don't help much!
-->
- [Greedy, Joint Syntactic-Semantic Parsing with Stack LSTMs]() 
    * **Swabha Swayamdipta**, Miguel Ballesteros, Chris Dyer, Noah A. Smith

    My talk went pretty well, actually. Had quite a large attendance and a fun question-answering session with Lluis Marquez, Haagen Fursteneau, James Henderson and Trevor Cohn.

<!--
- [Beyond Prefix-Based Interactive Translation Prediction]()
    * Jesús González-Rubio, Daniel Ortiz Martinez, Francisco Casacuberta, Jose Miguel Benedi Ruiz

    Had a strange claim : instead of translating as the sentence is seen from left to right, this work claimed that interactive translation quality is better when the entire sentence is seen.

- [Cross-Lingual Named Entity Recognition via Wikification]()
    * Chen-Tse Tsai, Stephen Mayhew, Dan Roth

    Too many technical difficulties.
-->

At the end of the day, I snuck into the open discussion at the Word Vector evaluation workshop. Felix Hill opened that session with a long description of the questions he believed the community should be discussing. The most interesting(very subjectively) that was brought up was the lack of shared tasks, which has spurred development in other communities. I think most people agreed with the need to continue this workshop over the next few years.

---

# Some talks I missed out on:

- [Simple and Accurate Dependency Parsing Using Bidirectional LSTM Feature Representations](http://arxiv.org/pdf/1603.04351.pdf)
    * Eliyahu Kiperwasser and Yoav Goldberg

    Bilstm for features of words, then mlp of head/modifier to score possible dependency attachment.  MST on top.  Also used in greedy incremental parsing. Nice results.

- [Stack-propagation: Improved Representation Learning for Syntax](http://www.aclweb.org/anthology/P/P16/P16-1147.pdf)
    * Yuan Zhang and David Weiss
    
    Could imagine this being useful in syntax/semantics models (they applied it to POS/syntax).

- [Document-level Sentiment Inference with Social, Faction, and Discourse Context](http://www.aclweb.org/anthology/P/P16/P16-1032.pdf)
    * Hannah Rashkin and Sameer Singh and Yejin Choi

    //todo: need to check out

# What’s on my reading list:

1. dkjfldf
2. jfdljfjdf
44. jfldjf;lkdjf

I also tweeted a bunch during the conference, and got retweeted by Hal Daumé  ! [Here is his own blog post](http://nlpers.blogspot.in/2016/08/some-papers-i-liked-at-acl-2016.html) about the ACL talks he liked.
