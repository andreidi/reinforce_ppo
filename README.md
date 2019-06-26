# REINFORCE & PPO PyTorch & Tensorflow implementations

This repository contains Torch & Tensorflow implementations of _*REINFORCE*_ and _*Proximal Policy Optimization*_ Deep Reinforcement Learning methods. Also provided in the repo is the `pong_karpathy.py` file courtesy of Andrej Karpathy from the famous 2016 blog-post [http://karpathy.github.io/2016/05/31/rl/]

### Test #1 TH

`reinforce_test1.py` uses `CartPole-v0` environment for basic REINFORCE. Included are grad calculation examples.
Numeber of steps until a solution is found:    
  Simple G calculation: 1353.0
  Normed disc rewards:   352.0

![cart_normed_disc_rewards](https://github.com/andreidi/pytorch_reinforce_cart/blob/master/cart_reinforce.gif)


### Test #1 Keras

A secondary implementation is provided based on Tensorflow in `reinforce_test1_tf.py` with similar results. 
This particular implementation purpose is to demonstrate how to setup the training process for `REINFOCE` method with Tensorflow. Two methods are provided. 

![cart_anim](20190626_084648_test.gif)

### Test #2

`reinforce_test2.py` uses either vanilla *REINFORCE* or *PPO PG* to solve `'PongDeterministic-v4'` env. Below are the comparision results for both methods:

#### PPO

For the *PPO PG* the policy manages to win some (almost constantly) at episode 350
```
Episode: 350, score:    1.2
  Workers: [-1.  1.  1.  1.  1.  3.  3.  1.]
  
Episode: 355, score:    0.5
  Workers: [ 3.  3. -3.  0.  0.  0. -2.  3.]
  
Episode: 360, score:    1.5
  Workers: [ 3.  3.  3.  1. -2. -2.  3.  3.]
  
Episode: 365, score:    0.1
  Workers: [ 0. -1.  0.  3.  0. -2.  1.  0.]
  
Episode: 370, score:    2.5
  Workers: [5. 1. 3. 3. 1. 3. 1. 3.]
```

and finally around episode  the results are showing good and consistent policy

```
Episode: 500, score:    4.8
  Workers: [3. 5. 5. 5. 5. 5. 5. 5.]
  
Episode: 505, score:    5.0
  Workers: [5. 5. 5. 5. 5. 5. 5. 5.]
  
Episode: 510, score:    5.0
  Workers: [5. 5. 5. 5. 5. 5. 5. 5.]
```
![ppo](https://github.com/andreidi/pytorch_reinforce_cart/blob/master/ppo_results.png)

And here is the agent winning the game:

![ppo](https://github.com/andreidi/pytorch_reinforce_cart/blob/master/PPO_play_test.gif)

#### REINFORCE

in contrast the vanilla *REINFORCE* version does not perform well even after 800 episodes

![ppo](https://github.com/andreidi/pytorch_reinforce_cart/blob/master/REINFORCE_8_workers.png)
```
Episode: 785, score:   -8.2,  time:  1.5 min / 82.0 min
  Workers: [ -3. -12.  -7.  -8. -11.  -9.  -6. -10.]
  
Episode: 790, score:   -6.4,  time:  1.0 min / 81.9 min
  Workers: [ -8.  -5. -10.  -3.  -7.  -7.  -5.  -6.]
  
Episode: 795, score:   -5.9,  time:  0.5 min / 81.9 min
  Workers: [-3. -1. -5. -8. -6. -6. -9. -9.]
  
Episode: 800, score:   -5.5,  time:  0.0 min / 81.9 min
  Workers: [ -2.  -3.  -8. -10.  -1. -10.  -9.  -1.]
```
And here is the test play (REINFORCE agent obviously losing the game):

![ppo](https://github.com/andreidi/pytorch_reinforce_cart/blob/master/REINFORCE_play_test.gif)
