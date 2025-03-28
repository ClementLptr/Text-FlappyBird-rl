# 3MD3220: Reinforcement Learning - Text Flappy Bird Project

## Overview
This repository contains the implementation and analysis for the 3MD3220 Reinforcement Learning Individual Assignment (March 2025). The project applies reinforcement learning (RL) techniques to solve the Text Flappy Bird (TFB) environment, a text-based variant of the classic Flappy Bird game. 

<div align="center">
  <img src="figures/TFB_agent.gif" alt="TFB Agent" height="200"/>
</div>

Two RL agents are implemented and compared:

1. **Monte Carlo Agent**: A first-visit Monte Carlo method with an ε-greedy policy.
2. **Sarsa(λ) Agent**: An on-policy temporal-difference method with eligibility traces, as described in Section 12.7 of *Reinforcement Learning: An Introduction* by Sutton and Barto.

The agents are trained on the `TextFlappyBird-v0` environment, which provides distance-based observations (x, y) to the nearest pipe gap. The project includes a Python notebook showcasing the implementation, training, and evaluation, along with a detailed report interpreting the results.

**Submission Date**: March 28, 2025  
**Author**: Clément Leprêtre  
**Course**: 3MD3220 - Reinforcement Learning  

---

## Repository Structure
```
📂 Text-FlappyBird-rl/
├── README.md              
├── TextFlappyBird_RL.ipynb # Python notebook with implementation and analysis
├── report.pdf             
├── 📂 figures/               
│   ├── state_value_comparison.png
│   ├── reward_convergence.png
│   ├── sweep_sarsa.png
│   ├── sweep_mc.png
│   ├── TFB_game.png
│   └── TFB_agent.gif 
├── requirements.txt
└── .gitignore
```

---

## Prerequisites
To run the code, ensure you have the following installed:
- Python 3.13+
- Required libraries (listed in `requirements.txt`):
  ```bash
  pip install -r requirements.txt
  ```

---

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/ClementLptr/Text-FlappyBird-rl
   cd Text-FlappyBird-rl
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Ensure the `TextFlappyBird-v0` environment is correctly installed via the GitLab repository.

---

## Running the Project
1. Open the Jupyter notebook:
   ```bash
   jupyter notebook TextFlappyBird_RL.ipynb
   ```
2. Execute the cells sequentially to:
   - Set up the TFB environment.
   - Train the Monte Carlo and Sarsa(λ) agents.
   - Generate plots (state-value functions, reward convergence, parameter sweeps).
   - Evaluate performance and generalization.

The notebook is organized with clear sections and comments for easy navigation.

---

## Implementation Details
- **Environment**: `TextFlappyBird-v0` (height=15, width=20, pipe gap=4).
- **Monte Carlo Agent**:
  - Policy: ε-greedy (ε=0.1).
  - Discount factor: γ=0.99.
  - Updates Q-values after each episode.
- **Sarsa(λ) Agent**:
  - Learning rate: α=0.1.
  - Trace decay: λ=0.9.
  - Discount factor: γ=0.99.
  - Uses eligibility traces for faster convergence.
- **State Space**: Basic State Space of the environment based on (x,y) distance from the next pipe.
- **Training**: 5,000 episodes per agent with early stop.

Results are visualized in the notebook and interpreted in the accompanying `report.pdf`.

---

## Results
- **Performance**: Sarsa(λ) converges faster (≈4,000 episodes) and achieves higher rewards (15.2 avg) compared to Monte Carlo (≈7,000 episodes, 12.8 avg).
- **Sensitivity**: Sarsa(λ) is sensitive to λ and α, while Monte Carlo is more robust but slower.
- **Generalization**: Agents struggle with different configurations (e.g., pipe gap=6), indicating overfitting.


See `report.pdf` for detailed analysis, plots, and discussion.

---

## Report
The `report.pdf` is formatted using the Springer LNCS template and includes:
1. Experimental setup and agent differences.
2. Comparison of TFB environment versions.
3. Adaptability to the original Flappy Bird game.
4. Generalization across configurations.
5. Comprehensive results with plots (state-value functions, reward curves, parameter sweeps).

---

## Acknowledgments
- Environment source: [Text Flappy Bird Gym](https://gitlab-research.centralesupelec.fr/stergios.christodoulidis/text-flappy-bird-gym).
- Reference text: Sutton, R. S., & Barto, A. G., *Reinforcement Learning: An Introduction*, 2nd ed.

---

## Contact
For questions or issues, contact Clément Leprêtre at [clement.lepretre@student-cs.fr].
