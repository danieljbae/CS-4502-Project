# Mining Las Vegas Restaurant Reviews on Yelp

Team: Daniel Bae, Thomas Cochran, Patrick Conley

## Description

The goal of our project is to mine interesting patterns in the Yelp Open Dataset ([Link](https://www.yelp.com/dataset)) that improve business planning and service for restaurants in the city of Las Vegas, NV. 

## Questions

Our project focused on the following questions:

* What restaurant categories are frequently reviewed by Yelp users with low and high review counts?
* Do restaurants with high or low average star reviews cluster around specific locations in the city?
* Are there areas in the city where review sentiment is more negative or positive?
* Can seasonal changes improve or impair restaurant review sentiment? If so, which restaurants are most affected by seasonal change?
* What are common text topics in Yelp low and high star reviews?

## Results

The Yelp open dataset lists business categories provided by the business owner. With these categories we predicted restaurant types (e.g. American, Fast Food, Pizza, Italian, etc.) through unsupervised classification using K-means clustering. 

Among these, we found that 'Nightlife', 'American', 'Mexican', 'Fast Food', and 'Sandwiches' are the top five most frequently reviewed restaurant types across all Las Vegas reviewers in our dataset. Yelp reviewers with lower review counts (approximately 0 to 5 reviews per user) rated 'specialtyfood', 'coffee', 'pizza', and 'bakeries' more frequently than very high reviewers (approximately 40 to 230 reviews per user) who reviewed 'asian fusion' and 'steak houses' more frequently.

Our density-based spatial clustering of applications with noise (DBSCAN) findings identify locations around the city where certain restaurant types with good average star reviews (4 to 5) and bad average star reviews (0 to 3) form dense clusters. For example, good sushi bars form clusters around the center of the city, in close proximity to the casinos. In contrast, good mexican restaurants cluster away from the center of the city, while mediocre mexican restaurants remain closer to the center with the casinos.

There was little variation observed throughout the year in review sentiment. Using tokenized review text, the top word across all categories is 'food'. In five star reviews, the words 'good', 'service', 'great', and 'try' were frequently used. One star reviews often used words 'service', 'time', and 'place'.


## Applications

The results of this project can inform current and future restaurant owners about the reviewing trends of Yelp users in the city of Las Vegas, NV. 

The frequency of reviews received by different types of restaurants across low and high review count users allows restaurant owners to gauge which types of restaurants receive more or less attention from users on the platform. Using this information, restaurant owners may decide to change what food is being served, or change what dining atmosphere their restaurant creates, based on what is receiving more reviews. 

The locations of densely clustered restaurants of the same type can also give new restaurant owners valualbe information about where to open their restaurant. In certain blocks of the city, dense clusters of mediocre star reviewed restaurants could present challenges by creating a poor reputation in an area of the city, or by increasing the competition for customers. Using our results, restaurant owners may decide to avoid the competition or the negative reputation in these densely clustered areas. In either case, applications of our results are clearly directed towards improving the outcome of restaurants in the area by mining interesting patterns from Yelp reviewers in the area.


## Links

The presentation video is [here](Group1_TextMiningYelpRestaurantReviews_Part6_Video.mp4)

The final report is [here](Group1_TextMiningYelpRestaurantReviews_Part4.pdf)
