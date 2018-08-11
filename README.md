# Deep Q Learning implementation
### The Environment

For this project, we will train an agent to navigate (and collect bananas!) in a large, square world.

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

-   **`0`**  - move forward.
-   **`1`**  - move backward.
-   **`2`**  - turn left.
-   **`3`**  - turn right.

The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Getting Started
The project environment is similar to, but **not identical to** the Banana Collector environment on the [Unity ML-Agents GitHub page](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#banana-collector).

For this project, you will  **not**  need to install Unity - this is because we have already built the environment for you, and you can download it from one of the links below. You need only select the environment that matches your operating system:

-   Linux:  [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
-   Mac OSX:  [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
-   Windows (32-bit):  [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
-   Windows (64-bit):  [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)

Then, place the file in the  root folder of this GitHub repository, and unzip (or decompress) the file.

(_For Windows users_) Check out  [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64)  if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

(_For AWS_) If you'd like to train the agent on AWS (and have not  [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use  [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip)  to obtain the "headless" version of the environment. You will  **not**  be able to watch the agent without enabling a virtual screen, but you will be able to train the agent. (_To watch the agent, you should follow the instructions to  [enable a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md), and then download the environment for the  **Linux**  operating system above._)

### Dependencies 
You'll need to install Conda and Python 3.6 for this project. You can follow [
](https://conda.io/docs/user-guide/install/index.html) guide to do the installation. 

To set up your python environment to run the code in this repository, follow the instructions below.

1.  Create (and activate) a new environment with Python 3.6.
    
    -   **Linux**  or  **Mac**:
    ```
    conda create --name dqn-banana python=3.6
    source activate dqn-banana
    ```
    -   **Windows**:
    ```
    conda create --name drlnd python=3.6 
    activate drlnd
    ```
2.  Clone the repository (if you haven't already!), and navigate to the  `python/`  folder. Then, install several dependencies.
	```
	git clone https://github.com/thisisppn/deep-q-learning-navigation.git
	cd deep-reinforcement-learning/python
	pip install .
	pip install jupyter
	```

4.  Run `jupyter notebook` and open the Navigation.ipynb file and execute the cells serially to start the training.
