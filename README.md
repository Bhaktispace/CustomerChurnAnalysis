# Customer Churn Analysis Project

## Business Problem
A leading e-commerce company is facing customer churn, which negatively impacts revenue and long-term customer value. To address this, an exploratory data analysis (EDA) was conducted to identify patterns in customer behavior, demographics, and purchasing habits that influence churn.

By analyzing factors such as tenure, login preferences, order frequency, payment methods, and customer satisfaction, the company seeks to uncover key drivers of churn. The insights from this analysis will help develop targeted retention strategies, such as personalized promotions, improved customer experience, and loyalty programs, to reduce churn and enhance customer engagement.

## Data Overview
This dataset contains information about customer demographics, engagement, and transaction history. It includes key attributes that help analyze customer behavior and identify churn patterns.

A. Customer Identification and Churn Status
 * Customer ID - Unique Customer ID
 * Churn - Binary flag indicating whether the customer has churned (1) or remains active (0)

B. Customer Demographics and Preferences
 *  Tenure - Length of time the customer has been with the company
 *  CityTier – Classification of the customer’s location (e.g., Tier 1, Tier 2, Tier 3)
 *  Gender – Gender of the customer
 *  MaritalStatus – Customer’s marital status

C. Customer Engagement and Behavior
 *  PreferredLoginDevice – Device most commonly used by the customer to access the platform (mobile or web)
 *  HourSpendOnApp – Average time the customer spends on the app or website
 *  NumberOfDeviceRegistered – Number of devices linked to the customer’s account
 *  NumberOfAddress – Number of addresses saved in the customer’s profile

D. Transactional and Purchase Behavior
 *  PreferredPaymentMode – Most frequently used payment method (credit card, debit card, cash on delivery, etc.)
 *  PreferedOrderCat – Most frequently purchased category of products in the last month
 *  OrderAmountHikeFromlastYear – Percentage increase in the customer's order value compared to the previous year
 *  OrderCount – Total number of orders placed in the last month
 *  DaySinceLastOrder – Number of days since the customer’s most recent order
 *  CouponUsed – Total number of coupons redeemed by the customer in the last month

E. Customer Satisfaction & Experience
 *  SatisfactionScore – Customer's rating of their satisfaction with the service
 *  WarehouseToHome – Distance between the warehouse and the customer’s home, which may impact delivery time and satisfaction

## Exploratory Data Analysis Findings
A. Churn Rate Analysis: 
 *  The overall churn percentage in the dataset is 16.84%
   
    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/13504e0ba00be42200156dd220d44c8aa4f78dce/graphs/Churn%20distribution.png)


 B. Customer Demographics and Preferences
 *  Breakdown of churn by CityTier:
    City Tier 1 has the most number of customers. It is odd that there are too few customers in Tier 2 but more customers in Tier 3. But as per the current data the highest churn rate is in tier 3. Customer Churn decreases as the Tier increases.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/846aca7154f0583c6a4483c04c5c4b296b72a382/graphs/city.png)

 *  Breakdown of churn by Gender:
    There are significantly more male customers than female customers. While males have a higher overall number of customers, they also have a higher absolute number of churned customers. The percentage of churned customers is slightly higher among males compared to females.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/846aca7154f0583c6a4483c04c5c4b296b72a382/graphs/gender.png)

 *  Breakdown of Churn by Marital Status:
    The Married category has the highest customer count, significantly more than Single or Divorced. The Single category has a moderate number of churned customers, but a higher proportion of churned customers relative to the non-churned customers compared to Married. 

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/846aca7154f0583c6a4483c04c5c4b296b72a382/graphs/marital%20status.png)

 *  Relationship between Tenure and Churn:
    For customers who did not churn, is skewed right indicating a concentration of customers with shorter tenure. For customers who churned, there is a higher density at shorter tenure. Customers with shorter tenures are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/846aca7154f0583c6a4483c04c5c4b296b72a382/graphs/tenure.png)

