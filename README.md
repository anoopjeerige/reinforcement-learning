# Basics of artificial neural networks, deep learning, and reinforcement learning
This repository contains notebooks and python modules implemented in Tensorflow that explore:
 - Basics of Artificial Neural Networks
 - Deep Learning
 - Reinforcement Learning (Policy Gradient and Q-Learning)
 
 The Deep Learning concepts have been mainly taken from the book "Hands-On Machine Learning with Scikit-Learn and TensorFlow" by Aurélien Géron.
 The Reinforcement Learning alogrithms have been mainly taken from reinforcement-learning repo by Denny Britz.
 
## Reinforcement Learning (Environment - Atari Breakout)
- Q-Learning
  Implementation of Deep Q-Learning
  #### Running
  ```
  ./train.py
  ```
  #### Pre-Trained Model and Checkpoint
  Download the pre-trained model and tensorflow checkpoint files from https://drive.google.com/open?id=1yPP3gdC8dQQEG4MLNjsxEnZWg28-d83M
  
- Policy Gradient
  Implementation of A3C (Asynchronous Advantage Actor-Critic)

  #### Running
  ```
  ./train.py --model_dir /tmp/a3c --env Breakout-v0 --t_max 5 --eval_every 300 --parallelism 8
  ```

  See `./train.py --help` for a full list of options. Then, monitor training progress in Tensorboard:

  ```
  tensorboard --logdir=/tmp/a3c
  ```
  #### Pre-Trained Model and Checkpoint
  Download the pre-trained model and tensorflow checkpoint files from https://drive.google.com/open?id=11Y63jXjLj_M4dozrVT2WUbPEbDDICvTI
  
  #### Components

  - [`train.py`](train.py) contains the main method to start training.
  - [`estimators.py`](estimators.py) contains the Tensorflow graph definitions for the Policy and Value networks.
  - [`worker.py`](worker.py) contains code that runs in each worker threads.
  - [`policy_monitor.py`](policy_monitor.py) contains code that evaluates the policy network by running an episode and saving rewards to Tensorboard.

## Gameplay
Video of the trained agents playing Atari breakout
https://drive.google.com/open?id=14msaniL7UggcyLN8vc75QXGdL1nCvyyO

## Reference:
 - Book : Gron, A. (2017). Hands-On Machine Learning with Scikit-Learn and TensorFlow: Concepts, Tools, and Techniques to Build Intelligent Systems. O'Reilly Media, Inc.
 - Deep Learning with Tensorflow repo : https://github.com/ageron/handson-ml
 - Reinforcement Learning Algorithms repo : https://github.com/dennybritz/reinforcement-learning
