# Interpretability and explainable machine-learning models.

## Introduction
As our models gets more and more complex and non-linear, it becomes difficult to clearly understand how they function and the reasons that have lead to a specific result.
Many attempts were made so far in the field: Visualization of CNN neurons; Measuring feature importance using LIME, SHAP, TCAV, to name a few. These methods shed light on the feature importance for a specific prediction/inference and can help understanding if the model is biased.

## Reading material and preparation
What exactly do we mean by model interpretability?

### Jenn Wortman Vaughan from Microsoft examines various aspects of interpretability from user perspective:
Video: https://www.youtube.com/watch?v=8ZoL-cKRf2o
Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_jenn_wortman_vaughan.pdf

### Viktoria Krakovna from DeepMind discuss the importance of interpretability in reinforcement learning:
Video: https://www.youtube.com/watch?v=3HzIutdlpho
Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_victoria_Krakovna.pdf

### An extended book about ML Interpretability (if you wish to dig deeper):
https://christophm.github.io/interpretable-ml-book/

Analyzing feature-importance using a 'shadow' linear model:

### The Intriguing Properties of Model Explanations:
https://arxiv.org/pdf/1801.09808.pdf

### lightning talk:
Video: https://youtu.be/p9vdQUxQOzg?t=650
Slides: http://s.interpretable.ml/nips_interpretable_ml_2017_spotlight_talks.pdf
(Slides 23 - 27 - although the rest is interesting too ;) )

### LIME
https://arxiv.org/abs/1602.04938
https://github.com/marcotcr/lime
https://medium.freecodecamp.org/how-to-improve-your-machine-learning-models-by-explaining-predictions-with-lime-7493e1d78375

### SHAP
https://arxiv.org/abs/1705.07874
https://github.com/slundberg/shap
https://medium.com/@gabrieltseng/interpreting-complex-models-with-shap-values-1c187db6ec83

### TCAV
https://arxiv.org/abs/1711.11279
https://github.com/tensorflow/tcav
https://www.quantamagazine.org/been-kim-is-building-a-translator-for-artificial-intelligence-20190110/

### Manifold
https://arxiv.org/pdf/1808.00196.pdf
https://eng.uber.com/manifold/

Various ML model Architectures:

### CNN dissection and Visualization:
paper: https://arxiv.org/pdf/1704.05796.pdf
slides: http://people.csail.mit.edu/bzhou/ppt/presentation_ICML_workshop.pdf
demo: http://netdissect.csail.mit.edu/

### GAN dissection:
https://gandissect.csail.mit.edu/

### Seq2Seq:
https://arxiv.org/abs/1804.09299
http://seq2seq-vis.io/

### NLP - Word & Sentence Embedding:
http://www.offconvex.org/2018/06/17/textembeddings/
https://arxiv.org/pdf/1608.04207.pdf
https://arxiv.org/pdf/1805.01070.pdf

### Autonomous Vehicles:
https://kimjinkyu.files.wordpress.com/2017/12/nips_2017.pdf

## Meeting Notes
Model interpretability depends on the target audience or on the context. A doctor will need a different explanation than a judge for a prediction.
It may also be personal: explanation that satisfies one person, may not be enough for another.
For data scientists and developers, it may be a tool to adjust the model - i.e. for debugging.
Therefore, there should be a clear distinction when speaking about model interpretability or reasoning, if it is made for the model creator (debugging a model) or for the end-user.

A certain concern was expressed: when disecting a neural network - are we focusing too much on the explainee neurons while ignoring neurons which do not have a clear purpose (which are the magority of the neurons in the net).

"Thinking fast and slow" from Kahnmann was brought as a possible explanation for neural network, where "intuition" was given as an explanation for a neural net. But this can not be satisfactory explanation for a model. Not morally nor legally.
ML should be explainable, and not be held as an intuition, as its acceptance, by humans in a mixed world, depends on understanding its "motives".
