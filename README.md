# Data Mining the Yelp Open Dataset

## Description:

	The Yelp Open Dataset contains over 5 million user reviews on over 170 thousands businesses in 11 metropolitan areas. The raw data is contained in 5 json files containing user info, business info, ratings, and reviews. A number of interesting questions can be answered using these data:

1. Are there optimal operating hours and locations for different categories of businesses?

2. Predict which businesses are likely to fail or succeed.

3. Are more active yelpers prone to giving higher ratings or more thorough reviews?

4. Do some yelpers give generally negative/positive reviews?

5. Are there common words present in reviews with similar ratings?

6. How consistent are ratings with common keywords?

7. Do business ratings change over time? Can this change be attributed to attributes in the review data?

8. What is the highest rated type of food (i.e. what restaurant is likely to please most?)

9. What type of business receives the best/worst ratings?

10. Does the quantity of photos indicate the rating of a business?

11. Where is the best/worst region for a business type?  

## Prior Work:

Category Predictor, Review Autocomplete: 
https://github.com/Yelp/dataset-examples

Kaggle Notebooks:
https://www.kaggle.com/yelp-dataset/yelp-dataset/code

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
Remove incomplete user, business, review data
Remove unecessary attributes
Fill in empty attributes
Compile all .json files into a relational database
Test availability and data format for concurrent remote development

## List of tools:
*Python, PyCharm, Jupyter Notebooks, numpy, pandas, matplotlib
*SQlite, Google/Amazon Cloud database if necessary


## Evaluation:
* Frequent Itemsets (common words in reviews across ratings)
* Support, Confidence, Correlation
* Bayesian Classification
* Outlier Detection 

## Team members:
* Daniel Bae
* Thomas Cochran
* Patrick Conley
