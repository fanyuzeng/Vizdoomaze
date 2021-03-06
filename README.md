
# ViZDoomaze
ViZDoomaze is a series of mazes based on [ViZDoom](https://github.com/mwydmuch/ViZDoom). It includes empty mazes and mazes with obstacles, based on the indoor plans of undecorated departments. These mazes have complicated structures on various scales. In Vizdoomaze, the color of the ceiling and the floor is earth-yellow, while the gray wall resembles brickwork. We set a red tower as a target object, which is randomly positioned in the maze at each training episode. In addition, some green towers representing obstacles randomly are placed in the mazes with obstacles. 

The agent’s objective in navigation tasks is to find the red tower, and the agent has 3 available actions: turn left, turn right and move forward. If the agent reaches the correct target object, it obtains a positive reward (+1.0), whereas if it does not reach the target object, it obtains a negative living reward (-0.0001). In the mazes with obstacles, the agent obtains a negative reward(-0.01) when it hits an obstacle.

### Requirements:
- [ViZDoom](https://github.com/mwydmuch/ViZDoom)


# Installation
    git clone https://github.com/fanyuzeng/ViZDoomaze.git  
    cd ViZDoomaze   
    pip install -e .    


# Mazes
The naming rule is "bedroom type-serial number". 
- All interior floor plans for one bedroom are named from [one_1](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/one) to [one_20](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/one).
- All interior floor plans for two bedrooms are named from [two_1](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/two) to [two_20](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/two).
- All interior floor plans for three bedrooms are named from [three_1](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/three) to [three_20](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/three).
- All interior floor plans for four bedrooms are named from [four_1](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/four) to [four_20](https://github.com/fanyuzeng/ViZDoomaze/tree/main/vizdoomaze/envs/scenarios/four).


# Example Usage
```python
import gym        
import vizdoomaze         
env = gym.make('vizdoomazeOne1-v0')      
episodes=10     
for i in range(episodes)：     
    print("Episodes #" + str(i+1))      
    observation = env.reset()
    steps = 100
    for step in range(steps): 
        env.render()      
        action = env.action_space.sample()      
        observation, reward, done, info = env.step(action)      
        if done:      
            print("Episode finished after {} timesteps".format(step+1))    
            break     
env.close()
```
