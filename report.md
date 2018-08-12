### Learning Algorithm
We've used a vanilla Deep Q Learning algorithm to train the agent. The Deep Q Network is given a state, action pair as input and it give the estimated value of the Q-table which contains the probability of taking an action when the agent is at a particular state. 

We have used two important tricks namely, Experience replay and Fixed Q targets. With Experience replay, we store a number of previous experiences i.e. (state, action, reward, next_state, done) tuple that is returned by the environment when taking an action and then after an interval learn from this experience. 

With Fixed Q Targets, we have two instance of our neural network, `qnetwork_target` & `qnetwork_local`. Initially both of them have the same weights. `qnetwork_local` is used for making the prediction when the agent is not learning/training. 

We train the network `qnetwork_local` after every `n` time steps if we have enough experiences in our memory (`ReplayBuffer` which stores the previous experiences). 
We use the following update rule to train the `qnetwork_local`
![enter image description here](https://i.imgur.com/HhZlL5E.png)
Then update the weights of `qnetwork_target` with that of `qnetwork_local`. 


