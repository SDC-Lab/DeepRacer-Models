## Overview

This folder includes some tests for the physical racetrack capabilities of AWS DeepRacer. The experiment focused on evaluating the impact of hyperparameters on the physical environment. Hyperparameters such as gradient descent batch size and loss type were changed systematically as well as training time settings. It was uncovered that in the simulated environment, models with a higher gradient descent batch size had better performance than models with a lower gradient descent batch size. Alternatively, in the physical environment, a gradient descent batch size of 128 appears to be preferable. It was found that models using the loss type of Huber outperformed models that used the loss type of MSE in both the simulated and physical environments. Please refere to the report for more information. 