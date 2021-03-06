---
layout: post
title:  "ACL in Berlin"
date:   2016-08-20 14:55:35 -0700
categories: blog conferences
---

I had a great time at ACL this year. Though there were too many parallel sessions at times and I had to take some time out to work on my own talk, I managed to attend many of the sessions. In this post, I've summarized my notes on the various talks I got to see.

Distributional semantics continued to be the overarching themes. Reinforcement learning is quickly gaining interest too. But this could be a biased opinion, and rather incomprehensive, based on the sessions and talks I attended.


---

## Day 1 : 8th Aug

### Keynote Talk 1: Same Policy Issue, Different Portrayal: The Importance of Tone and Framing in Language

#### Amber Boydstun

The same political issue could be framed in different ways, influencing public opinion. The speaker showed some cool statistical analyses that strengthened her theory. The challenge presented to the NLP audience was the following: can we automatically detect when there is framing and where on the political spectrum does the agenda-driven speech lie? In my opinion, this is still a very, very difficult NLP problem - we are barely scratching the surface of what can be potentially useful applications for society. This is good news - we are not going to be out of jobs anytime soon, yay!

### Session 1

* [Noise reduction and targeted exploration in imitation learning for Abstract Meaning Representation parsing](https://aclweb.org/anthology/P/P16/P16-1001.pdf)
    - James Goodman, Andreas Vlachos and Jason Naradowsky

    Suggested improvements to an existing transition-based approach to AMR parsing, which is prone to error propagation, especially if a greedy decoding method is employed. In particular, a DAgger-style imitation learning algorithm is used, which augments the training sample with examples that the parser is more likely to see at test time. Noise reduction is achieved through an alpha-bound on the training examples which are worth selecting. Targeted exploration involves taking into account the uncertainty of the imitation learner. Concepts of RollIn (ask the dynamic expert whether you are in error state) and RollOut (ask the dynamic expert whether the previous action was good) are defined for the DAgger-style algorithm. Results comparable to state-of-the-art. Really liked this one.

* [Generalized Transition-based Dependency Parsing via Control Parameters](https://www.aclweb.org/anthology/P/P16/P16-1015.pdf)
   - Bernd Bohnet, Ryan McDonald, Emily Pitler and Ji Ma

    Introduction of soft constraints on the transition sequences in a generalized transition-based parsing set up. The soft constraints are in terms of control parameters for transitions. In addition to unprocessed and operative (stack) tokens, active tokens are maintained. Global control parameters dictate system-wide behavior and transition control parameters, as the name suggests, are transition-specific. Applicability to various transition systems is demonstrated theoretically. Empirical comparison between some of the popular transition systems is provided, easy-first proving to be the best. I liked the motivation behind this, not sure if the idea itself is simple or worthwhile to implement, need to read the paper to figure out.

* [Learning the Curriculum with Bayesian Optimization for Task-Specific Word Representation Learning](https://www.aclweb.org/anthology/P/P16/P16-1013.pdf)
    - Yulia Tsvetkov, Manaal Faruqui, Wang Ling, Brian MacWhinney and Chris Dyer

    This one was about curriculum learning, where instead of training  on the natural corpus order of examples, the best order (curriculum) is learnt from samples provided. The curriculum is controlled by hyper parameters, which are learnt using Bayesian optimization. Curriculum learning was used here to learn word representations, and the learnt embeddings were tested out on multiple downstream tasks (hear, hear!), including dependency parsing, sentiment analysis, NER, etc. What's not immediately obvious, but interesting, is the large improvement over a random order of traning examples. Many friends on this paper, regardless of which I liked this one :) 

* [Named Entity Recognition with Bidirectional LSTM-CNNs](http://arxiv.org/abs/1511.08308) (TACL)
    - Jason P.C. Chiu and Eric Nichols

    Feature engineering for NER is claimed to have been replaced by learning a hybrid LSTM  + ConvNet architecture. Results are demonstrated on a CoNLL 2003 shared task - they're good! In spirit, this is very similar to my own paper - unfortunately though, the talk heavily emphasized only on the engineering in the work.

### Session 2

- [Active Learning for Dependency Parsing with Partial Annotation](http://www.aclweb.org/anthology/P/P16/P16-1033.pdf)
    * Zhenghua Li, Min Zhang, Yue Zhang, Zhanyi Liu, Wenliang Chen, Hua Wu and Haifeng Wang

    Dependency treebanking based on partial annotation. The active learning framework allows to manually annotate only the most uncertain words in each iteration. The uncertainty estimates come from a probabilistic CRF-based model. The partial trees obtained from the partial annotation are converted into a forest. A forest-based training objective is minimized to learn the parameters. Interesting, but will need to carefully read the paper to understand the methodology and figure out how thorough the experiements that compared partial to full annotation were. 

- [Morpho-syntactic Lexicon Generation Using Graph-based Semi-supervised Learning](https://transacl.org/ojs/index.php/tacl/article/download/730/166) (TACL)
    * Manaal Faruqui, Ryan McDonald and Radu Soricut

    Method to automatically extend a small sample morpho-syntactic lexicon to a large corpus using label propagation, Google-style. The twist is a featurized projection, instead of edge-wise label propagation. Though the approach is monolingual, they did it for eleven languages. Seems practically useful for lexical distributional semantics. Experimental results on the downstream task of dependency parsing are good. A general approach that exploits cross-lingual resources seems a lot more exciting and a great direction for future work.

- [News Citation Recommendation with Implicit and Explicit Semantics](http://www.aclweb.org/anthology/P/P16/P16-1037.pdf)
    * Hao Peng, Jing Liu and Chin-Yew Lin

    Talk by our newest ARK member! It's a new task which involves providing recommendations to authors of news articles the relevant citations they must include. Authorship disambiguation is facilitated through grounding the entities, as well as word embeddings for topic-based author information. As is norm for recommendation systems, this is a reranking task exploiting well known similarity metrics.

- [Document-level Sentiment Inference with Social, Faction, and Discourse Context](http://www.aclweb.org/anthology/P/P16/P16-1029.pdf)
    * Eunsol Choi, Hannah Rashkin, Luke Zettlemoyer and Yejin Choi

    Theories about relationships between entities, like friends of enemies are enemies, were empirically justified from text data. Involved complex annotation schemes and guidelines (I annotated!)

### Session 3

- [Multilingual Projection for Parsing Truly Low-Resource Languages](https://transacl.org/ojs/index.php/tacl/article/viewFile/869/197) (TACL)
    * Željko Agić, Anders Johannsen, Barbara Plank, Héctor Martínez Alonso, Natalie Schluter and Anders Søgaard

    The selling point of this paper was the usage of "truly" low-resource languages, instead of "cozy" languages, which are really still Indo-European (wonder if Emily Bender is convinced).  In fact, they need multi-parallel data, which also contains the low-resource language, limiting their options to Bible text. Same style of annotation projection as was used by Dipanjan and colleagues at Google, is employed, but more robust noise reduction techniques are employed (edge scores are projected instead of edges).

- [Combining Natural Logic and Shallow Reasoning for Question Answering](http://www.aclweb.org/anthology/P/P16/P16-1042.pdf)
    * Gabor Angeli, Neha Nayak and Christopher D. Manning

    Broad-coverage and high-precision techniques are combined for question answering. Relational entailment and meronymy are incorporated into the natural logic framework to support the shallow lexical methods. The talk demonstrated a clever trick using a sample logic puzzle. The Stanford NaturalLI framework is used for experiments, a new evaluation methodology is introduced.

- [Many Languages, One Parser](https://transacl.org/ojs/index.php/tacl/article/view/892/207) (TACL)
    * Waleed Ammar, George Mulcaire, Miguel Ballesteros, Chris Dyer and Noah A. Smith

    As the title suggests, a single parsing model was used for twelve different languages, some low-resource, exploiting linguistic and typological universals (may not be that low-resource, especially after Agić talk). The approach relies on multilingual word embeddings as well as dealt with the currently trending problem of language identification. This paper was from our research group, Waleed always has fun slides :)

- [Unsupervised Part-Of-Speech Tagging with Anchor Hidden Markov Models](http://www.cs.columbia.edu/~djhsu/papers/poshmm-tacl.pdf) (TACL)
    * Karl Stratos, Michael Collins and Daniel Hsu

    Anchor HMMs are HMMs that assume for every tag at least one word that is always associated with that tag only. In some sense, this structurally restricts the HMM, but then again comes with performance guarantees. However, it wasn't clear if  the properties generalize. Anchor HMMs were applied to unsupervised POS tagging in the non-negative matrix factorization framework by Arora, and resulted in a consistent estimator. Again, I'm partial to this paper because it has friends. Regardless, it improves something as basic as HMMs for POS tagging, all the while using this very agreeable anchor assumption - how can one not like it?

- [Multi-lingual dependency parsing evaluation: a large-scale analysis of word order properties using artificial data](https://transacl.org/ojs/index.php/tacl/article/viewFile/870/201) (TACL)
    * Kristina Gulordava and Paola Merlo

    Multlingual treebank properties versus linguistic properties are analyzed. Artificial treebanks are generated by manipulating word orders, the motivation being to test how the treebank properties hold, with different linguistic properties (a different language). One of the tricks used to generate an artificial language was changing the sentence to minimize the dependency lengths, resulting in word order permutations. Parsing performance was analyzed post these permutations - word order variability most negatively affected the same. Cool idea, the talk was very difficult to follow, though.

---

## Day 2 : 9th Aug

### Keynote talk 2: Mark Steedman

This talk was about what the speaker classified as collocational vs denotational paradigms of distributional semantics. Collocational semantics is what word vectors are all about. Denotational semantics equates to logical semantics, building knowledge graphs, etc.

The speaker went over a lot of history of distributional sematics, and situated his own body work in the whole scheme of things. Lots of linguistic insights were provided, particularly why entailment is so important for natural language understanding..

---

## Day 3 : 10th Aug

### Outstanding Papers Session I and II

- [A Thorough Examination of the CNN/Daily Mail Reading Comprehension Task](http://www.aclweb.org/anthology/P/P16/P16-1223.pdf)
    * Danqi Chen, Jason Bolton and Christopher D. Manning

    Simple methods for reading comprehension -- question answering about a missing entity. Involved a detailed analysis of the dataset to show patterns in the data. I loved the fact that they clearly showed that simple hyperparameter tuning improvement beat the Felix Hill baseline - proving that the task has fundamental problems, and can probably not be solved any better.

- [Learning Language Games through Interaction](http://www.aclweb.org/anthology/P/P16/P16-1224.pdf)
    * Sida I. Wang, Percy Liang and Christopher D. Manning

    Cool task of playing an interactive language game between a human player and a computer. Outlined the necessity of better user interaction, as opposed to supervision, to teach machines better. Users who gave consistent commands taught the systems better, even if the commands were not in a real language. A semantic parser was trained, it used probabilistic feature-based mapping. The work showed the benefit of incorporating pragmatics.

- [Finding Non-Arbitrary Form-Meaning Systematicity Using String-Metric Learning for Kernel Regression](http://www.aclweb.org/anthology/P/P16/P16-1225.pdf)
    * E.Dario Gutierrez, Roger Levy and Benjamin Bergen {WON best paper award}

    Correlations between word meaning and word form. These seem arbitrary at first glance, but actually follow patterns in the corpus. Specially interesting are phonaesthemes. Used distributional models to confirm local phono semantic hypotheses. The mapping is found using supervised learning, non-parametric kernel regression, in particular.

- [On-line Active Reward Learning for Policy Optimisation in Spoken Dialogue Systems](https://www.aclweb.org/anthology/P/P16/P16-1230.pdf)
    * Pei-Hao Su, Milica Gasic, Nikola Mrkšić, Lina M. Rojas Barahona, Stefan Ultes, David Vandyke, Tsung-Hsien Wen and Steve Young {WON best student paper award}

    Instead of just awarding static rewards, learn the rewards to associate with different methods.

- [Globally Normalized Transition-Based Neural Networks](https://www.aclweb.org/anthology/P/P16/P16-1231.pdf)
    * Daniel Andor, Chris Alberti, David Weiss, Aliaksei Severyn, Alessandro Presta, Kuzman Ganchev, Slav Petrov and Michael Collins

    Feed-forward nets with global normalization obviate the need for looking forward into the rest of the sentence (dump the buffer). Happy that Google open sourced its code!

### Life-time Achievement Award : Joan Bresnan

She invented Lexical Functional Grammars. Used a garden - bush analogy, not my favorite, but whatever! Cutely nerded out about Bantu languages. Garden to bush- not my favorite analogy, but anyway. Answered a question saying “I don’t know” - so much easier to admit than to go around the bush. She didn't recognize an older Jason Eisner, it was funnily endearing. Her talk historically outlined how statistical methods became mainstream in linguistics.

---

## Day 4 : 10th Aug

### Representation Learning Workshop 

Snuck into this one for the excellent line-up of keynote talks...

### Keynote Talk 3: Formal and distributional semantics

#### Katrin Erk

The talk was about representation learning for single document understanding. Montague meets Markov: first-order logic and Markov logic networks were emphasized. Probabilistic inference for undirected graphical models was discussed - network size is the limiting issue. The speaker was strongly in favor of this paradigm of representation learning.

There was also a discussion on textual entailment. She encouraged the audience to question if a paraphrase is in the context of the current document or a true paraphrase. Rare events and one-shot learning for lexical semantics, with a concern for overfitting, were also discussed.

I'm a little lost on what the ultimate gist was. There was a discussion at length on first-order logic, in the question-answering session.

### Keynote Talk 4: Tensor decompositions to learn sentence embeddings

#### Animashree Anandkumar

The speaker emphasized on the greater challenge in the learning of representations of sentences, as compared to words. Some previously used methods and their weaknesses were first described, such as compositional models and paragraph vectors - these do not incorporate word ordering and need supervision. Skip-thought vectors for sentence embeddings (like skip-gram is for words) are better since they are unsupervised, but need collection of sentences, not just a single sentence. Convolutional models for sentence embeddings incorporate word vectors, but are supervised. The speaker's own work also deal with convolutional models for sentence embeddings, but make them unsupervised, and hence difficult to train.

The biggest problem here is nonconvex optimization (still in an alternating minimization algorithm), which comes with saddle points and the lack of good stopping criteria. Here comes tensor decompostion to the rescue - properties which do not hold in two dimensions, hold in three, so use tensors now. Singular value decomposition is not necessarily unique for matrices, but is for tensors. All you have to do is stack your matrices and form tensors.
The estimation will now involve higher-order moment-based methods and spectral learning.

Not only is this method fast, but also comes with convergence guarantees. Other applications: Visual QA; Topic Models; Image Caption generation. Spectral methods can also be used for POMDPs in a reinforcement learning framework.

Super cool talk, made me want to revisit my convex optimization class notes!

### Keynote Talk 5: Learning representations

#### Hal Daumé III

This talk was about learning representations of characters, phones, words and structured outputs. All our representation learning was in the form of linear models till some time back.

Languages are different - so can provide supervision for each other. According to Hal, input/output correlation is overrated.

Transliteration uses IPAs to learn embeddings and then do matches across languages. There are different pronunciation systems across languages. Also true for other tasks - translation is not exact. How then should we tie languages? Proposed solution: let their pronunciations be close but not exactly the same, because languages bring in different information. A joint minimization over both words, such that there is a small wiggle room allowing them to be different, works much better than regular input-output pairing. This is generally good advice for multilingual models across any task.

Speaking of structured prediction, Hal suggested the following: instead of combined features of input and output, have separate feature vectors for both and then minimize the Euclidean distance between input and output feature vectors with some margin. The separate representation learning would help.

He then spoke about incremental prediction and imitation learning. He used some cognitive sciencey motivation : a rather heartless experiment done in the past using a kitten with  a full view and another with a constrained view. Obviously the former kitten learns more about the world.

He finally talked about some ongoing work on imitation learning with neural nets (no backprop). The unpublished dependency parsing results are 1% better than a strong baseline. Backdrop through time changes the story though. Hal trolled us a little bit by saying they are using LSTMs and embeddings and SGD and Adagrad, and then said he was kidding - they are really just using CCA.

It was a great talk, as expected. I'm going to remember the wiggle room bit, reminds me of Kevin Gimpel's work on loss functions. Also, very ridiculously, someone stepped on the stage in the middle of the talk, with the statement that infinity is the answer :P

### CoNLL

The actual thing I signed up to attend...

### Keynote Talk 6: Disfluency detection by humans

#### Fernanda Ferreira

Humans are obviously the best parsers, so much so that our brains are wired to account for disfluency, even before it occurs. We definitely parse language left to right, we don't necessarily always build trees bottom up. 

Fascinating talk! I’m a big sucker for anything involving language and human psychology - so I was on the edge of the seat for this one. 

---

## Day 5: 11th Aug

### Keynote Talk 7: RNNaissance

#### Jürgen Schmidhuber


Grand talk, started with a history of neural nets and the LSTM (he was one of the inventors), cited a lot of previous work. The talk ended with promises for a future involving artificial intelligence exploring other planets, and even leading to singularity 😃  Interestingly, the name long short-term memory comes from biological short-term memories

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

## Some talks I missed out on:

- [Simple and Accurate Dependency Parsing Using Bidirectional LSTM Feature Representations](http://arxiv.org/pdf/1603.04351.pdf)
    * Eliyahu Kiperwasser and Yoav Goldberg

<!-- 
    Bi-LSTM for features of words, then mlp of head/modifier to score possible dependency attachment.  MST on top.  Also used in greedy incremental parsing. Nice results.
-->

- [Stack-propagation: Improved Representation Learning for Syntax](http://www.aclweb.org/anthology/P/P16/P16-1147.pdf)
    * Yuan Zhang and David Weiss
    
<!--    
    Could imagine this being useful in syntax/semantics models (they applied it to POS/syntax).
-->

- [Document-level Sentiment Inference with Social, Faction, and Discourse Context](http://www.aclweb.org/anthology/P/P16/P16-1032.pdf)
    * Hannah Rashkin and Sameer Singh and Yejin Choi

- [Beyond Privacy: The Social Impact of Natural Language Processing](http://www.aclweb.org/anthology/P/P16/P16-2096.pdf)
    * Dirk Hovy and Shannon L. Spruit

## On my reading list:

- [Generalized Transition-based Dependency Parsing via Control Parameters](https://www.aclweb.org/anthology/P/P16/P16-1015.pdf)
- [Active Learning for Dependency Parsing with Partial Annotation](http://www.aclweb.org/anthology/P/P16/P16-1033.pdf)
- [Stack-propagation: Improved Representation Learning for Syntax](http://www.aclweb.org/anthology/P/P16/P16-1147.pdf)
- [Simple and Accurate Dependency Parsing Using Bidirectional LSTM Feature Representations](http://arxiv.org/pdf/1603.04351.pdf)
- [Finding Non-Arbitrary Form-Meaning Systematicity Using String-Metric Learning for Kernel Regression](http://www.aclweb.org/anthology/P/P16/P16-1225.pdf)
- [On-line Active Reward Learning for Policy Optimisation in Spoken Dialogue Systems](https://www.aclweb.org/anthology/P/P16/P16-1230.pdf)

One cool thing I've got to mention is that ACL this year was a strong indicator that the community is thinking about gender diversity. We’re lucky to have a fair amount of female NLP researchers, compared to other areas in Computer Science. However, there are still milestones to achieve. ACL encouraged a lot of women speakers. I met a lot of cool researchers - Sharon Goldwater, Emily Bender, Animashree Anandkumar and had one of the best brainstorming sessions with Yejin Choi. It makes a big difference to me seeing successful women in the field - I can relate to them and it reaffirms my faith in my own decision to pursue NLP. It was total fun hearing them nerd out about their research (something I kind of miss about CMU, everyone was always nerding it out).

I tweeted a bunch during the conference, and also got retweeted by Hal Daumé! [Here is his own blog post](http://nlpers.blogspot.in/2016/08/some-papers-i-liked-at-acl-2016.html) about the ACL talks he liked.
