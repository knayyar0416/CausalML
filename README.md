# Uplift Modelling on Marketing Promotion Campaign
In this project, I developed an Uplift Model, using CausalML and Supervised Learning Classification algorithms, to maximize the impact of marketing promotion campaign by targeting the right customers.

## 🔍 Objective: 
I am using Customer Retention data to prescribe actions to a business for maximizing marketing campaign and reducing campaign cost.

  💡 [Uplift modeling](https://proceedings.mlr.press/v67/gutierrez17a/gutierrez17a.pdf) refers to the set of techniques used to model the incremental impact of an action or treatment on a customer outcome. Therefore, it is both a Causal Inference problem and a Machine Learning one. It is a causal inference problem because one needs to estimate the difference between two outcomes that are mutually exclusive for an individual. Uplift modeling is also a machine learning problem as one needs to train different models and select the one that yields the most reliable uplift prediction according to some performance metrics. This requires sensible cross-validation strategies along with potential feature engineering.

## 🌐 About Dataset:
  <sup>:exclamation:This is a fictional dataset for practicing purpose.</sup><sub></sub>

Marketing Promotion Campaign with a total of 64,000 customers data.
- recency: months since last purchase
- history: $value of the historical purchases
- used_discount: indicates if the customer used a discount before
- used_bogo: indicates if the customer used a buy one get one before
- zip_code: class of the zip code as Suburban/Urban/Rural
- is_referral: indicates if the customer was acquired from referral channel
- channel: channels that the customer using, Phone/Web/Multichannel
- offer: the offers sent to the customers, Discount/But One Get One/No Offer
- conversion: customer conversion (buy or not)

## ⚖️ Methodology: 
Causal Inference Model using CausalML library.

## 🛠️ Approach: 
I intend to calculate Average Treatment Effect (ATE) on different models and learners, along with their feature importances. For experimentation purposes, I will consider conversion as 'Target' feature, and 'offer' as Treatment feature.

## 🎉 Outcome Interpretation
#### S-Learner
1. XGBClassifier: 
  - ATE: 0.14
  - From the method= 'auto' output, we can see that **history** is the most important feature, and **zip_code_urban** is the least important feature.
  - From the method='permutation' output, we can see that **history** is the most importance feature, and **channel_multichannel** is the least important feature. 
  - **used_bogo** is the most important feature, followed by **history**, **is_referral**, and **recency**. 
2. LGBMClassifier:
  - ATE: 0.13
  - From the method= 'auto' output, we can see that **history** is the most important feature, and **zip_code_urban** is the least important feature.
  - From the method='permutation' output, we can see that **used_bogo** is the most importance feature, and **zip_code_urban** is the least important feature. This is different from the auto method results.
  - **used_bogo** is the most important feature, followed by **is_referral**, **history**, and **recency**. \

#### T-Learner
1. XGBClassifier:
  - ATE: 0.17
  - From methods= 'auto' and 'permutation' output, we can see that **history** is the most importance feature, and **channel_multichannel** is the least important feature. 
  - **history** is the most important feature, followed by **used_bogo**, **recency**, and **is_referral**. 
2. LGBMClassifier:
  - ATE: 0.14
  - From methods= 'auto' and 'permutation', we can see that **history** is the most important feature, and **channel_multichannel** is the least important feature.
  - **used_bogo** is the most important feature, followed by **history**, **is_referral**, and **recency**.
 
## 🎯 Key Takeaways
Exploring the causal relationship between the 'offer' treatment variable and 'conversion' target variable showed **three** important relationships which were common throughout most learners:
- For a majority of customers using 'web' channel, we observe a failed conversion (i.e., no buy decision).
- For customers who used a discount and used a buy one get one before, we observe a success on conversion (i.e., buy decision).
- For customers with more passed months since last purchase, there is a success on conversion (i.e., buy decision).

## 🔗 Supporting files
- 👩‍💻 [Python script for clustering models](Code/uplift-modeling.ipynb)
- 📁 [Entire dataset](Dataset/customer_retention_data.csv) and [Data Dictionary](Dataset/customer-retention-data-dictionary.xlsx)
