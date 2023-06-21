# README

Code for generating fair trajectories for robots.

## Scripts
- `experiment_central.py`: runs a set of experiment trials for finding fair trajectories using a centralized method
- `experiment_distributed.py`: runs a set of experiment trials for finding fair trajectories using a distributed method
- `objective.py`: defines class responsible for formulating the optimization problem that finds fair trajectories
- `run_experiments.sh`: runs a series of experiments for different notions of fairness and robot team size
- `generate_trajectories.py`: generates the robot trajectories using code excerpt from https://github.com/markwmuller/RapidQuadrocopterTrajectories stored in `trajectorygenerationcodeandreas`

## Fairness Notions
The scripts `experiment_central.py` and `experiment_distributed.py` take in a `--notion` argument for the fairness notion to be optimized over robot inputs `u` in the experiment. The following notions are implemented:

- set `--notion 1`: u^TQu, an _energy_ term is optimized where Q is positive definite.
- set `--notion 0`: u^TQu + f1 is optimized, where f1 is the variance of the normalized energy of the inputs
- set `--notion 2`: no energy term or fairness notion is optimized
- set `--notion 3`: u^TQu + f4 is optimized, where f4 is the variance of the total energy surge of the inputs
- set `--notion 4`: only f1 is optimized
- set `--notion 5`: only f4 is optimized
