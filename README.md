# Ipl_Win_Probability
This project predicts the real-time win probability of the chasing team in an IPL match using historical match data (2009–2019). It leverages machine learning to estimate the chances of a team winning based on match context — such as runs required, balls remaining, wickets in hand, and current run rate.


**Objective**
To build a reliable machine learning model that can predict the probability of a team winning while chasing, using match situation data, with a focus on producing plausible and interpretable probabilities rather than just maximum accuracy.


**Dataset**
-Source: Kaggle IPL Dataset:
-matches.csv: Match-level data
-deliveries.csv: Ball-by-ball data
**Filtered**: Removed non-active teams and focused only on matches with clear outcomes (no ties, D/L method, etc.).


**Feature Engineering**
Generated the final dataset with the following key features for the second innings:
-Current Run Rate (CRR)
-Required Run Rate (RRR)
-Runs Left
-Balls Left
-Wickets Remaining
-Match Venue
-Batting and Bowling Teams


**Preprocessing**
Used:
-One-Hot Encoding for categorical features
-ColumnTransformer to combine preprocessing steps
-Pipeline to streamline transformation and model training


**Models Used**
-**Logistic Regression:**
Chosen as the final model for its interpretable and plausible probability estimates. For example, in a scenario like:
-MI needs 82 from 8 overs at Wankhede with 7 wickets in hand
Logistic Regression gives ~70% win probability for MI — matching expert intuition.

-**Random Forest:**
Higher Accuracy but discarded due to overconfident predictions (e.g., 95% for MI), which lacked realistic variability.


**Evaluation**
-Compared models using test set accuracy and domain knowledge
-Prioritized probability realism over just classification accuracy


**Tech Stack**
-Python (Pandas, NumPy, Scikit-learn, Matplotlib)
-Jupyter Notebook


**Project Structure**
![image](https://github.com/user-attachments/assets/e47e0868-3455-450a-8a59-57150e0001a6)


**Future Improvements**
-Integrate live match data via API for real-time predictions
-Build a web dashboard to visualize win probabilities dynamically
-Incorporate more features like player form, pitch report, toss result, etc.
