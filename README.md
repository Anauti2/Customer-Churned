# Customer-Churned
Customer Churned model time based 
“My second project was a Customer Churn Prediction system. 
The goal was to predict whether a customer would leave a telecom company 
based on demographic information, tenure, contract type, monthly charges, 
total charges, and other customer attributes.”

“I performed data preprocessing, exploratory analysis, categorical 
encoding, train-test splitting, and then trained a Logistic Regression classification model.”

Challenge 1 — Missing values

“One challenge I faced was that the TotalCharges column contained blank values. 
When I tried to train Logistic Regression, I got an error because the model doesn't accept NaN values.”

Then explain your solution:

df["TotalCharges"] = pd.to_numeric(
    df["TotalCharges"],
    errors="coerce"
)

df = df.dropna()

Then:

“After converting the column to numeric, I removed the missing rows and 
verified that there were zero NaN values before training.”

Cahllenge 2 - Categorical data

“The dataset contained many categorical columns such as contract type, 
payment method, and internet service. Machine-learning models require 
numerical inputs, so I used one-hot encoding.”

df = pd.get_dummies(
    df,
    drop_first=True
)

Challenge 3 — Choosing evaluation metrics

“I didn't want to evaluate the model using accuracy alone because churn prediction is a 
classification problem where identifying customers who actually churn is important. 
So I also evaluated precision, recall, and F1-score using a classification 
report and confusion matrix.”

"Recall was especially important because a false negative means the model 
predicts that a customer will stay when they actually leave.”

Challenge 4 — Model errors during development

“During development I encountered issues such as missing columns, 
incorrect argument ordering, and NaN values. 
I solved these by checking the DataFrame columns, 
validating each preprocessing step, and checking for 
missing values before passing the data to the model.”

