# Mining Las Vegas Restaurant Reviews on Yelp

Team: Daniel Bae, Thomas Cochran, Patrick Conley

## Description

The goal of our project is to mine interesting patterns in the Yelp Open Dataset ([Link](https://www.yelp.com/dataset)) that improve business planning and service for restaurants in the city of Las Vegas, NV. 

## Questions

Our project focused on three questions:

* What restaurant categories are frequently reviewed by Yelp users with low and high review counts?
* Do restaurants with high or low average star reviews cluster around specific locations in the city?
* Are there areas in the city where review sentiment is more negative or positive?

## Results

The Yelp open dataset lists business categories provided by the business owner. With these categories we predicted restaurant types (e.g. American, Fast Food, Pizza, Italian, etc.) through unsupervised classification using K-means clustering. Among these, we found that 'Nightlife', 'American', 'Mexican', 'Fast Food', and 'Sandwiches' are the top five most frequently reviewed restaurant types across all Las Vegas reviewers in our dataset. Yelp reviewers with lower review counts (approximately 0 to 5 reviews per user) rated 'specialtyfood', 'coffee', 'pizza', and 'bakeries' more frequently than very high reviewers (approximately 40 to 230 reviews per user) who reviewed 'asian fusion' and 'steak houses' more frequently. 


<img src="https://github.com/danieljbae/CS-4502-Project/tree/master/Analysis/Figures/fig1.png">


Our density-based spatial clustering of applications with noise (DBSCAN) findings identify locations around the city where certain restaurant types with good average star reviews (4 to 5) and bad average star reviews (0 to 3) form dense clusters. For example, good sushi bars form clusters around the center of the city, in close proximity to the casinos. In contrast, good mexican restaurants cluster away from the center of the city, while mediocre mexican restaurants remain closer to the center with the casinos (clusters are red, outliers are black):


<img src="https://github.com/danieljbae/CS-4502-Project/tree/master/Analysis/Figures/fig2.png">


## Applications

The results of this project can inform current and future restaurant owners about the reviewing trends of Yelp users in the city of Las Vegas, NV. The frequency of reviews received by different types of restaurants across low and high review count users allows restaurant owners to gauge which types of restaurants receive more or less attention from users on the platform. Using this information, restaurant owners may decide to change what food is being served, or change what dining atmosphere their restaurant creates, based on what is receiving more reviews. The locations of densely clustered restaurants of the same type can also give new restaurant owners valualbe information about where to open their restaurant. In certain blocks of the city, dense clusters of mediocre star reviewed restaurants could present challenges by creating a poor reputation in an area of the city, or by increasing the competition for customers. Using our results, restaurant owners may decide to avoid the competition or the negative reputation in these densely clustered areas. In either case, applications of our results are clearly directed towards improving the outcome of restaurants in the area by mining interesting patterns from Yelp reviewers in the area.


## Links

The presentation video is [TODO](https://www.python.org/)
The final report is [TODO](https://www.python.org/)




























## Description:

* **Goal:** 
    - Mining for patterns in restaurant review text that can facilitate improvements in food, service, and review quality.

* **Identify text patterns for different categories of restaurants:**
    - What are frequent features found in 1-star and 5-star restaurant reviews?
        - What are frequently used words?
        - How does review length vary?
    - Are there nuanced text patterns among major cities in the US?
    - Can seasonal changes affect text sentiment?

* **Identify text patterns among Yelp users:**
    - What makes a user's review tagged as Useful, Funny, or Cool?
    - Are there clusters of Yelp users who more frequently give positive or negative reviews? 
        - What is common among these users?
        - Are there associations between total review count, average star rating, or friend network?

## Prior Work:

Since this dataset was released by Yelp for academic purposes, there is a plethora of prior work. Some relevant works include:

* Kaggle Notebooks: [Link](https://www.kaggle.com/yelp-dataset/yelp-dataset/code)
* Category Predictor, Review Autocomplete: [Link](https://github.com/Yelp/dataset-examples)
* Inferring Futrue Business Attention: [Link](https://www.yelp.com/html/pdf/YelpDatasetChallengeWinner_InferringFuture.pdf)
* Sentiment Analysis for Yelp Review Classification: [Link](https://urytrayudu1.medium.com/sentiment-analysis-for-yelp-review-classification-54b65c09ff7b)
* Identifying Social Sub-Groups Through Clustering of Yelp User Data: [Link](https://rpubs.com/saraabi/yelp_clustering)
* Text Mining and Sentiment Analysis for Yelp Reviews of A Burger Chain: [Link](https://towardsdatascience.com/text-mining-and-sentiment-analysis-for-yelp-reviews-of-a-burger-chain-6d3bcfcab17b)

## Datasets:

The Yelp Open Dataset contains over 5 million user reviews on over 170 thousands businesses in 11 metropolitan areas. The raw data is contained in 5 json files containing user info, business info, ratings, and reviews.

* **Download Link**: [Yelp Dataset](https://www.yelp.com/dataset)
 
* **Documentation**: [Yelp dataset attributes and types](https://www.yelp.com/dataset/documentation/main)
    
* **Files**: 
  * yelp_academic_dataset_business.json
  * yelp_academic_dataset_checkin.json
  * yelp_academic_dataset_review.json
  * yelp_academic_dataset_tip.json
  * yelp_academic_dataset_user.json

## Proposed work:

* **Data cleaning**:
    * Filter non-english reviews and special characters.
    * Bin and cluster average user rating to detect and remove "outlier" users that preferentially give the highest or lowest possible rating.
    * Verify all user data points are unique.
    * Bin restaurants with similar types of cuisine.

* **Data reduction**: 
    * Remove attribute columns that are not relevant to our project.
    * Remove all business categories that are unrelated to food. 
    * Remove users with no text reviews.
    * Remove redundant data using correlation analysis

* **Data integration**:
    * Compile all .json files into a relational database to improve accessibility.
    * Import relational database to the cloud.

* **Data transformation**:
    * Normalize user attributes such as `compliment_cool` and `compliment_funny` using Z-Scores or Min-Max.
    * Use the bag-of-words model to simplify review text (i.e. tokenize words, generate feature vectors for sentences).
    * Model review text sentiment to classify reviews as either negative, positive or neutral

## List of tools:

* **Development Environment**
    * Python ([Link](https://www.python.org/))
    * Pycharm ([Link](https://www.jetbrains.com/pycharm/))
    * Jupyter Notebook ([Link](https://jupyter.org/))

* **Data analysis and statistics**

    * Pandas ([Link](https://pandas.pydata.org/))
    * Numpy ([Link](https://numpy.org/)) 
    * NetworkX ([Link](https://networkx.org/))
    * matplotlib ([Link](https://matplotlib.org/))

* **Data storage and integration**

    * Sqlite ([Link](https://www.sqlite.org/))
    * Google Cloud ([Link](https://cloud.google.com/))
    * Amazon Cloud ([Link](https://aws.amazon.com/))

* **Text processing and classification**

    * NLTK ([Link](https://www.nltk.org/)
    * TextBlob ([Link](https://textblob.readthedocs.io/en/dev/))

## Evaluation:

* **Clustering and Similarity measures**:
    - Cluster users grouped by star review.
    - Cluster negative and positive reviews grouped by location, word frequency and count, and month posted.
    - Use different similarity measures depending on the data types involved, such as: Minkowski distance or euclidean distance.
    
* **Association rules and pattern evaluation:**
    - Identify frequent itemsets (e.g. common words in reviews across ratings)
    - Identify associations between candidate itemsets, for example:
        - (1-star review) => funny review tag
        - (positive sentiment) => useful review tag
    - Examine interestingness of associations using null-invariant measures, such as: Kulczynski and Jaccard.
    
* **Community Detection**:
    - Evaluate the relative density of links of a community, with the Louvain method or Label Propagation algorithm (e.g. communities of yelp users and their friends)
    
* **Text Classification**:
    - Evaluate text sentiment using Naive Bayesian classification.
