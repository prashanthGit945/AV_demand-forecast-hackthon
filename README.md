# AV-JanataHack-Demand-Forecasting

Approach to "Analytics Vidhya JanataHack Demand Forecasting"

<img width="712" alt="Rank_LB" src="https://datahack-prod.s3.ap-south-1.amazonaws.com/__sized__/contest_cover/cover_1_3vEBqwk-thumbnail-1200x1200.png">

Hosted at: https://datahack.analyticsvidhya.com/contest/janatahack-demand-forecasting/#ProblemStatement
           https://datahack.analyticsvidhya.com/contest/janatahack-demand-forecasting/#LeaderBoard

# Rank: 3 from 13,287 registered participant.

## Problem Statement:

One of the largest retail chains in the world wants to use their vast data source to build an efficient forecasting model to predict the sales for each SKU in its portfolio at its 76 different stores using historical sales data for the past 3 years on a week-on-week basis. Sales and promotional information is also available for each week - product and store wise. 

However, no other information regarding stores and products are available. Can you still forecast accurately the sales values for every such product/SKU-store combination for the next 12 weeks accurately? If yes, then dive right in!

## Data Description:

Variable	          Definition <br />
record_ID:          Unique ID for each week store sku combination <br />
week:     	        Starting Date of the week <br />
store_id:           Unique ID for each store (no numerical order to be assumed) <br />
sku_id:             Unique ID for each product (no numerical order to be assumed) <br />
total_price:	      Sales Price of the product  <br />
base_price: 	      Base price of the product <br />
is_featured_sku:	  Was part of the featured item of the week <br />
is_display_sku:	    Product was on display at a prominent place at the store <br />
units_sold(Target): Total Units sold for that week-store-sku combination <br />

## Approach:

1. Considered this as a regression problem with 'units_sold' as a target <br />
2. Generated following new features: <br />
  (a) checked the variance of  target and transformed to log(target) <br />
  (b) checked the correlation and  missing value treatment is done <br />
  (c) Categorical Encoded 'sku-id' & 'store-id' with labelEncoder() and get dummies for is_feat and is_display variables <br />
  (d) mostly feature engineering is done created new features using given variables like avg_price,diff_price..etc  <br />
  (e) Price difference percent between base price & total-price <br />
3. Trained the data on XGB & LGBM Regressor <br />
4. cross-vaildation is done for better results  <br />
5. Tuned the above models<br />
