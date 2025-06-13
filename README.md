
# Quantifying Cybersecurity–QoS Trade-Offs in Smart Hospitals

This repository provides all the source code, simulations, and visualizations for the paper:

 **Quantifying Cybersecurity–QoS Trade-Offs in Smart Hospitals: A Comparative Study Using CSPNs and Markovian Agent Models** (2025)

The project explores how mitigation actions taken to contain cyberattacks in a smart hospital environment may themselves impact Quality of Service (QoS), potentially violating Service Level Agreements (SLAs). Two complementary modeling paradigms are developed and compared:

- **Colored Stochastic Petri Nets (CSPNs)**: token-level, discrete-event simulations with stochastic timing.
- **Markovian Agent Models (MAMs)**: continuous-time, population-level models governed by coupled differential equations.

---

##  Project Scope

This dual-model approach is applied to a realistic healthcare scenario involving ECG devices, adaptive attackers, alert systems, security mitigators, and human operators. The models capture both the dynamics of cyberattacks and the systemic response, quantifying trade-offs between **resilience** and **performance degradation**.

---

##  Repository Structure

```

.
├── src/
│   ├── simulate\_cspn.py         # CSPN simulation (stochastic transitions, token tracking)
│   ├── plot\_latency\_cdf.py      # Generates CDF plot from latency records
│   ├── mam\_odes.py              # ODE system for the Markovian Agent Model
│   ├── mam\_plot.tex             # LaTeX TikZ code for MAM diagram
│   └── graphviz\_cspn.py         # Graphviz script to draw the CSPN layout
│
├── plots/
│   ├── latency\_hist.png         # Histogram of alert-to-mitigation latency
│   ├── latency\_cdf.pdf          # Cumulative distribution of latency
│   ├── mean\_tokens.png          # Average token count per place
│   ├── throughput.png           # Transition firing counts
│   ├── cspn.pdf                 # CSPN structure (Graphviz)
│   └── mam\_onepanel.pdf         # MAM population trajectories
│
├── paper/
│   ├── main.tex                 # LaTeX source of the article
│   └── bibliography.bib         # BibTeX references
│
├── requirements.txt             # List of required Python packages
└── README.md                    # This file

````

---

##  How to Use

###  Setup

Make sure you have Python 3.9+ and install dependencies:

```bash
pip install -r requirements.txt
````

###  Run the CSPN Simulation

```bash
python src/simulate_cspn.py
```

This performs 100 runs of the CSPN model and saves:

* Latency histograms
* Token count per place
* Transition throughput statistics

###  Generate Latency CDF

```bash
python src/plot_latency_cdf.py
```

Produces a cumulative distribution (`latency_cdf.pdf`) from alert-to-mitigation latencies.

###  Solve and Plot MAM

```bash
python src/mam_odes.py
```

Solves the MAM using `scipy.integrate.solve_ivp` and plots population dynamics.

###  Visualize the CSPN Structure

```bash
python src/graphviz_cspn.py
```

Renders a visual diagram (`cspn.pdf`) of the colored stochastic Petri net.

---

##  Citation

If you use this work in your research, please cite:

```bibtex
@article{your2025paper,
  title = {Quantifying Cybersecurity--QoS Trade-Offs in Smart Hospitals: A Comparative Study Using CSPNs and Markovian Agent Models},
  author = {Your Name and Collaborators},
  year = {2025},
  journal = {To Appear},
}
```

---

##  License

This project is licensed under the MIT License. You are free to use, modify, and distribute it with attribution.

---
