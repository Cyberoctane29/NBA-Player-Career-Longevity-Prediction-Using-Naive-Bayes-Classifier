<img src="https://i.ibb.co/spn0rD1h/nba-bg-1.png" alt="nba" align="centre" width="45px" style="margin-right: 15px;">

# NBA Player Career Longevity Prediction: Using Naive Bayes Classifier

This project analyzes how rookie season performance metrics influence the probability of an NBA player sustaining a career of five years or longer. Using **Gaussian Naive Bayes classification**, I aim to model this relationship to inform data-driven decision-making in player scouting and team management. The project uses Python libraries including **pandas**, **seaborn**, **scikit-learn**, **matplotlib**, and **pickle** for data preprocessing, visualization, modeling, and performance evaluation.

---

## **Project Overview**

The **NBA Player Career Longevity Prediction** project aims to:

* **Identify Predictive Features**: Determine which rookie season statistics best forecast long-term career outcomes
* **Build Classification Model**: Implement and evaluate a Gaussian Naive Bayes classifier for career longevity prediction
* **Validate Model Assumptions**: Assess conditional independence, normality, and class balance for model suitability
* **Support Roster Decisions**: Provide actionable insights for scouting, player development, and team-building strategy

---

## **Dataset Structure**

The dataset contains rookie season statistics from **1,340 NBA players**, capturing their on-court performance across various metrics. Key features include:

**Career Longevity Target:**

* `target_5yrs`: Binary outcome variable indicating career duration (1 = career ≥5 years, 0 = otherwise)

**Performance Metrics:**

* `gp`: Games played in the rookie season (integer)
* `min`: Average minutes played per game (continuous)
* `pts`: Average points per game (continuous)
* `fg`: Field goal percentage per game (continuous)
* `3p`: Three-point field goal percentage per game (continuous)
* `ast`: Average assists per game (continuous)
* `stl`: Average steals per game (continuous)
* `blk`: Average blocks per game (continuous)
* `reb`: Average rebounds per game (continuous)
* `tov`: Average turnovers per game (continuous)
* `ft`: Free throw percentage per game (continuous)

**Engineered Features:**

* `total_points`: Total points scored in the rookie season (derived by multiplying `pts` and `gp`)
* `efficiency`: Points per minute played (derived by dividing `pts` by `min`)

This dataset forms the basis for exploring career longevity patterns and developing predictive models to identify players likely to sustain long-term NBA careers — providing valuable insights for scouting and roster management.

---

## **Data Processing and Analysis Steps**

* **Data Cleaning**:

  * Verified no missing values in all 1,340 observations
  * Removed redundant or less informative features

* **Exploratory Data Analysis (EDA)**:

  * Assessed class balance (62% of players had careers ≥5 years)
  * Visualized feature distributions and correlation patterns within classes

* **Feature Engineering**:

  * Created `total_points` (games played × points per game)
  * Developed `efficiency` as a productivity-per-minute metric

* **Modeling Approach**:

  * Fit a **Gaussian Naive Bayes classifier** using scikit-learn
  * Split data into 75% training and 25% testing sets
  * Evaluated model using accuracy, precision, recall, and F1 score

* **Assumption Validation**:

  * Checked for conditional independence and normality within classes
  * Noted moderate correlations and slight normality deviations, but acceptable for model use

---

## **Key Insights**

### **Predictive Features**

* The engineered `efficiency` metric proved highly informative
* Shooting percentages (`fg`, `3p`) contributed meaningfully to predictions
* Traditional stats like points and assists retained value but were complemented by derived features

### **Model Performance**

* Achieved **84.1% precision** in identifying long-career players
* Delivered balanced **68.96% accuracy**
* Recall of **58.6%** indicates room to improve detection of all long-career cases

---

## **Project Highlights**

* Developed **novel efficiency metrics** to enhance predictive power
* Applied **Gaussian Naive Bayes** with thorough assumption checks
* Achieved **high precision**, valuable for strategic roster decisions
* Provided **clear, actionable recommendations** for basketball operations teams
* Established a framework for future model improvements

---

## **Future Work**

* **Enhance Feature Set**: Incorporate advanced stats like Player Efficiency Rating and usage rates
* **Address Class Imbalance**: Explore resampling or reweighting techniques
* **Test Alternative Models**: Compare performance of Random Forest, Logistic Regression, and Gradient Boosting
* **Build Decision-Support Tools**: Develop interactive dashboards or prediction apps for team use
* **Longitudinal Validation**: Apply the model to recent draft classes for ongoing refinement

This project demonstrates how a structured, data-driven approach can produce **practical, interpretable insights** in professional sports analytics, improving talent evaluation and roster construction through predictive modeling.
