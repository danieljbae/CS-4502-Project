# Data Mining the Yelp Open Dataset

## Description:

1. What makes a review vote tagged as Useful, Funny, or Cool with respect to the review's text and star rating? Are there nuanced patterns amongst major cities in the US?

2. What are frequent features of 1-star (negative) and 5-star (positive) text reviews for different categories of business?

3. Are there clusters of Yelp users who more frequently give positive or negative reviews? What is common among these users?

4. Are there unexpected regions with higher stars (rare patterns)? Something non-trivial that may be discovered are "hidden gems" such as food cart street or local spots

5. Do users that are more likely to give negative reviews have a network of friends that are also more likely to give negative reviews?

## Prior Work:

Since this dataset was released by Yelp for academic purposes, there is a plethora of prior work. Some relevant works include:

* Inferring Futrue Business Attention: [Link](https://www.yelp.com/html/pdf/YelpDatasetChallengeWinner_InferringFuture.pdf)
* Sentiment Analysis for Yelp Review Classification: [Link](https://urytrayudu1.medium.com/sentiment-analysis-for-yelp-review-classification-54b65c09ff7b)
* Identifying Social Sub-Groups Through Clustering of Yelp User Data: [Link](https://rpubs.com/saraabi/yelp_clustering)
* Text Mining and Sentiment Analysis for Yelp Reviews of A Burger Chain: [Link](https://towardsdatascience.com/text-mining-and-sentiment-analysis-for-yelp-reviews-of-a-burger-chain-6d3bcfcab17b)

## Datasets:

* **Download Link**: [Yelp Dataset](https://www.yelp.com/dataset)
 
* **Documentation**: [Yelp dataset attributes and types](https://www.yelp.com/dataset/documentation/main)
    
* **Files**:

> yelp_academic_dataset_business.json<br>
> yelp_academic_dataset_checkin.json<br>
> yelp_academic_dataset_review.json<br>
> yelp_academic_dataset_tip.json<br>
> yelp_academic_dataset_user.json
    
## Proposed work:

**Data Preprocessing:**

* **Data cleaning**:
    1. Filter non-english reviews and special characters
    2. Ignore users with no text reviews (i.e. missing data points).
    3. Ignore reviews with no attached text.
    4. Bin and cluster average user rating to detect "outlier" users that preferentially give the highest or lowest possible rating.
    5. Verify all user data points are unique.
    6. If time permits: detect and remove fake reviews and spam with machine learning techniques.


* **Data reduction**: 
    1. Remove attribute columns that are not relevant to our project using either forward selection or backward elimination.
    2. Identify and remove redundant data using correlation analysis (e.g. perhaps "useful" and "cool" vote counts are highly correlated)

* **Data integration**:
    1. Aggregate the initial json files into a relational database to improve accessibility.

* **Data transformation**:
    1. Normalize user attributes such as `compliment_cool`, `compliment_funny`, `compliment_cute` using Z-Scores or Min-Max.
    2. Use the bag-of-words model to simply review text (i.e. tokenize words, generate feature vectors for sentences).

## List of tools:

* **Data analysis and statistics**

    1. Pandas ([Link](https://pandas.pydata.org/))
    2. Numpy ([Link](https://numpy.org/)) 
    3. NetworkX ([Link](https://networkx.org/))

* **Data storage and integration**

    1. Sqlite ([Link](https://www.sqlite.org/))

* **Text processing and classification**

    1. Keras ([Link](https://keras.io/))
    2. Pytorch ([Link](https://pytorch.org/))
    3. NLTK ([Link](https://www.nltk.org/)
    4. TextBlob ([Link](https://textblob.readthedocs.io/en/dev/))



## Evaluation:

* **Similarity measures**:
    - Use different similarity measures depending on the data types involved, such as: Minkowski distance or euclidean distance.

* **Association rules and pattern evaluation measures**:
    - Identify associations by partitioning the data to find candidate itemsets (e.g. (1-star review) => funny review tag, (positive text review) => useful review tag)
    - Examine interestingness of associations using null-invariant measures, such as: Kulczynski and Jaccard.
* **Community Detection**:
    - Evaluate the relative density of links of a community, with the Louvain method or Label Propagation algorithm (e.g. communities of yelp users and their friends)


## Team members:
* Daniel Bae
* Thomas Cochran
* Patrick Conley
