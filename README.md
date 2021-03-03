# Text Mining Yelp Restaurant Reviews

## Description:

* **Goal:** Identify patterns in restaurant review text that can facilitate improvements in food, service, and review quality.

* **Identify review text patterns for different categories of restaurants:**
    - What are frequent features found in 1-star and 5-star text reviews for different categories of restaurants?
        - What are frequently used words?
        - How does review length vary?
    - Are there nuanced text review patterns among major cities in the US?
    - Can seasonal changes affect text review sentiment?

* **Identify review text patterns among Yelp users:**
    - What makes a user's text review tagged as Useful, Funny, or Cool?
    - Are there clusters of Yelp users who more frequently give positive or negative reviews? 
        - What is common among these users?
        - Are there associations between total review count, average star rating, or friend network and review negativity?

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
    * Filter non-english reviews and special characters
    * Remove users with no text reviews.
    * Remove unecessary attributes and fill in empty attributes.
    * Bin and cluster average user rating to detect "outlier" users that preferentially give the highest or lowest possible rating.
    * Verify all user data points are unique.
    * If time permits: detect and remove fake reviews and spam with machine learning techniques.

* **Data reduction**: 
    * Remove attribute columns that are not relevant to our project using either forward selection or backward elimination.
    * Identify and remove redundant data using correlation analysis (e.g. perhaps "useful" and "cool" vote counts are highly correlated)

* **Data integration**:
    * Compile all .json files into a relational database to improve accessibility.

* **Data transformation**:
    * Normalize user attributes such as `compliment_cool`, `compliment_funny`, `compliment_cute` using Z-Scores or Min-Max.
    * Use the bag-of-words model to simply review text (i.e. tokenize words, generate feature vectors for sentences).

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

    * Keras ([Link](https://keras.io/))
    * Pytorch ([Link](https://pytorch.org/))
    * NLTK ([Link](https://www.nltk.org/)
    * TextBlob ([Link](https://textblob.readthedocs.io/en/dev/))

## Evaluation:

* **Similarity measures**:
    - Use different similarity measures depending on the data types involved, such as: Minkowski distance or euclidean distance.
    
* **Association rules and pattern evaluation measures**:
    - Identify frequent itemsets (e.g. common words in reviews across ratings)
    - Identify associations by partitioning the data to find candidate itemsets (e.g. (1-star review) => funny review tag, (positive text review) => useful review tag)
    - Examine interestingness of associations using null-invariant measures, such as: Kulczynski and Jaccard.
    
* **Community Detection**:
    - Evaluate the relative density of links of a community, with the Louvain method or Label Propagation algorithm (e.g. communities of yelp users and their friends)
    
* **Classification**:
    - Decision Tree Classification
    - Bayesian Classification

## Team members:
* Daniel Bae
* Thomas Cochran
* Patrick Conley
