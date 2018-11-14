---
layout: post
title:  "EMNLP 2018 Brussels"
date:   2018-11-03 04:55:35 -0700
categories: jekyll update
--- 

Alert : self-selection bias!

---

## Overall Trends

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
        *  Kaushik & Lipton [Best Paper]

---

## [BlackBox NLP](https://blackboxnlp.github.io/)

- [Yoav Goldberg Keynote](http://u.cs.biu.ac.il/~yogo/blackbox2018.pdf)

    Nice summary of how different papers have over the years tried to interpret RNNs. Formal expressive power and connections to FSAs.

- Leila Wehbe Keynote:

    Argued that we are studying a blackbox (human brain) with another blackbox (artificial neural nets). Study of brain activations with word embeddings.

- Understanding Convolutional Neural Networks for Text Classification.
    * Jacovi et. al.

    Filters + max-pooling = n-gram detectors

- Language Models Learn POS First.
    * Saphra et. al.

- Language Modeling Teaches You More than Translation Does: Lessons Learned Through Auxiliary Syntactic Task Analysis.
    * Zhang et. al.

- Interpretable Structure Induction via Sparse Attention.
    * Peters et. al.

    Sparse posteriors help learn a latent structure which helps interpretability

- Under the Hood: Using Diagnostic Classifiers to Investigate and Improve how Language Models Track Agreement Information. [Best Paper]
    * Giulianelli et. al.

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
- [Graham Neubig talk in Blackbox NLP](http://www.phontron.com/slides/neubig18blackbox.pdf)
    * Treat structure as latent in various RNN-based models.

---

## Variational Autoencoders are hot!

- [Spherical Latent Spaces for Stable Variational Autoencoders.](http://aclweb.org/anthology/D18-1480)  
    *  Xu & Durrett.

    Preventing posterior collapse with Mises-Fisher distribution

- Generation: [Generating Classical Chinese Poems via Conditional Variational Autoencoder and Adversarial Training.](http://aclweb.org/anthology/D18-1423)
    * Li et. al.

- Translation: [Improving Unsupervised Word-by-Word Translation with Language Model and Denoising Autoencoder.](http://aclweb.org/anthology/D18-1101)
    * Kim et. al.

- Sentence Encoders: [Learning Universal Sentence Representations with Mean-Max Attention Autoencoder.](http://aclweb.org/anthology/D18-1481)
    * Zhang et. al.

- Text Cat: [GraphBTM: Graph Enhanced Autoencoded Variational Inference for Biterm Topic Model.](http://aclweb.org/anthology/D18-1495)
    * Zhu et. al.

- Script Generation: [Hierarchical Quantized Representations for Script Generation.](http://aclweb.org/anthology/D18-1413) 
    * Weber et. al.  

- Coreference: [Variational Sequential Labelers for Semi-Supervised Learning.](http://aclweb.org/anthology/D18-1020) 
    * Chen et. al. 

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

- Johan Bos. Keynote.

    Boxer: CCG-like semantic formalism. Understanding the semantics of translations. Neural vs classic models. Discussion of evaluation of models.

- [Towards Dynamic Computation Graphs via Sparse Latent Structure.](http://aclweb.org/anthology/D18-1108)
    * Niculae et. al.

    Sparse distribution over latent structures + end-to-end differentiability

- [Learning Neural Templates for Text Generation.](http://aclweb.org/anthology/D18-1356)
    *   Wiseman et. al.
Unsupervised learning of “templates” which are latent structures given by hidden semi-Markov models

- [Pathologies of Neural Models makes Interpretations Difficult](http://aclweb.org/anthology/D18-1407)
    *  Feng et. al.

    Removing “least important” words preserves neural model performance while being manually uninterpretable. Fine-tuning with high entropy with reduced data.

## Other EMNLP Summaries:

- [Patrick Lewis](https://www.patricklewis.io/post/emnlp2018/)
- [Sebastian Ruder](http://ruder.io/emnlp-2018-highlights/)
- [Claudia Hauff](https://chauff.github.io/2018-11-04-emnlp/)