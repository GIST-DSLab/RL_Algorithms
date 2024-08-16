# Enhancing Analogical Reasoning in the Abstraction and Reasoning Corpus via Model-Based RL [[PDF](https://github.com/user-attachments/files/16637774/WorldModel_IJCAIW2024_May10_main12p.1.pdf)]
The implementation of experiments comparing Proximal Policy Optimization (PPO) and DreamerV3 within the ARCLE environment.

Code instructions are located within each algorithm's folder.

## Experimental setting
- Actions - 5 Operations (Rotate 90, Rotate 270, Horizontal Flip, Vertical Flip), and entire selection.
- Tasks: 4 simple tasks, augmented 1000 demo pairs and 100 test pairs.
- Metric - number of corrected grid in test pairs.

![image](https://github.com/user-attachments/assets/138611b3-824f-47e2-a5ab-35f4362bb960)


## Research Question

- RQ1: Learning a Single Task
- RQ2: Reasoning about Tasks Similar to Pre-Trained Task
- RQ3: Reasoning about Sub-Tasks of Pre-Trained Task
- RQ4: Learning Multiple Tasks Simultaneously 
- RQ5: Reasoning about Merged-Tasks of Pre-Trained Tasks

In this work, we focus on addressing Research Questions 1 and 2.

## Results

### RQ1: Learning a Single Task
![image](https://github.com/user-attachments/assets/a462b685-a8a6-418c-8257-872c615e093d)

- For complex tasks(Diagonal Flip), Model-Based RL can learn complex tasks, showing higher Accuracy and Sample Efficiency.
- For simple tasks(Rotate and Horiontal Flip), both algorithms have no significant differences
- DremerV3 have difficulty in learning N x N grid size tasks.

### RQ2: Reasoning about Tasks Similar to Pre-Trained Task
![image](https://github.com/user-attachments/assets/a1cacf44-fe6c-4e24-baf5-d97da135fb03)

- DreamerV3 successfully adapted to unseen grid sizes that have a share rule.
- Both algorithms are struggled with learning N x N Diagonal Flip Tasks, leading to poor performance in 3 x 3 Diagonal Flip adaptation.

## Algorithm Details

### Proximal Policy Optimization (PPO)
- [paper](https://arxiv.org/pdf/1707.06347)
- [code](https://github.com/DLR-RM/stable-baselines3/blob/master/stable_baselines3/ppo/ppo.py)

We reimplemented the experiments from the [first implementation](https://github.com/ku-dmlab/arc_trajectory_generator) of PPO on ARCLE environments.

### Mastering Diverse Domains through World Models (Dreamerv3)
- [paper](https://arxiv.org/pdf/2301.04104v1)
- [code](https://github.com/NM512/dreamerv3-torch)

This is pythorch implementation of [authors' DreamerV3 implementation](https://github.com/danijar/dreamerv3)
