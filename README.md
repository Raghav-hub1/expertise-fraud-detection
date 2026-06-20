# Expertise Fraud Detection using Reinforcement Learning

This project explores the use of Reinforcement Learning (RL) for detecting potential expertise fraud in candidate evaluations. The goal is to model a screening process where an agent decides whether to PASS a candidate, FLAG them for possible inconsistencies, or INVESTIGATE further through additional questioning.

The project uses synthetic candidate profiles and interview responses to simulate different levels of expertise, consistency, and evidence quality.

## Features Used

The candidate evaluation process is based on several indicators:

* Consistency between profile claims and interview responses
* Alignment between claimed skills and supporting evidence
* Quality and depth of technical explanations
* Performance on follow-up questions
* Overall response reliability

## Approach

The problem is modeled as a sequential decision-making task.

* Synthetic candidate profiles are generated with varying authenticity levels.
* Candidate responses are scored using predefined evaluation criteria.
* An RL agent interacts with the environment and learns an action policy.
* The agent receives rewards for correct decisions and penalties for incorrect classifications or unnecessary investigations.

Possible actions:

* PASS
* FLAG
* INVESTIGATE

## Project Structure

```text
├── README.md
├── requirements.txt
├── thesis.md
├── data/
│   └── synthetic_candidates.json
└── src/
    ├── synthetic_data.py
    ├── probe_score.py
    ├── features.py
    ├── environment.py
    ├── agent.py
    └── train.py
```

## Installation

```bash
pip install -r requirements.txt
```

## Quick Start

Generate synthetic candidate data:

```bash
python -m src.synthetic_data generate 700
```

Train the agent:

```bash
python -m src.train
```

Train using existing data:

```bash
python -m src.train --data data/synthetic_candidates.json
```

Generate and save data during training:

```bash
python -m src.train --save --n 700
```

Run individual modules:

```bash
python -m src.probe_score
python -m src.features
python -m src.synthetic_data
python -m src.environment
python -m src.agent
```

## Results

The RL agent learns a decision policy for candidate evaluation by balancing classification accuracy with the cost of additional investigation steps. The project serves as a proof-of-concept for applying reinforcement learning to structured screening workflows.

## Future Improvements

* More realistic candidate generation
* Additional interview signal features
* Deep Reinforcement Learning methods
* Calibration and uncertainty estimation
* Evaluation on real-world datasets

```
```
