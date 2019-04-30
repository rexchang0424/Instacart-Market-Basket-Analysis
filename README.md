# Instacart Market Basket Analysis
---
## **Problem Statement:**

Learning consumer behavior is one of the key component to increase the sales. However, how do predict what will the consumer buy next ? 

My objective is to predict the consumer behavior and what order (item) they will put on their next purchase. In this case, I can create a recommender system for each of the consumer based on their past purchsing history. This will not only boost the consumer experience but also the overall sales goal. 

for more information regarding this kaggle chanllenge [click here](https://www.kaggle.com/c/instacart-market-basket-analysis). 

## Dataset 

I have total of six dataset to work with. Each of the dataset represent an unqiue information for the consumer. 

### 1. orders_df 

Initial Insights: `orders_df` consist of the information for the orders. What did the user order, on what day, what time is the order, etc...

### 2. prodcuts_df 

Initial Insights: `products_df` obtained all the prodcuts that Instacart sells with the location ID of each unique product. Each product has their own unique Id as well. `products_df` can be merged with `order_products_prior`'s product_id

### 3. departments_df 

Initial Insights: `departments_df` contain the information that is in products. This is a good data to merge into `products_df` based on the unique department_id column

### 4. aisles_df

Initial Insights: Similar to `departments_df`, `aisles_df` can be merge into the `prodcuts_df` to better visualize the data

### 5. order_produ ts_prior

Initial Insights: `order_products_prior_df` consist a unique order_id. The order_id is corsponding with `orders_df`'s order_id. product_id cosponds with `products_df`'s id. Therefore, `order_products_prior_df` only have two new information. add_to_cart_order and redordered. 

### 6. order_products_train

Initial Insights: Similar to `orders_prior_df` `order_products_train` have the same information. To find out the difference between train and prior, we will look into it moments later.


## Final Result

**Baseline Model:**
- This is our baseline model. The 1's represent there are 59.8861% of which means reordered (positive class) and 40.1139% of didn't reordered (negative class) in our dataset. This is good, because this tells us that our model is pretty evenly distributed.  Our base goal is to fit our data into several models and get the accuracy score that is higher than **59.8861%**. In that case, we will know we are doing better than the baseline.

After performing an indept EDA on all of the dataset, I've impletment two different machine learning model. First is the Logistic regression,
- I've used Grid Search to perform different parameter of C, and in result 1.0 gave the best result. 
- The parameter C is the the inverse of regularization strength in Logistic Regression. 
- The reason why I choose this model as my final, our expectation for our model is high accuracy. In this case the Logistic Regression's result gave us an accuracy of **64.189%**, which is higher than Random Forest Classifier's accuracy. 
- Not only the accuracy is higher than Random Forest Classifier, but also performed better than our Baseline model.

followed by the Random Forest Classifier

- I've used Grid Search to perform different parameter of Min_sample_split, and max_depth in result it gave the best result. of max_depth of None and min_samples_split of 1.0, Due to the compute time, I can only minimize to 2 parameters. With more time and compute power, I am sure I can find a higher accuracy.
- The reason why I did not choose this model as my final, because to be able to interpret if a model is good the accuracy if a key, our expectation for our model is high accuracy. In this case the Random Forest Classifier's result gave us an accuracy of **59.825%**, which is lower than Logistic Regression's accuracy.

## Futher Steps and Future planning

Although my model did slightly better than the baseline model, this doesn't mean this is a good result. There are still a lot of EDA I can improve on, also, due to the computing power, the use of my parameter are limited. Therefore, I can not use the full benefit of random forest classifier although I have used pipeline. This is still an on-going project. So once I discover a better EDA result I will update this Github repo. 
