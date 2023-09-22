<h1 align='center'>AWS DeepRacer Models</h1>

<div align='center'>

![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fgithub.com%2FSDC-Lab%2FDeepRacer-Models&countColor=%23007ec6&style=flat-square)

![Stars](https://img.shields.io/github/stars/SDC-Lab/DeepRacer-Models?style=flat-square&logo=GitHub)
![Forks](https://img.shields.io/github/forks/SDC-Lab/DeepRacer-Models?style=flat-square&logo=GitHub)
![RepoSize](https://img.shields.io/github/repo-size/SDC-Lab/DeepRacer-Models?style=flat-square&logo=GitHub)
![GitHub commit activity (branch)](https://img.shields.io/github/commit-activity/t/SDC-Lab/DeepRacer-Models?style=flat-square&logo=GitHub)
![GitHub last commit (branch)](https://img.shields.io/github/last-commit/SDC-Lab/DeepRacer-Models/main?style=flat-square&logo=GitHub&color=blue)

[![Static Badge](https://img.shields.io/badge/SDC_Lab-Click%20Here-blue?style=flat-square&link=https%3A%2F%2Fsdclab.cdms.westernsydney.edu.au%2F)](https://sdclab.cdms.westernsydney.edu.au/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat-square&logo=linkedin)](https://www.linkedin.com/company/sdcomlab)
[![SDC Lab YT](https://img.shields.io/badge/YouTube-%40SDCLab-blue?style=flat-square&logo=YouTube)](https://www.youtube.com/@SDCLab/videos)

</div>

## Overview

This repository contains valuable insights, practical recommendations, and model details to help you elevate the performance of your AWS DeepRacer on physical racetracks. Achieving success in the physical environment requires a combination of stability, consistency, and speed. Whether you're a student or a seasoned DeepRacer enthusiast, this repository will provide you with the knowledge you need to optimise your racing experience.

## Table of Contents

1. [Enhancing AWS DeepRacer Physical Track Performance](models/README.md/#enhancing-aws-deepracer-physical-track-performance)
   1. [Recommendations](models/README.md/#recommendations)
      1. [Recommendation 1: Start At Lower Speeds](models/README.md/#recommendation-1-start-at-lower-speeds)
      2. [Recommendation 2: Train On Different Tracks](models/README.md/#recommendation-2-train-on-different-tracks)
      3. [Recommendation 3: Increase The Minimum Speed](models/README.md/#recommendation-3-increase-the-minimum-speed)
      4. [Recommendation 4: Calibrate The Physical Car](models/README.md/#recommendation-4-calibrate-the-physical-car)
      5. [Recommendation 5: Minimise Noise In The Physical Environment](models/README.md/#recommendation-5-minimise-noise-in-the-physical-environment)
      6. [Recommendation 6: Proportionally Penalise Off-Track Behaviour](models/README.md/#recommendation-6-proportionally-penalise-off-track-behaviour)
      7. [Recommendation 7: Set Up The Track On A Flat Surface](models/README.md/#recommendation-7-set-up-the-track-on-a-flat-surface)
      8. [Recommendation 8: Use A Discrete Action Space](models/README.md/#recommendation-8-use-a-discrete-action-space)
   2. [StayOnTrack](models/README.md/#model-1-stayontrack)
      1. [Reward Function](models/README.md/#reward-function)
      2. [Hyperparameter Selection and Time](models/README.md/#hyperparameter-selection-and-time)
      3. [Discrete Action Space](models/README.md/#discrete-action-space)
      4. [Training Reward Graph](models/README.md/#training-reward-graph)
      5. [Simulation Evaluation](models/README.md/#simulation-evaluation)
      6. [Physical Track Test](models/README.md/#physical-track-test)
   3. [CenterAlignModel](models/README.md/#model-2-centeralignmodel)
      1. [Reward Function](models/README.md/#reward-function-1)
      2. [Hyperparameter Selection and Time](models/README.md/#hyperparameter-selection-and-time-1)
      3. [Continuous Action Space](models/README.md/#continuous-action-space)
      4. [Training Reward Graph](models/README.md/#training-reward-graph-1)
      5. [Simulation Evaluation](models/README.md/#simulation-evaluation-1)
      6. [Physical Track Test](models/README.md/#physical-track-test-1)
   4. [NaviGator](models/README.md/#model-3-navigator)
      1. [Reward Function](models/README.md/#reward-function-2)
      2. [Hyperparameter Selection and Time](models/README.md/#hyperparameter-selection-and-time-2)
      3. [Action Space](models/README.md/#discrete-action-space-1)
      4. [Training Reward Graph](models/README.md/#training-reward-graph-2)
      5. [Simulation Evaluation](models/README.md/#simulation-evaluation-2)
      6. [Physical Track Test](models/README.md/#physical-track-test-2)

## Getting Started

To access the models and resources on a physical racetrack, you can easily download this repository to get started. Before you proceed, please ensure you have the following prerequisites in place:

### Prerequisites

- **AWS DeepRacer Car:** You must have access to an AWS DeepRacer car to make use of the models and recommendations provided in this repository. The physical car is essential for testing and applying the insights you'll gain here.

- **AWS Account:** You need an active AWS (Amazon Web Services) account. If you don't have one, you can sign up for AWS at [AWS Signup](https://aws.amazon.com/).

### Installation

Now, follow these steps to download the repository:

- **Clone the Repository:** Open your command line or terminal and use the following command to clone this repository to your local machine:

  ```shell
  git clone https://github.com/SDC-Lab/DeepRacer-Models.git
  ```

## Project Structure

The repository is organised as follows:

1. **models/**: This directory contains the DeepRacer models and associated files. Each model is organised into its own subdirectory, and the relevant files for each model can be found there.

   - _StayOnTrack_: Contains the files and information related to the StayOnTrack model.
   - _CenterAlignModel_: Contains the files and information related to the CenterAlignModel.
   - _NaviGator_: Contains the files and information related to the NaviGator model.

2. **images/**: This directory contains images used in the README, particularly for showcasing training reward graphs and visual representations of model performance.

   - _Training Reward Graphs_: Graphical representations of the training progress and reward curves for different models.

3. **videos/**: This directory stores videos demonstrating the DeepRacer models in action on physical tracks. Videos can provide a more visual understanding of the models' performance.

   - _StayOnTrack_: Video demonstrating the performance of the StayOnTrack model.
   - _CenterAlignModel_: Video showcasing the CenterAlignModel in action.
   - _NaviGator_: Video illustrating the performance of the NaviGator model.

## Helpful Links

Here are some helpful links and resources to enhance your AWS DeepRacer experience and understanding of reinforcement learning:

### SDC Lab Links

- [Introduction to AWS DeepRacer](https://www.linkedin.com/pulse/introduction-aws-deepracer-bahman-javadi) - An introductory article providing insights into AWS DeepRacer by Bahman Javadi.
- [AWS DeepRacer Models For Beginners](https://www.linkedin.com/pulse/aws-deepracer-models-beginners-bahman-javadi?trk=article-ssr-frontend-pulse_more-articles_related-content-card) - A guide aimed at beginners, covering AWS DeepRacer models by Bahman Javadi.
- [Sample of Reward Functions for AWS DeepRacer](https://www.linkedin.com/pulse/samples-reward-functions-aws-deepracer-bahman-javadi?trk=article-ssr-frontend-pulse_more-articles_related-content-card) - An exploration of sample reward functions for AWS DeepRacer by Bahman Javadi.

### Other Links

- [AWS DeepRacer Documentation](https://docs.aws.amazon.com/deepracer/latest/developerguide/what-is-deepracer.html) - Official documentation for AWS DeepRacer, including getting started guides, tutorials, and reference materials.
- [AWS DeepRacer Console](https://console.aws.amazon.com/deepracer/home) - Access the AWS DeepRacer Console to manage your DeepRacer car, create simulations, and deploy custom models.
- [AWS DeepRacer Community](https://deepracing.io/) - Join the AWS DeepRacer Community to connect with other enthusiasts, ask questions, and share your experiences.
- [Deep Reinforcement Learning](https://www.deeplearningbook.org/) - The Deep Learning book by Ian Goodfellow, Yoshua Bengio, and Aaron Courville has a section on reinforcement learning that provides a solid theoretical foundation.
