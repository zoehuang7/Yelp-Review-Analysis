# Yelp-Review-Analysis
**Dataset Link: https://www.kaggle.com/yelp-dataset/yelp-dataset**
# 1. Overall Project Objectives
Yelp is an application to provide the platform for customers to write reviews and provide a star-rating. A research indicates that a one-star increase led to 59% increase in revenue of independent restaurants. Therefore, we see great potential of Yelp dataset as a valuable insights repository.

The main purpose of our project is to conduct thorough analysis on 7 different cuisine types of restaurants which are Korean, Japanese, Chinese, Vietnamese,Thai, French and Italian, figure out what makes a good restaurant and what concerns customers, and then make recommendations of the future improvement and profit growth. Specifically, we will mainly analyze customers' reviews and figure out reasons why customers love or dislike the restaurant. For example, there may be great reviews primarily due to the friendly service, or negative reviews about high price. Meanwhile, we will also compare among those 7 different cuisine types and figure out differences from reviews and gain valuable insights to make customized recommendations to different types of restaurants.

# 2. Description of Data
The Yelp dataset is downloaded from Kaggle website. In total, there are 5,200,000 user reviews, information on 174,000 business. we will focus on two tables which are business table and review table. 

**Attributes of business table are as following:**
* business_id: ID of the business
* name: name of the business
* neighborhood
* address: address of the business
* city: city of the business
* state: state of the business
* postal_code: postal code of the business
* latitude: latitude of the business
* longitude: longitude of the business
* stars: average rating of the business
* review_count: number of reviews received
* is_open: 1 if the business is open, 0 therwise
* categories: multiple categories of the business

**Attribues of review table are as following:**
* review_id: ID of the review
* user_id: ID of the user
* business_id: ID of the business
* stars: ratings of the business
* date: review date
* text: review from the user
* useful: number of users who vote a review as usefull
* funny: number of users who vote a review as funny
* cool: number of users who vote a review as cool

# 3. Direction of Analysis
**Exploratory data analysis**

* Count the number of each cuisine type of restaurants
* Count the number of reviews in each cuisine type of restaurants
* Visualize the distribution of restaurants according to the ratings and cuisine types of restaurants.

**Review Analysis**
* Clean the category column in business table into different cuisine types of restaurants and find out how the reviews can help this type of restaurants improve in the future.
* Refer the business id in business table to review table, collect all the reviews of this type of restaurants and perform sentiment analysis to analyze frequent words in positive and negative reviews.
* Implement SVM model to get relatively positive and negative words and get score of each word.
* Get top 10 positive words and negative words in each cuisine type of restaurants in order to figure out the reason of high score and low score.
* Compare among different types of restaurants to figure out the advantages and disadvantages, then we can generate a series of recommendations to this type of restaurants for the future development.
* Overall, recommendations may have different topics which is but not limited to service, food, or decoration, etc. Our analysis is generally based on review words which we can tell from such as rude, overpriced, and slow to find out which aspect in this type of restaurants that they could improve.

# 4. Summary of Progress
**Selection and Filtering**
* Filter out 50 states of US.
* Filter out all restaurants of US.

**Cleaning**
* Categorize all restaurants by cuisine type using the matching keywords.
* Delete all records with null category.
* Remove quotation marks of name and address columns.
* Label restaurants above rating of 4 as positive, below rating 3 label as negative, label rating 3 as neural.
* Drop rows with neural label.
* Apply 'bag of words': the frequencies of various words appeared in each review as features and conduct SVM model to get score of each word.

**Reshaping and Reindexing**
* Reindex the data frame.
* Build a new column to input the new category name and delete the previous column.
* Convert array to dataframe.

**Visualization**
* Visualize the distribution of restaurants and reviews by category using seaborn.
* Visualize the distribution of restaurants and reviews by rating.
* Visualize top 10 negative words and positive words in each cuisine type.

**Manipulation**
* Get a 'polarity score' (a value that reflects the polarity of sentiment) towards each restaurant category, the sentiment score of each word was first multiplied by its frequency, and then normalized by the total number of reviews for the specific category of restaurants.
* Merging multiple data sets
* Merge business table and review.

# 5. Findings
In general, We found out that for most restaurant types, delicious ranks first among all positive words, indicating that tastes might weight more than other factors like service and price when people are judging a restaurant. For most cuisine types, the word friendly rank first before the word reasonable, which means the friendly service is more likely to be the reason for the high score rather than reasonable price. It could also be observed that when it comes to the flavor of food, customers value freshness more than tastiness.

Different characteristics are also shown for different restaurant categories. Vietnamese and Italian food received positive feedback because of freshness, while French restaurants received positive reviews for their sweet food. However, sweet food is the reason for Korean restaurants to have negative reviews. Korean, Japanese, Chinese, and Thai have positive reviews mainly for their friendly service, especially for Korean restaurants, since attentive ranks third. The variety of food is also the reason of high score for Korean, Japanese and Thai cuisine types. Fun and creative are special charateristics for Japanese restaurants. For Italian cuisine type, customers prefer classic Italian food. The reason of high score in French cuisine type is related to the romantic and beautiful appearence or environment.

From the negative word list, we could observe that bland is one of the main problems for Korean, Thai and Vietnamese restaurants, which means customers expect food of those three cuisine type should be spicy. For French, Italian and Japanese cuisine types of restaurants, it is likely to have the low score because the food is cold. The low score of Japanese cuisine type is also due to the dark and crowded environment. Sour is one of the main problems for Chinese cuisine type. Slow service is the main negative characteristic for Korean and French. French cuisine type receive negative reviews also for the expensive price. Thai receive negative reviews mainly for greasy food.

Since our analysis may help to extract specific features from any set of reviews, restaurant owners can make good use of it for essential information once they received a certain amount of Yelp reviews. From those reviews they can understand why customers love or dislike their restaurants, maybe great reviews primarily due to fresh food, or perhaps unsatisfied reviews caused by too high price. Meanwhile they can also compare the restaurant with similar restaurants within the same type.
