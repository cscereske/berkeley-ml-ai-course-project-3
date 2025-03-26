# Used Car Price Analysis
**By Chris Cereske**

# Objective
The primary goal of this project was to develop a predictive model for used car prices, providing meaningful insights into the key factors that drive valuation.

# Analysis
#### Data Cleaning:
Removed missing or inconsistent entries to ensure data integrity. While we were able to visually identify several categorical features that needed cleaning, we tried to use algorithmic methods to determine how to clean our data.
#### Feature Engineering:
We tranformed categorical columns using three encoding techinique:
    - ordinal encoding
    - one hot encoding
    - target encoding
Additionally, we added new "popularity" features to certain categories based on the frequency of those categories in our dataset.

#### Correlation Analysis:
We looked at the correlation of all of our converted features to the price to determine which we should consider modeling. This was necessary because we had too many features to model in reasonable time complexity.
Model Selection: Evaluated multiple algorithms with Linear Regression using the following techniques: 
    - polynomial feature expansion
    - sequential feature selection
    - Lasso feature selection
    - Ridge

    
# Model
Our final model is a linear regression model that uses 10 sequentially selected features. While we did see that a polynomial feature expansion of 6 gave us a lower MSE for our test data, our sequential feature selection did not pick any features from a degree higher than 1. I believe we can safely remove polynomial feature selection from our model without compromised our accuracy. That being said, I am still not happy with the MSE result of this model. While it has helped us accurately predict some key drivers of price, it is not the most effective yet as a full predicition model.

<!-- For the Grader: My predictions did not turn out as accurately as I'd hoped. Any insight into what I can add/change to improve my model would be greatly appreciated!  -->

# Evaluation
Our analysis indicated that there are many factors that influence used car prices:
### Primary Drivers:
- Model – The specific model of the vehicle play the most significant role in determining price, as expected.
- Odometer – Mileage strongly correlates with depreciation; higher mileage tends to reduce a vehicle’s value.
- Year – Newer vehicles generally hold higher value, while older models depreciate over time.

### Secondary Factors:
- Type – The body style (e.g., sedan, SUV, truck) impacts pricing based on market demand and utility.
- Transmission Type – While automatic transmissions generally command a higher price than a manual transmission. A transmission type outside of these 2 categories (Other) generally has the strongest correlation with a car's purchase price.
- Fuel Type – While we didn't have enough hyrbid or electric cars in our dataset to use, we do still see a clear indication that gas and diesel cars tend to correlate with a higher sales value.
- Location – Regional factors such as climate, road conditions, and demand patterns influence pricing. Likely this is due to the location of sale and won't be of much use to a dealership in one particular region.
- Manufacturer – The brand reputation, reliability, and perceived quality seem to contribute to value retention.
# Conclusion
The insights derived from our model offer tangible business value despite the fact that our model's accuracy is still limited.
The current feature set captures many key pricing drivers and our data has shown us that there a large number of elements that influence a car's resale price. However, incorporating additional  (e.g., accident history, service records) would enhance model accuracy. In addition, there are many categorical values in our dataset we were not able to use due to our limited amount of data. Including my items in our dataset to cover these missing values would improve our predictions.

# Next steps
A model to predict a car's sales price is useful but will not tell us the full story about our dealership's revenue. Assuming we have limited capacity in our lot, stocking it full of expensive cars that do not sell frequently would not be fruitful endeavor. Any car on our lot is taking up space that could be filled by another car, so it is in the dealership's best interest to find cars with a good sales price that sell frequently.
I would urge the client to collect addition data around how long a car has been at the dealership before being sold. This will allow us to create a new model to predict a car's value per day at the dealership. For instance, a $10,000 car that take 30 days would be less valuable per day on the lot than a $2,000 car that sells in 5 days.
