### Learning Algorithm
We've used a vanilla Deep Q Learning algorithm to train the agent which is defined in the file `agent.py`. The Deep Q Network is given a state, action pair as input and it give the estimated value of the Q-table which contains the probability of taking an action when the agent is at a particular state. 

We have used two important tricks namely, Experience replay and Fixed Q targets. With Experience replay, we store a number of previous experiences i.e. (state, action, reward, next_state, done) tuple that is returned by the environment when taking an action and then after an interval learn from this experience. 

With Fixed Q Targets, we have two instance of our neural network, `qnetwork_target` & `qnetwork_local`. Initially both of them have the same weights. `qnetwork_local` is used for making the prediction when the agent is not learning/training. 

We train the network `qnetwork_local` after every `n` time steps if we have enough experiences in our memory (`ReplayBuffer` which stores the previous experiences). 
We use the following update rule to train the `qnetwork_local`
![enter image description here](https://i.imgur.com/HhZlL5E.png)

Then update the weights of `qnetwork_target` with that of `qnetwork_local`. 

The neural network which is defined in the file `model.py` consists of two hidden layers layers. The first hidden layer has an input of 120 neurons and the second has 64 neurons. The input neurons is the same as the length of the state space and the output is same as the length of the action space. I've also used Relu activation functions throughout the network.

Here are some of the hyper-parameters used in the project. 
```python
BUFFER_SIZE = int(1e5) 				# replay buffer size
BATCH_SIZE = 64 					# minibatch size
GAMMA = 0.99 						# discount factor
TAU = 1e-3 							# for soft update of target parameters
LR = 5e-4 							# learning rate
UPDATE_EVERY = 4 					# how often to update the network
```

### Plot of Rewards
The following plot shows how the agent was able to learn and improve it's score through the episodes. The agent took 416 episodes to get an average of score of more than 13.

![Average score every 100 episodes](https://i.imgur.com/PS67nq3.png)
![Score vs Episode](https://i.imgur.com/GxU9hIq.png)

### Ideas for future work. 
- Eventually I want to implement the Rainbow algorithms with includes all the 6 improvements to the DQN algorithm. But first, I'd like to implement the Double DQN (DDQN).
- Will try to implement Batch Normalisation and also try with deeper networks to see if that improves the performance. 
- Instead of stopping training when the agent reaches 13 average score. I'd let it keep learning for more episodes, which would definitely increase the efficiency of the agent when testing it out.
