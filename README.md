# Marketing Promotion Campaign Uplift Modelling
In this project, I developed an Uplift Model, using CausalML and Supervised Learning Classification algorithms, to maximize the impact of marketing promotion campaign by targeting right customers.

## Objective: 
I am using Customer Retention data prescribe actions to business regarding customers' conversion rate. This is a case of Uplift Modelling.

  💡 [Uplift modeling](https://proceedings.mlr.press/v67/gutierrez17a/gutierrez17a.pdf) refers to the set of techniques used to model the incremental impact of an action or treatment on a customer outcome. Therefore, it is both a Causal Inference problem and a Machine Learning one. It is a causal inference problem because one needs to estimate the di↵erence between two outcomes that are mutually exclusive for an individual. Uplift modeling is also a machine learning problem as one needs to train di↵erent models and select the one that yields the most reliable uplift prediction according to some per- formance metrics. This requires sensible cross-validation strategies along with potential feature engineering.

## 🌐 About Dataset:
<sup>:exclamation:This dataset is a fictional dataset for practicing purpose.</sup><sub></sub>
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

## Methodology: 
Causal Inference Model using CausalML library.

## Approach: 
I intend to calculate Average Treatment Effect (ATE) on different models and learners, along with their feature importances. For experimentation purposes, I will consider conversion as 'Target' feature, and 'offer' as Treatment feature.