C. Customer Engagement Patterns
 *  Distribution of PreferredLoginDevice (mobile vs. web) and its correlation with churn:
    Significantly higher number of customers use Mobile vs Web. The churn rate is higher for Web than for Mobile.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/ffc46955b28dd86b08e0488441fba6d1684dda68/graphs/logindevice.png)
    
    Preferred login device is not a significant predictor or cause of customer churn in the dataset.

 *  Analysis of HourSpendOnApp to see if low app engagement correlates with higher churn:
    The highest count of non-churned customers is at 3 hours spent on the app. The number of churned customers increases as the hours spent on the app increase, peaking at 3 hours. The counts are very low for both churned and non-churned customers at the extreme ends (0.0, 1.0, and 5.0 hours). The churn rate is higher at 3 and 4 hours compared to the other categories.
    
    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/ffc46955b28dd86b08e0488441fba6d1684dda68/graphs/hoursspend.png)
    
    Hours spent on App is not a significant predictor or cause of customer churn in the dataset.

 *  Impact of NumberOfDeviceRegistered on churn—do customers with multiple devices tend to stay longer:
    The largest group of customers has 4 devices registered. While 4 devices have the highest count, they also show a significant number of churned customers. The customers with either 1 or 6 devices registered shows a low churn rate.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/ffc46955b28dd86b08e0488441fba6d1684dda68/graphs/device%20registered.png)

D. Purchase & Transaction Behavior
 *  Trends in OrderCount and OrderAmountHikeFromlastYear to see if decreasing purchases predict churn:
    Churn = 0: Skewed right, indicating a concentration of customers with lower order counts. Churn = 1: Similar to Churn = 0, but with a slightly higher density at higher order counts. Customers with higher order counts are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/ffc46955b28dd86b08e0488441fba6d1684dda68/graphs/order%20count.png)

     OrderAmountHikeFromlastYear: should not be used for analysis because the dataset does not give any count of orders from last year so using just the percentage value does not return any meaningful analysis. So, rather it should be dropped from the analysis.

 *  Distribution of PreferedOrderCat among churned vs. retained customers:
    Laptop and Accessory is the most popular preferred order category, with a significant lead over others. Despite having the highest number of customers, it shows a relatively low number of customers churned. Mobile Phones and Fashion are the other category which is popular between the custimers. Grocery has a relatively lower churn rate.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/bd004ca967afdfb6be49640350301adff4db9449/graphs/ordercat.png)

 *  Effect of PreferredPaymentMode on churn—are certain payment methods associated with lower retention:
    Cash on Delivery (COD) has the highest churn rate (24.9%) among all payment methods. E Wallets (22.8%) and UPI (17.4%) also have relatively high churn rates.Credit Card (14.2%) and Debir Card (15.4%) has the lowest churn rates, indicating more loyal customers.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/bd004ca967afdfb6be49640350301adff4db9449/graphs/preferred%20Payment%20Mode.png)

 *  Average DaySinceLastOrder for churned vs. active customers:
    Churn = 0: Bimodal, indicating two groups of customers with different recency patterns. Churn = 1: Similar to Churn = 0, but with a slightly higher density at longer days since the last order. Customers with longer periods since their last order are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/bd004ca967afdfb6be49640350301adff4db9449/graphs/dayssincelast%20order.png)

E. Discount & Loyalty Impact
 *  Number of CouponUsed and its relationship with churn—are loyal coupon users more likely to stay:
    Churn=0, Skewed right, indicatinga concentration of customers who used fewer coupons. Churn=1, similar to Churn=0, but with a slightly higher density at higher couponusage. Customers who used more coupons are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/8834ef0db772d5c25cbca931bc5a0145ded71ac4/graphs/coupon%20used.png)

 *  Effect of CashbackAmount on customer retention—do higher cashback incentives reduce churn: 
    Churn = 0: Skewed right, indicating a concentration of customers with lower cashback amounts. Churn = 1: Similar to Churn = 0, but with a slightly higher density at higher cashback amounts. Customers with higher cashback amounts are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/8834ef0db772d5c25cbca931bc5a0145ded71ac4/graphs/cashback%20amount.png)

