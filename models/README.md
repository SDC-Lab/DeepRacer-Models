# **Enhancing AWS DeepRacer Physical Track Performance**

This article aims to provide valuable insights and practical recommendations to elevate the performance of AWS DeepRacer on physical racetracks. The determinant of achieving a successful model is the optimal combination of stability, consistency, and speed. This becomes paramount as AWS DeepRacer transcends virtual simulations and confronts the unique challenges presented by physical racetracks. In addition, models constructed by students will be showcased. The relevant information such as hyperparameter selection, action space choice, reward function, and results from the physical track testing will be displayed.

## **Recommendations**

### **Recommendation 1: Start At Lower Speeds**

Speed in the AWS DeepRacer console can be scaled. Begin testing the model at a low speed such as 20%. Gradually increase the speed until the agent moves comfortably. When operating at lower speeds, the agent might encounter halting or stalling issues. In such cases, a simple solution to reset its behaviour is to lift the agent up.

### **Recommendation 2: Train On Different Tracks**

By experiencing different track-specific features, the model gains valuable insights that can equip the agent with adaptability and decision-making skills to handle various challenges. Ultimately, this leads to improved performance on physical racetracks.

### **Recommendation 3: Increase The Minimum Speed**

A low minimum speed can lead to the agent stalling or struggling to initiate movement on the physical racetrack. By setting a more suitable minimum speed, such as 1.3 meters per second, the model gains better momentum and is less likely to encounter halting issues on the physical racetrack.

### **Recommendation 4: Calibrate The Physical Car**

Proper calibration facilitates smooth execution of the learned behaviours and decisions made by the model during training, effectively translating them into real-world actions. By meticulously calibrating the physical car, the agent excels on the physical racetracks.

### **Recommendation 5: Minimise Noise In The Physical Environment**

Background distractions, light reflections, and gaps between barriers can introduce uncertainties that impact the agent’s decision-making. By creating a controlled and focused environment, the agent can better interpret sensor inputs and make accurate navigation choices.

### **Recommendation 6: Proportionally Penalise Off-Track Behaviour**

By discouraging the model from deviating from the track, the agent becomes more adept at staying within the designated boundaries during runs on the physical track.

### **Recommendation 7: Set Up The Track On A Flat Surface**

Bumps or uneven surfaces can hinder the agent's navigation and stability during races, potentially causing the physical car to get stuck. A level and smooth track surface ensures a consistent environment, enabling the agent to execute learned behaviours more effectively and achieve superior performance on physical racetracks.

### **Recommendation 8: Use A Discrete Action Space**

It is advisable to use discrete action spaces instead of continuous ones. Continuous action spaces have demonstrated issues, including significant halts and an inability to complete laps on the physical track.

<!-- ### **Recommendation 9: Replicate The Simulated Environment** -->

## **Model 1) v1-SpeedOnTrack**

### **Hyperparameter Selection**

| Hyperparameters                                                      | Values     |
| -------------------------------------------------------------------- | ---------- |
| Gradient descent batch size                                          | 64         |
| Number of epochs                                                     | 10         |
| Learning rate                                                        | 0.000001   |
| Entropy                                                              | 0.01       |
| Discount factor                                                      | 0.999      |
| Loss type                                                            | Huber loss |
| Number of experience episodes between each policy-updating iteration | 20         |

### **Action Space**

| Action Number | Steering | Speed |
| :-----------: | :------: | :---: |
|       0       |   -30    |  1.4  |
|       1       |   -30    |  1.6  |
|       2       |   -30    |  1.8  |
|       3       |   -15    |  1.4  |
|       4       |   -15    |  1.6  |
|       5       |   -15    |  1.8  |
|       6       |    0     |  1.4  |
|       7       |    0     |  1.6  |
|       8       |    0     |  1.8  |
|       9       |    15    |  1.4  |
|      10       |    15    |  1.6  |
|      11       |    15    |  1.8  |
|      12       |    30    |  1.4  |
|      13       |    30    |  1.6  |
|      14       |    30    |  1.8  |

### **Reward Function**

```python
def reward_function(params):
    reward = 1e-3
    PENALTY = 5.0

    if not params['all_wheels_on_track']:
        reward -= PENALTY * params['distance_from_center']
    else:
        reward += 1

    return float(reward)
```

### **Physical Track Test**

https://github.com/SDC-Lab/DeepRacer-Models/assets/115546292/581db9bf-c458-45d3-a433-d1b258593eb8

