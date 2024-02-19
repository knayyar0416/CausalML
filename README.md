# Marketing Promotion Campaign Uplift Modelling
Uplift Modelling to maximize the impact of marketing promotion campaign by targeting right customers

**Objective**: I am using Customer Retention data prescribe actions to business regarding customers' conversion rate. This is a case of Uplift Modelling. \

**Methodology**: Causal Inference Model using CausalML library. \

**Dataset**: Marketing Promotion Campaign with a total of 64,000 customers data.
- recency: months since last purchase
- history: $value of the historical purchases
- used_discount: indicates if the customer used a discount before
- used_bogo: indicates if the customer used a buy one get one before
- zip_code: class of the zip code as Suburban/Urban/Rural
- is_referral: indicates if the customer was acquired from referral channel
- channel: channels that the customer using, Phone/Web/Multichannel
- offer: the offers sent to the customers, Discount/But One Get One/No Offer
- conversion: customer conversion(buy or not)

**Approach**: I intend to calculate Average Treatment Effect (ATE) on different models and learners, along with their feature importances. For experimentation purposes, I will consider conversion as 'Target' feature, and 'offer' as Treatment feature.
