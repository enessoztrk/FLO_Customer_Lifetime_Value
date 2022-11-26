# FLO CLTV Prediction Interview Case

## Business Problem
FLO wants to set a roadmap for sales and marketing activities.
In order for the company to make a medium-long-term plan, it is necessary to estimate the potential value that existing customers will provide to the company in the future.

## Dataset Story
The dataset is based on the past shopping behavior of customers who made their last purchases from OmniChannel (both online and offline) in 2020 - 2021 consists of the information obtained.

- master_id: Unique client number
- order_channel : Which channel of the shopping platform is used (Android, ios, Desktop, Mobile, Offline)
- last_order_channel : The channel where the last purchase was made
- first_order_date : The date of the customer's first purchase
- last_order_date : The date of the last purchase made by the customer
- last_order_date_online : The date of the last purchase made by the customer on the online platform
- last_order_date_offline : The date of the last purchase made by the customer on the offline platform
- order_num_total_ever_online : The total number of purchases made by the customer on the online platform
- order_num_total_ever_offline : Total number of purchases made by the customer offline
- customer_value_total_ever_offline : The total price paid by the customer for offline purchases
- customer_value_total_ever_online : The total price paid by the customer for their online shopping
- interested_in_categories_12 : List of categories the customer has purchased from in the last 12 months



## TASKS

TASK 1: 
Preparing the Data
- Read the data flo_data_20K.csv. Make a copy of the dataframe.
- Define the outlier_thresholds and replace_with_thresholds functions needed to suppress outliers.
- Note: When calculating cltv, frequency values must be integers. Therefore, round the lower and upper limits with round().
- Set the variables "order_num_total_ever_online","order_num_total_ever_offline","customer_value_total_ever_offline","customer_value_total_ever_online"  suppress outliers if any.
- Omnichannel means that customers shop from both online and offline platforms. Total for each customer create new variables for number of purchases and spend.
- Examine the variable types. Change the type of variables that express date to date.

- TASK 2: 
- Creating CLTV Data Structure
- 1. Take 2 days after the date of the last purchase in the data set as the date of analysis.
- Create a new cltv dataframe with the values 2.customer_id, recency_cltv_weekly, T_weekly, frequency and monetary_cltv_avg.
- Monetary value will be expressed as average value per purchase, recency and tenure values will be expressed in weekly terms.


- TASK 3: BG/NBD, Establishing Gamma-Gamma Models, Calculating CLTV
           # 1. Fit the BG/NBD model.
                # a. Estimate expected purchases from customers in 3 months and add exp_sales_3_month to cltv dataframe.
                # b. Estimate expected purchases from customers in 6 months and add exp_sales_6_month to cltv dataframe.
           # 2. Fit the Gamma-Gamma model. Estimate the average value of the customers and add it to the cltv dataframe as exp_average_value.
           # 3. Calculate 6 months CLTV and add it to the dataframe with the name cltv.
                # b. Observe the 20 people with the highest Cltv value.

- TASK 4: Creating Segments by CLTV
           # 1. Divide all your 6-month customers into 4 groups (segments) and add the group names to the dataset. Add it to the dataframe with the name cltv_segment.
           # 2. Make short 6-month action suggestions to the management for 2 groups you will choose from among 4 groups.
