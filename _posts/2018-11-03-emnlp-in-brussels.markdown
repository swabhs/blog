---
layout: post
title:  "Notes from EMNLP 2018 Brussels"
date:   2018-11-03 04:55:35 -0700
categories: blog conferences
---

My very brief notes from EMNLP 2018.

---

## Overall Trends
_Note that this might be subject to some self-selection bias._

1. Datasets abound (at least 25!)
    - QuAC, HotpotQA, MultiWoz, SWAG
2. Blackbox NLP sellout
    - 650+ registrations
3. Variational auto-encoders
4. Syntax is back! At least in SRL…

---

## Continuing Trends

1. Multitask / Transfer learning
2. Adversarial learning
3. Language Modeling
4. Machine Translation
    - [Phrase-Based & Neural Unsupervised Machine Translation.](http://aclweb.org/anthology/D18-1549)
        * Lample et. al. [Best Paper] 
5. Breaking / Replicating models
    - [How Much Reading Does Reading Comprehension Require? A Critical Investigation of Popular Benchmarks.](http://aclweb.org/anthology/D18-1546)
        *  Kaushik \| Lipton [Best Paper]

---

## [BlackBox NLP](https://blackboxnlp.github.io/)

- [Keynote I](http://u.cs.biu.ac.il/~yogo/blackbox2018.pdf)
    * Yoav Goldberg

    Nice summary of how different papers have over the years tried to interpret RNNs. Formal expressive power and connections to FSAs.

- [Keynote II](http://www.phontron.com/slides/neubig18blackbox.pdf)
    * Graham Neubig

    Treat structure as latent in various RNN-based models.

- [Keynote III]()
    * Leila Wehbe

    Argued that we are studying a blackbox (human brain) with another blackbox (artificial neural nets). Study of brain activations with word embeddings.

- [Understanding Convolutional Neural Networks for Text Classification.](http://aclweb.org/anthology/W18-5408)
    *  Alon Jacovi \| Oren Sar Shalom \| Yoav Goldberg

    Filters + max-pooling = n-gram detectors

- [Language Models Learn POS First.](http://aclweb.org/anthology/W18-5438)
    * Naomi Saphra and Adam Lopez

- [Language Modeling Teaches You More than Translation Does: Lessons Learned Through Auxiliary Syntactic Task Analysis.](http://aclweb.org/anthology/W18-5448)
    * Kelly Zhang \| Samuel Bowman

- [Interpretable Structure Induction via Sparse Attention.](http://aclweb.org/anthology/W18-5450)
    * Ben Peters \| Vlad Niculae \| André F. T. Martins

    Sparse posteriors help learn a latent structure which helps interpretability

- [Under the Hood: Using Diagnostic Classifiers to Investigate and Improve how Language Models Track Agreement Information.](http://aclweb.org/anthology/W18-5426)
    * Mario Giulianelli \| Jack Harding \| Florian Mohnert \| Dieuwke Hupkes \| Willem Zuidema
    * [Best Paper]

- Terminology trend: “Diagnostic Classifiers”

---

## [Tutorial: Deep Latent Variable Models for Natural Language](http://nlp.seas.harvard.edu/latent-nlp-tutorial.html)

- Bridge between deep learning and learning latent variables.
Compatible and incompatible
- Approaches for inference with different kinds of latent variables
    * Discrete LVs (tractable inference) - Naïve Bayes
    * Continuous LVs (intractable) - Variational Auto-encoders
    * Structured LVs (intractable) - Unsupervised parsing
- Advanced:
    * Reparameterization for discrete LVs (Gumbel Softmax)
    * Tightening the lower bound: Flows and importance sampling.

---

## Variational Autoencoders are hot!

Other than in the tutorial above, variational autoencoders seem to have captured the NLP imagination. This EMNLP they featured in papers across different tasks, such as:

- Generation: [Generating Classical Chinese Poems via Conditional Variational Autoencoder and Adversarial Training.](http://aclweb.org/anthology/D18-1423)
    * Li et. al.

- Translation: [Improving Unsupervised Word-by-Word Translation with Language Model and Denoising Autoencoder.](http://aclweb.org/anthology/D18-1101)
    * Kim et. al.

- Sentence Encoders: [Learning Universal Sentence Representations with Mean-Max Attention Autoencoder.](http://aclweb.org/anthology/D18-1481)
    * Zhang et. al.

- Text Cat: [GraphBTM: Graph Enhanced Autoencoded Variational Inference for Biterm Topic Model.](http://aclweb.org/anthology/D18-1495)
    * Zhu et. al.

- Script Generation: [Hierarchical Quantized Representations for Script Generation.](http://aclweb.org/anthology/D18-1413)
    * Noah Weber \| Leena Shekhar \| Niranjan Balasubramanian \| Nathanael Chambers

    Script generation using hierarchical VAEs, using a quantization trick to allow for discrete latent variables. Evaluation as a language model, which apparently is the new trend. Training seems hard to get to work. Other approaches for dealing with a hierarchy of latent variables involve variance reduction, clustering-like feature maps. 

- Coreference: [Variational Sequential Labelers for Semi-Supervised Learning.](http://aclweb.org/anthology/D18-1020) 
    * Chen et. al. 

- In general: [Spherical Latent Spaces for Stable Variational Autoencoders.](http://aclweb.org/anthology/D18-1480)  
    *  Xu & Durrett.

    Preventing posterior collapse with Mises-Fisher distribution

This list is obviously not comprehensive, I've only selected a representative sample from each area.

---
## Syntax is back (in SRL at least)!

- [Linguistically-Informed Self-Attention for Semantic Role Labeling.](http://aclweb.org/anthology/D18-1548) 
    * Strubell et. al.

    Training attention heads with syntax in a transformer architecture. Also multi-task learning.

- [A Unified Syntax-aware Framework for Semantic Role Labeling.](http://aclweb.org/anthology/D18-1262)
    * Li et. al.

    Syntax encoded as a graph convnet improves SRL

- [Towards Semi-Supervised Learning for Deep Semantic Role Labeling.](http://aclweb.org/anthology/D18-1538)
    *  Mehta et. al.

    Syntactic-inconsistency loss to explicitly incorporate syntactic constituents,  SRL-unlabeled instances to train a joint-objective.

- [Semantic Role Labeling for Learner Chinese: the Importance of Syntactic Parsing and L2-L1 Parallel Data.](http://aclweb.org/anthology/D18-1414)
    *  Lin et. al. 

    Use of syntax significantly improves transferability of SRL to learner languages.

- Shameless Plug: [Syntactic Scaffolds for Semantic Structures](http://aclweb.org/anthology/D18-1412)
    * Swabha Swayamdipta et. al.

---
## Other talks and papers I liked:

- [Keynote III]()
    * Johan Bos

    Boxer: CCG-like semantic formalism. Understanding the semantics of translations. Neural vs classic models. Discussion of evaluation of models.

- [Towards Dynamic Computation Graphs via Sparse Latent Structure.](http://aclweb.org/anthology/D18-1108)
    * Niculae et. al.

    Sparse distribution over latent structures + end-to-end differentiability

- [Learning Neural Templates for Text Generation.](http://aclweb.org/anthology/D18-1356)
    *   Wiseman et. al.

    Unsupervised learning of “templates” which are latent structures given by hidden semi-Markov models


- [Targeted Syntactic Evaluation of Language Models](http://aclweb.org/anthology/D18-1151)
    * Rebecca Marvin \| Tal Linzen

    LSTMs might not be as good at capturing syntax, or grammaticality.

- [Pathologies of Neural Models makes Interpretations Difficult](http://aclweb.org/anthology/D18-1407)
    *  Feng et. al.

    Removing “least important” words preserves neural model performance while being manually uninterpretable. Fine-tuning with high entropy with reduced data.

- [Semi-Supervised Sequence Modeling with Cross-View Training](http://aclweb.org/anthology/D18-1217)
    * Kevin Clark \| Minh-Thang Luong \| Christopher D. Manning \| Quoc V. Le

    Learning contextualized represnetations via sequence modeling (as opposed to language modeling).
    Fine-tuning as opposed to feature-based learning.
    When supervision is present, use it to train primary modules.
    When absent, make a prediction using a reduced view in an auxillary module, and minimize the KL divergence from the predicted primary module distribution.
    This results in training better representations, since the auxillaries are forced to make the same predictions as primary without seeing all the features.
    This is similar to a teacher-student network or distillation.
    Further improvements are observed using a multi-task learning setup, which results in much faster convergence.
    Very careful experiments, loved the attention to detail in this paper.

## Other EMNLP Summaries:

- [Patrick Lewis](https://www.patricklewis.io/post/emnlp2018/)
- [Sebastian Ruder](http://ruder.io/emnlp-2018-highlights/)
- [Claudia Hauff](https://chauff.github.io/2018-11-04-emnlp/)


I found Brussels super charming, but the ease of availability of chocolate is _extremely_ dangerous.