E. Customer Satisfaction & Experience
 *  Distribution of SatisfactionScore among churned vs. retained customers:
    The highest number of customers have a satisfaction score of 3. While score 3 has the highest customer count, it also exhibits the highest number of churned customers. Generally, as the satisfaction score increases, the number of churned customers decreases there appears to be an inverse relationship. Despite having lower overall customer counts, scores 1 and 2 show relatively fewer churned customers compared to scores 3, 4, and 5. Even with a score of 5, which is the highest satisfaction score, there is still a significant number of people who churned.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/8834ef0db772d5c25cbca931bc5a0145ded71ac4/graphs/satisfaction%20score.png)

 *  Influence of WarehouseToHome distance on churn—does longer delivery time lead to customer drop-off:
    or customers who did not churn, skewed right indicating a concentration of customers closer to the warehouse. For customers who did churn, there is a slightly higher density at longer distance. Customers living farther from the warehouse are more likely to churn.

    ![image alt](https://github.com/Bhaktispace/CustomerChurnAnalysis/blob/8834ef0db772d5c25cbca931bc5a0145ded71ac4/graphs/warehouse%20to%20home.png)    

## Key Insights & Potential Ideas
A. Churn Trends & Demographics
 🔹 City Tier 
    * Analysis and Insight
        1. Socio-economic factors: City tier represent different socio-economic groups with varying level of disposable income, spending habits and access to technology. 
        2. Infrastructure: Lower tier city might have limited internet connectivity impacting customer experience and leading to higher churn in higher Tiers.
        3. Customer Needs: Customer needs and expectations might be different between the Tier customers. 

    * Potential Ideas:
        1. Develop localized Marketing campaign for each Tier.
        2. Analyze customer demographic and behavior for each Tier.
 
 🔹 Gender
    * Analysis and Insights:
        1. Gender Impact: Gender appears to be a factor influencing customer churn.
        2. Potential for Targeted Strategies: The difference in churn between genders suggests the need for tailored strategies to address the specific needs of each group.

    * Potential Ideas:
        1. Analyze customer feedback, transaction history, or other relevant data to identify potential causes (e.g., product preferences, service issues, communication styles) to understand why males have a higher churn rate.
        2. Segment Customers based on gender to analyze their characteristics and behavior.

 🔹 Marital Status
    * Analysis and Insights:
        1. The high churn among married customers suggests potential issues specific to this demographic. It could be related to family-related factors, time constraints, or specific needs that are not being met. It could also be that since there are just more married people, there are also more married people who churn.
        2. The higher proportion of churn among single customers indicates potential dissatisfaction or unmet needs. It could be related to lifestyle factors, individual preferences, or service expectations.
        3. The low churn among divorced customers suggests a higher level of satisfaction or loyalty. It could be related to specific needs being met, or a higher value placed on the service.

    * Potential Ideas: 
        1. Conduct surveys, interviews, or focus groups with married customers to understand their needs, pain points, and expectations.
        2. Analyze the behavior and preferences of single customers, and design personalized offers, communication, or support.
        3. Analyze the usage patterns, feedback, and demographics of divorced customers to identify key drivers of loyalty.
        4. Use clustering algorithms or other segmentation techniques to identify distinct customer segments with unique needs and preferences.
 
 🔹 Tenure
    * Analysis and Insights:
        1. High Churn at Low Tenure: there might be issues during the initial onboarding or early stages of customer experience.
        2. Low Churn at Higher Tenure: the density of churned customers decreases significantly as tenure increases, implying that longer-term customers are less likely to churn.
        3. Early Customer Experience: The extremely high peak of churn at the very beginning of tenure is a strong indicator that something is happening at the start of the customer journey that is causing customers to leave.

    * Potential Ideas:
        1. Analyze the onboarding process, including communication, initial product usage, and customer support during the first few months.
        2. Develop a strategy to improve customer engagement and reduce churn during the initial tenure period.
        3. Segment customers based on their tenure and develop targeted retention strategies for each segment.
        4. Understand the relationship between tenure and customer Lifetime Value, CLTV and develop strategies to increase customer lifetime value.

B. Customer Engagement & Platform Usage
🔹 Preferred Login Device
    * Analysis and Insights
        1. Mobile Focus: Customers use the mobile platform the most. Prioritize the mobile app development and user interface.
        2. Platform Optimization: The web platform might have usability issues or lack of features which are present in the mobile app, leading to higher customer churn.
        3. Targeted Retention: Conduct surveys with the web users to find out the pain areas and develop specific retention strategies for web users addressing their pain points.

    * Potential Ideas:
        1. Conduct audit of the web platform.
        2. Feature analysis differences in the mobile app and web.
        3. Create a trgeted marketing campaign for web users.
        
🔹 Hours Spend on App 
    * Analysis and Insights:
        1. App Engagement and Churn: The graph suggests a relationship between app engagement (measured by hours spent) and churn. However, it's not a simple linear relationship.
        2. Potential Sweet Spot: There appears to be a "sweet spot" of around 3 hours where the highest number of customers are engaged (non-churned).
        3. High Churn at Mid-Range: The relatively high proportion of churn at 3 and 4 hours indicates a potential issue at this engagement level.
        4. Low Engagement Impact: Very low engagement (0 and 1 hours) also leads to low numbers of customers, suggesting a lack of adoption.
        5. High Engagement Impact: Very high engagement (5 hours) leads to a low number of customers, suggesting that go back to the data team and understand is this hours a weekly number or monthly or daily. assuming if it is monthly number maybe take data for the other months and see if the pattern is similasr. Or maybe there is entry problem in the data.

    * Potential Ideas:
        1. Analyze app usage patterns, customer feedback, or other relevant data to identify potential causes (e.g., specific features, usability issues, content relevance).
        2. Identify distinct customer segments and analyze their characteristics and behavior.

🔹 Number of Devices Registered
    * Analysis and Insight:
        1. Potential Feature Gap: There could be features and functionalities that are lacking for users with multiple devices.
        2. Complexity: Customers with multiple devices might be experieencing issues realted to their accounts with their devices like login issues, difficulty keeping data consistent across devices.
    * Potential Ideas:
        1. Identify the pain points and challenges faced by users with multiple registered devices.
        2. Identify and propose new features that simplify multi-device management.

C. Purchase Behavior & Retention
🔹 Preferred Payment Mode
    * Analysis and Insights:
        1. Debit Card has the highest number of customers both churned and not churned.
        2. The Churn rate varies significantely varies significantly across payment modes.
        3. Customers using E Wallet are more likely to Churn.

    * Potential Ideas:
        1. Offer discounts for prepaid orders to encourage a shift towards digital payment.
        2. Surveys can be run for customers for COD methods and E Wallets to identify potential problems.
        3. Provide reward points to increase repeat purchases.
        4. Conduct deeper analysis into why e-wallet users have a high churn rate.
        5. Segment customers based on their preferred payment mode and churn status.

D. Discounts & Loyalty Programs
🔹 Coupon Used
    * Analysis and Insights:
        1. High Density at Low Coupon Usage: Both churned and non-churned customers show a high density at low coupon usage (around 0-2). This suggests that a large proportion of customers, regardless of churn status, use very few coupons.
        2. Similar Distributions: coupon usage might not significantly differentiate customers who churn from those who don't.

    * Potential Ideas:
        1. Investigate the relationship between coupon usage and churn, particularly the slightly higher churn rate among customers who use no coupons.
        2. Develop a personalized coupon strategy to improve customer engagement and reduce churn.
    3. Analyze the effectiveness of different coupon types and promotions in retaining customers.

🔹 Cashback
    * Analysis and Insights:
        1. High Density at Moderate Cashback Amounts: Both churned and non-churned customers show a high density at moderate cashback amounts (around 100-200). This suggests that a large proportion of customers, regardless of churn status, earn cashback within this range.
        2. Potential for Cashback as a Feature: While the distributions are similar, the slight shift suggests that 'cashbackamount' could be a useful feature in conjunction with other features for churn prediction.
        3. Tail for Higher Cashback Amounts: Both distributions have a tail extending towards higher cashback amounts, indicating that some customers earn significantly more cashback.
        4. Potential for Cashback Program Evaluation: The differences in the distributions could point towards a need to evaluate the effectiveness of the cashback program in retaining customers

    * Potential Ideas:
        1. Investigate the relationship between cashback amounts and churn, particularly the slightly higher cashback amounts earned by customers who churn.
        2. Develop a personalized cashback strategy to improve customer engagement and reduce churn.
        3.  Improve the accuracy of churn prediction models by incorporating cashback amount as a feature.

E. Customer Satisfaction & Delivery Experience
🔹 Satisfaction Score
    * Analyis and Insight:
        1. Score 3 as a Critical: A score 3 might represent a neutral or indifferent sentiment. Customers at this level are potentially vulnerable to churn as they are neither highly satisfied nor dissatisfied. There might be specific issues or pain points that lead customers to rate their experience as a 3.
        2. Potential for Improvement at Higher Scores: While churn decreases with higher scores, it's still present. Even highly satisfied customers might churn due to external factors or specific issues that were not captured by the satisfaction score. The fact that there is still a significant number of churn at a score of 5 indicates that satisfaction score is not the only important metric.
        3. Surprising Low Churn at Low Scores: The relatively low churn at scores 1 and 2 could indicate that dissatisfied customers might be vocal about their issues, leading to resolution or targeted interventions. Also these customers may have already expressed their negative opinions and left, so the remaining customers are those who are still willing to use the product/service, even with a low score.
        4. Satisfaction Score Limitations: A single satisfaction score might not capture the complexity of customer experience. There might be other factors influencing churn that are not reflected in the score.

    * Potential Ideas:
        1. Investigate the specific issues and pain points that lead customers to rate their experience as a 3.
        2. Identify other factors that contribute to churn, even among highly satisfied customers.
        3. Develop targeted interventions to improve customer retention at score 3.
        4. Enhance the feedback loop to capture more detailed and actionable insights from customers.

🔹 Warehouse to Home
    * Analysis and Insights:
        1. High Churn at Low Tenure: there might be issues during the initial onboarding or early stages of customer experience.
        2. Low Churn at Higher Tenure: the density of churned customers decreases significantly as tenure increases, implying that longer-term customers are less likely to churn.
        3. Early Customer Experience: The extremely high peak of churn at the very beginning of tenure is a strong indicator that something is happening at the start of the customer journey that is causing customers to leave.

    * Potential Ideas:
        1. Analyze the onboarding process, including communication, initial product usage, and customer support during the first few months.
        2. Develop a strategy to improve customer engagement and reduce churn during the initial tenure period.
        3. Segment customers based on their tenure and develop targeted retention strategies for each segment.
        4. Understand the relationship between tenure and customer Lifetime Value, CLTV and develop strategies to increase customer lifetime value.

## Future Project Ideas for Customer Churn Prevention
A. Predictive Churn Modeling :
Develop a machine learning model to predict churn probability based on historical customer data. 
Use classification algorithms (e.g., logistic regression, decision trees, random forest) to build a predictive model.

B. Customer Segmentation for Targeted Marketing: Perform clustering (e.g., K-Means, DBSCAN) to segment customers into high-risk and low-risk groups. Create personalized marketing campaigns for each segment.

C. Recommendation System for Retention: Build a recommendation engine suggesting relevant products to improve customer engagement. Use collaborative filtering or content-based filtering to provide personalized recommendations.

D. Sentiment Analysis on Customer Reviews & Feedback: Analyze customer reviews to identify dissatisfaction trends. Use NLP techniques to extract sentiment from customer complaints.
