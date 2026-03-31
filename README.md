# AGENT-MISCON: Learning Meta-Strategies to Contain Misinformation in Social Networks

**Authors:** Mir Murtaza (1*), Rauf Ahmed Shams Malick (1,2), Hocine Cherifi (3)

**Affiliations:**
1. National University of Computer and Emerging Sciences, Karachi, Pakistan
2. GU Tech, Karachi, Pakistan
3. University of Burgundy, France
* *Corresponding Author:* K214810@nu.edu.pk

---

## Abstract
Containing misinformation on social networks is a significant challenge, often modeled as a competitive influence game between an adversary and a defender. Existing defense methods largely rely on static heuristics or exact optimization. However, heuristics are often predictable and exploitable by strategic opponents, while exact optimization suffers from combinatorial explosion, making it intractable as network complexity increases. 

This paper introduces Adaptive Graph Neural Agent for Misinformation Containment (**AGENT-MISCON**), a novel framework in which agents learn an adaptive *meta-strategy*—selecting the best heuristic from a discrete set based on the current network state. By abstracting the action space from individual node selection ($N$) to high-level strategies ($K \ll N$), our approach resolves the dimensionality bottleneck inherent in graph-based reinforcement learning. 

We model the environment as a two-player, zero-sum sequential game under a Competitive Linear Threshold (CLT) model. Each agent's strategy is represented by a Graph Attention Network (GAT) combined with a Deep Q-Network (DQN). We implement and compare two learning paradigms: standard Independent DQN (IND) and game-theory-aware Minimax DQN (MM). We conduct experiments on synthetic Barabási–Albert (BA), Erdős–Rényi (ER), and Watts–Strogatz (WS) networks, as well as empirical datasets (Email, Facebook, Polblogs). 

Our results show that network topology, not agent strategy, is the dominant factor in containment outcomes. Final influence varies significantly across network types (Kruskal–Wallis H=176.6, p < 0.0001), with empirical networks proving significantly harder to defend than synthetic ones. Furthermore, we identify structural entropy as a key predictor of network vulnerability; it shows a significant negative correlation with final influence (Spearman's $\rho = -0.692$, $p = 0.013$). This work provides a robust foundation for developing learning-based defense mechanisms that are invariant to network size.

---

## Data
The datasets used to support the findings of this study are included in this repository. 
* **`[Folder/Filename 1].csv`**: Contains the synthetic network structures (BA, ER, WS) used for baseline training and evaluation.
* **`[Folder/Filename 2].csv`**: Contains the empirical real-world network datasets (Email, Facebook, Polblogs).
* **`[Folder/Filename 3].csv`**: Contains the logged output metrics, structural entropy scores, and final influence spread results used for our statistical analysis.

*(Note: Please update the filenames above to match your actual repository structure).*

---

## Interactive Simulation
An interactive web-based simulation of the influence spread and containment strategies can be accessed directly in your browser without any setup.

🌐 **[Launch Interactive Simulation Here](https://[YourUsername].github.io/[YourRepoName]/simulation.html)** *(Note: Once you activate GitHub Pages as described in the setup guide, replace the URL above with your actual GitHub Pages link).*

---

## Code & Reproduction
To ensure full reproducibility of the AGENT-MISCON framework, the codebase has been divided into implementation (training) and evaluation (simulation/results) modules, hosted on cloud platforms for easy access.

### 1. Model Implementation & Training (Kaggle)
The heavy model training, including the GAT and DQN components (Independent and Minimax), is hosted on Kaggle. This notebook contains the core logic for the meta-strategy learning framework.
* **Implementation Code:** [View and Run on Kaggle](https://www.kaggle.com/code/mathifydata/rwminimaxdqn/edit) 
*(Note: For public sharing, you may want to share the public viewing link rather than the `/edit` URL).*

### 2. Simulation (Google Colab)
The simulation code used to run the trained agents against the Competitive Linear Threshold (CLT) environment can be run interactively in Google Colab.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1CsZX8T4bZMw_5tz8HZRzHzX7dPiCXqNM?authuser=0#scrollTo=dxYFd-2EvCZb)

### 3. Results Analysis (Google Colab)
The statistical analysis, including the Kruskal-Wallis tests and Spearman's rank correlation regarding structural entropy and network vulnerability, can be verified here.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1vbMJmeFza2prcDa3OHTn5eBUuyxaLxMy)

---

## License
The software code in this repository is licensed under the [MIT License](LICENSE). The datasets (.csv) and simulation web files (.html) are licensed under a [Creative Commons Attribution 4.0 International License (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
