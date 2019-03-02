# Interpretability and explainable machine-learning models.

## Introduction
As our models gets more and more complex and non-linear, it becomes difficult to clearly understand how they function and the reasons that have lead to a specific result.
Many attempts were made so far in the field: Visualization of CNN neurons; Measuring feature importance using LIME, SHAP, TCAV, to name a few. These methods shed light on the feature importance for a specific prediction/inference and can help understanding if the model is biased.

### Reading material and preparation
What exactly do we mean by model interpretability?

#### Jenn Wortman Vaughan from Microsoft examines various aspects of interpretability from user perspective:
- Video: https://www.youtube.com/watch?v=8ZoL-cKRf2o
- Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_jenn_wortman_vaughan.pdf

#### Viktoria Krakovna from DeepMind discuss the importance of interpretability in reinforcement learning:
- Video: https://www.youtube.com/watch?v=3HzIutdlpho
- Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_victoria_Krakovna.pdf

#### An extended book about ML Interpretability (if you wish to dig deeper):
https://christophm.github.io/interpretable-ml-book/

Analyzing feature-importance using a 'shadow' linear model:

#### The Intriguing Properties of Model Explanations:
[The Intriguing Properties of Model Explanations](https://arxiv.org/pdf/1801.09808.pdf)

### lightning talk:
- Video: https://youtu.be/p9vdQUxQOzg?t=650
- Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_spotlight_talks.pdf (Slides 23 - 27 - although the rest is interesting too ;) )

#### LIME
- ["Why Should I Trust You?": Explaining the Predictions of Any Classifier](https://arxiv.org/abs/1602.04938)
- https://github.com/marcotcr/lime
- https://medium.freecodecamp.org/how-to-improve-your-machine-learning-models-by-explaining-predictions-with-lime-7493e1d78375

#### SHAP
- [A Unified Approach to Interpreting Model Predictions](https://arxiv.org/abs/1705.07874)
- https://github.com/slundberg/shap
- https://medium.com/@gabrieltseng/interpreting-complex-models-with-shap-values-1c187db6ec83

#### TCAV
- [Interpretability Beyond Feature Attribution: Quantitative Testing with Concept Activation Vectors (TCAV)](https://arxiv.org/abs/1711.11279)
- https://github.com/tensorflow/tcav
- https://www.quantamagazine.org/been-kim-is-building-a-translator-for-artificial-intelligence-20190110/

#### Manifold
- [Manifold: A Model-Agnostic Framework for Interpretation and Diagnosis of Machine Learning Models](https://arxiv.org/pdf/1808.00196.pdf)
- https://eng.uber.com/manifold/

Various ML model Architectures:

#### CNN dissection and Visualization:
- paper: https://arxiv.org/pdf/1704.05796.pdf
- slides: http://people.csail.mit.edu/bzhou/ppt/presentation_ICML_workshop.pdf
- demo: http://netdissect.csail.mit.edu/

#### GAN dissection:
https://gandissect.csail.mit.edu/

#### Seq2Seq:
- [Seq2Seq-Vis: A Visual Debugging Tool for Sequence-to-Sequence Models](https://arxiv.org/abs/1804.09299)
- http://seq2seq-vis.io/

#### NLP - Word & Sentence Embedding:
- http://www.offconvex.org/2018/06/17/textembeddings/
- [Fine-grained Analysis of Sentence Embeddings Using Auxiliary Prediction Tasks](https://arxiv.org/pdf/1608.04207.pdf)
- [What you can cram into a single $&!#* vector:Probing sentence embeddings for linguistic properties](https://arxiv.org/pdf/1805.01070.pdf)
- [Dissecting Contextual Word Embeddings:Architecture and Representation](http://aclweb.org/anthology/D18-1179)

#### Autonomous Vehicles:
https://kimjinkyu.files.wordpress.com/2017/12/nips_2017.pdf

## Meeting Notes
Model interpretability depends on the target audience or on the context. A doctor will need a different explanation than a judge for a prediction.
It may also be personal: explanation that satisfies one person, may not be enough for another.
For data scientists and developers, it may be a tool to adjust the model - i.e. for debugging.
Therefore, there should be a clear distinction when speaking about model interpretability or reasoning, if it is made for the model creator (debugging a model) or for the end-user.

A certain concern was expressed: when disecting a neural network - are we focusing too much on the explainee neurons while ignoring neurons which do not have a clear purpose (which are the magority of the neurons in the net).

"Thinking fast and slow" from Kahnmann was brought as a possible explanation for neural network, where "intuition" was given as an explanation for a neural net. 
But this can not be satisfactory explanation for a model. Not morally nor legally.
ML should be explainable, and not be held as an intuition, as its acceptance by humans in a mixed world, depends on understanding its "motives".

Humans are making decisions first, and only afterwards understand the reasons that lead to those decisions. In a way, LIME acts similarly by supplying an explanations to predictions after they were deducted. Clients are mostly interested in those local explanations (compared to global general model explanations) after an unexpected prediction were made.

Training data validity, variance and quality is an important factor as well to the quality of the model explanation.

The current usage of LIME gives an initial intuition for the model performance, but this intution may be wrong. The linear surrogate model that is created by the current LIME implementation has unexplainaed inner assumptions regarding the distance (delta or epsilon) around the local point. Changes to this distance leads to different explanations. In addition, it is insensitive to noise, and it does not take into considereation the importance of combination of features and their mutual contribution.
A combination of features is found in SHAP, as well as in the second version of LIME - [anchor-LIME](https://arxiv.org/abs/1611.05817).

Both LIME and SHAP are actually another model, that is done to explain the original model. A question arrose: can we trust the model tat explain the model? and if not, how deep should we go, nesting explaination models?

For having a decent and satisfying model explanation, a human should be in the loop from an early stage. I.e - the users should be presented with the prediction explanations and maybe even rate them. Currently, people trust companies and brands more, and tends to let it affect them when they trust the models.

One of the disadvantages of an end-to-end models, is that they lack an explanation and reasoning to their prediction. But would a combination of simple models still be explanable?

The topic of layability was briefly discussed as well: AI makers and users are legal colaboratives to an event (autonomous car accident). Given that morality is culture-dependant, how should an AI be trained? It also implies that the explainability may differ, location- and culture-wise.
