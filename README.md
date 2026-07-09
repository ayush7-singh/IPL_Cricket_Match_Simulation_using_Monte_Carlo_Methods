# 🏏 IPL Cricket Match Simulation using Monte Carlo Methods

A data-driven IPL cricket match simulator that predicts realistic match outcomes using **Monte Carlo Simulation** and **ball-by-ball historical IPL data** from ESPNcricinfo.

The project models player performance statistically and simulates thousands of cricket matches to estimate scores, win probabilities, and other match statistics.

---

## 📌 Project Overview

Cricket is inherently uncertain—every delivery can produce multiple possible outcomes. Instead of trying to predict the exact result of every ball, this project models each delivery probabilistically using historical player statistics.

Using **Monte Carlo Simulation**, thousands of virtual IPL matches are generated to estimate:

* Match-winning probabilities
* Expected first innings scores
* Distribution of total scores
* Individual player performances
* Realistic innings progression

The simulation is based on actual IPL ball-by-ball data and uses probability distributions fitted separately for each player.

---

## 🎯 Objectives

* Simulate IPL matches ball-by-ball.
* Model batsmen and bowlers using statistical probability distributions.
* Estimate realistic match outcomes.
* Validate the model using unseen IPL season data.
* Demonstrate the application of Monte Carlo Simulation in sports analytics.

---

## 📊 Dataset

### Training Data

* IPL 2021
* IPL 2022
* IPL 2023
* IPL 2024

### Validation Data

* IPL 2025

### Data Source

* ESPNcricinfo Ball-by-Ball Data
* Python `cricdata` library

Older seasons are assigned lower weights while recent seasons receive higher importance using recency weighting.

---

## 🧠 Methodology

The simulator models five random variables for every player.

### 1. Batsman Survival

Distribution:

* Geometric Distribution

Represents:

* Number of balls faced before dismissal.

---

### 2. Runs per Ball

Distribution:

* Categorical Distribution

Possible outcomes:

* 0
* 1
* 2
* 3
* 4
* 6

---

### 3. Extras

Distribution:

* Bernoulli Distribution

Represents:

* Wide
* No-ball probability

---

### 4. Extra Runs

Distribution:

* Categorical Distribution

Models the number of runs awarded after an extra delivery.

---

### 5. Strike Rotation

Distribution:

* Bernoulli Distribution

Models the tendency of a batsman to rotate strike by taking singles.

---

## 🏏 Match Phases

The innings is divided into three phases.

| Phase        | Overs |
| ------------ | ----- |
| Powerplay    | 1–6   |
| Middle Overs | 7–15  |
| Death Overs  | 16–20 |

Separate probability distributions are estimated for each phase to better capture player behavior.

---

## ⚙️ Monte Carlo Simulation

For every simulated match:

1. Select batting and bowling teams.
2. Simulate every legal delivery.
3. Sample outcomes from fitted probability distributions.
4. Update match state.
5. Continue until:

   * 20 overs are completed, or
   * All wickets fall.
6. Repeat the simulation thousands of times.

Final statistics are computed from all simulations.

---

## 📈 Exploratory Data Analysis

The notebook performs several analyses, including:

* Runs per delivery distribution
* Phase-wise scoring analysis
* Run rate progression
* Wickets per innings
* Extras distribution
* Top batsmen
* Top bowlers

These analyses validate the quality of the training dataset before simulation.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Cricdata
* Jupyter Notebook

---

## 📂 Project Structure

```
├── IPL_MonteCarlo_Simulation.ipynb
├── ipl_train_multiyear.csv
├── ipl_2025_ball_by_ball.csv
├── README.md
└── requirements.txt
```

---

## 🚀 Installation

Clone the repository.

```bash
git clone https://github.com/yourusername/IPL-MonteCarlo-Simulation.git
```

Move into the project folder.

```bash
cd IPL-MonteCarlo-Simulation
```

Install dependencies.

```bash
pip install -r requirements.txt
```

or

```bash
pip install pandas numpy matplotlib seaborn cricdata
```

---

## ▶️ Running the Project

Launch Jupyter Notebook.

```bash
jupyter notebook
```

Open

```
IPL_MonteCarlo_Simulation.ipynb
```

Run all cells sequentially.

During execution, you can:

* Choose IPL teams
* Select batting order
* Select bowlers
* Simulate thousands of matches

---

## 📊 Model Features

* Multi-season training data
* Recency-weighted player statistics
* Bayesian smoothing
* Phase-wise player modelling
* Fast parameter caching
* Interactive team selection
* Ball-by-ball simulation
* Match validation using IPL 2025

---

## 📌 Future Improvements

* Player vs Player matchup probabilities
* Pitch condition modelling
* Weather effects
* Toss simulation
* Dynamic batting strategy
* Bowling rotation optimization
* Machine Learning based player form prediction
* Win Probability Graphs
* Interactive Streamlit Web App

---

## 📷 Sample Outputs

* Ball-by-ball score simulation
* Match scorecards
* Score distribution plots
* Win probability estimates
* Top performer statistics
* Phase-wise scoring charts

---

## 📖 Applications

This project can be used for:

* Cricket Analytics
* Sports Data Science
* Monte Carlo Simulation demonstrations
* Probability & Statistics coursework
* Machine Learning projects
* Predictive Sports Analytics

---

## 👨‍💻 Author

**Ayush Singh**

B.Tech, Ocean Engineering & Naval Architecture
Indian Institute of Technology (IIT) Kharagpur

---

## 📜 License

This project is intended for educational and research purposes.

Historical match data belongs to ESPNcricinfo and is accessed using the `cricdata` library.
