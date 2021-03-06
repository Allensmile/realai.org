---
permalink: /continual-learning/
---
# Continual Learning

Continual learning focuses on an agent's ability to learn new tasks without forgetting old ones. Skills learned from old tasks may or may not transfer to new tasks, but must be largely retained. One approach is to penalize learning for weights that are important for remembering old tasks. Importance measures of weights can be computed online ([Zenke & Poole & Ganguli, 2017](https://arxiv.org/abs/1703.04200)). The elastic weight consolidation (EWC) ([Kirkpatrick et al, 2016](https://arxiv.org/abs/1612.00796)) method relies on computing the Fisher information metric at the end of each task. [Seff et al. (2017)](https://arxiv.org/abs/1705.08395) explain that both of these methods can be adapted to training conditional GANs.

Another approach to prevent catastrophic forgetting is to design novel network architectures. PathNets ([Fernando et al., 2017](https://arxiv.org/abs/1701.08734)) are large neural networks where the learning of a particular task evolves towards a subset of parameters, these parameters are then fixed before learning moves on to the next task. Note that when such a large architecture is viewed as a family of possible standard deep neural networks, [Veniat & Denoyer (2017)](https://arxiv.org/abs/1706.00046) demonstrate that reinforcement learning can be used to discover networks that are efficient in computational cost (Flop) or time (milliseconds).

A more intuitive method is to add new components for adaption to new tasks. The progressive network ([Rusu & Rabinowitz et al., 2016](https://arxiv.org/abs/1606.04671)) instantiates a new column for each new task being solved. [Rosenfeld & Tsotsos (2017)](https://arxiv.org/abs/1705.04228) adds a controller to each convolutional layer in a trained neural network that mixes the filters in that layer to adapt to a new task. A new set of controllers is required for each new task.

While current research largely focuses on not forgetting old tasks, eventually we'd like an AI system to be capable of learning a long series of diverse tasks, i.e. lifelong learning. By that time, there may not be a clear distinction between training and testing. It's plausible that through sustained learning, such a system can accumulate a vast amount of knowledge that forms the basis of "common sense", or a "world model." Besides that, we also hope to review studies that focus on augmenting the input and output modules of a deep architecture to adapt to new tasks without forgetting the old ones.

## Evolutionary Algorithms 

[Ellefsen et al. (2015)](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004128) evolve neural networks with a cost for neural connections. This causes modularity and reduces the problem of catastrophic forgetting. Introducing modulatory signals based on nodes' location in the neural network, [Velez & Clune (2017)](https://arxiv.org/abs/1705.07241) show that diffusion-based neuromodulation induces task-specific learning in groups of nodes and connections, which produces functional modules for each task.

## References

* 2017 May 31, Tom Veniat and Ludovic Denoyer. [Learning Time-Efficient Deep Architectures with Budgeted Super Networks](https://arxiv.org/abs/1706.00046). *arXiv:1706.00046*.
* 2017 May 23, Ari Seff, Alex Beatson, Daniel Suo, and Han Liu. [Continual Learning in Generative Adversarial Nets](https://arxiv.org/abs/1705.08395). *arXiv:1705.08395*.
* 2017 May 20, Roby Velez and Jeff Clune. [Diffusion-based neuromodulation can eliminate catastrophic forgetting in simple neural networks](https://arxiv.org/abs/1705.07241). *arXiv:1705.07241*.
* 2017 May 11, Amir Rosenfeld and John K. Tsotsos. [Incremental Learning Through Deep Adaptation](https://arxiv.org/abs/1705.04228). *arXiv:1705.04228*.
* 2017 March 13, Friedemann Zenke, Ben Poole, and Surya Ganguli. [Improved multitask learning through synaptic intelligence](https://arxiv.org/abs/1703.04200). *arXiv:1703.04200*.
* 2017 January 30, Chrisantha Fernando, Dylan Banarse, Charles Blundell, Yori Zwols, David Ha, Andrei A. Rusu, Alexander Pritzel, and Daan Wierstra. [PathNet: Evolution Channels Gradient Descent in Super Neural Networks](https://arxiv.org/abs/1701.08734). *arXiv:1701.08734*.
* 2016 December 2, James Kirkpatrick, Razvan Pascanu, Neil Rabinowitz, Joel Veness, Guillaume Desjardins, Andrei A. Rusu, Kieran Milan, John Quan, Tiago Ramalho, Agnieszka Grabska-Barwinska, Demis Hassabis, Claudia Clopath, Dharshan Kumaran, and Raia Hadsell. [Overcoming catastrophic forgetting in neural networks](https://arxiv.org/abs/1612.00796). *arXiv:1612.00796*.
* 2016 June 15, Andrei A. Rusu, Neil C. Rabinowitz, Guillaume Desjardins, Hubert Soyer, James Kirkpatrick, Koray Kavukcuoglu, Razvan Pascanu, and Raia Hadsell. [Progressive Neural Networks](https://arxiv.org/abs/1606.04671). *arXiv:1606.04671*.
* 2015 April 2, Kai Olav Ellefsen, Jean-Baptiste Mouret, and Jeff Clune. [Neural Modularity Helps Organisms Evolve to Learn New Skills without Forgetting Old Skills](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1004128). *PLOS Computational Biology*, 11(4).
