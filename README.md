# NLP-Text-Classification
**NLP Text Classification techniques used for Sentiment Classification of Amazon Customer Reviews**

**Note** There are three notebooks in this repository. Each notebook is associated with a different dataset that the models are trained on (see the Dataset section below). While the analysis is similar, there is valuable insight into each dataset and the specific usecase they can address. It is recommended to follow the order when reviewing the notebooks.

**Project Overview:** The objective of this project is to utilize Natural Language Processing (NLP) text classification techniques to analyze customer review sentiments on Amazon products. The primary goal is to develop a model for classifying reviews as either positive or negative and identifying the features and key words that are most associated with each of the sentiments. Six different machine learning models, including Logistic Regression, Decision Tree, Naive Bayes, Support Vector Machines (SVM), and Random Forest and AdaBoost Ensemble Models were evaluated as part of this project to identify the top performer. In conclusion, Logistic Regression performed best, as measured by accuracy, precision and recall score, on three different datasets - with different levels of granularity - fitted into the model.

**Dataset:** We fitted the models on three different datasets of customers reviews: 1) Mix of reviews across variaous product categories, 2) Grocery product category reviews, 3) Reviews associated with a specific product. We compared the model performance, and more importantly, the insight we got into features (key words) associated with a positive or negative review for each dataset.

The data processing comprised of reducing the data into two columns: the review and the sentiment. The sentiment was derived from the start ratings associated with each review, where 4 or 5 stars were considered 'positive', 1 and 2 stars were considered negative, and 3 star was considered neutral and ommitted from the analysis.

Data source:

Reviews across various categories: https://www.kaggle.com/datasets/kritanjalijain/amazon-reviews
Grocery and product-specific datasets: https://www.kaggle.com/datasets/cynthiarempel/amazon-us-customer-reviews-dataset?select=amazon_reviews_us_Grocery_v1_00.tsv


**Project Objective:** Key usecases to the Sentiment Analysis conducted in this project through NLP Text Classification are as follows:

1. <u>Sentiment Prediction:</u> The fitted model scales customer review insight analysis by automatically classifying reviews as positive or negative, eliminating the need to read through each review.

2. <u>Feature Importance Analysis:</u> The model coefficients can provide various layers of insight into the keywords or phrases that are strongly associated with positive or negative sentiment. The generic dataset, which entailed customer reviews across various product categories, provides strategic insight into the characteristics of a happy or unhappy e-commerce customer. The product-specific review dataset provides insight into specific reasons customers are happy or unhappy with a given product. 

3. <u>Sentiment-based Feedback Loop:</u> Once the features of positive and negative sentiment are identified, they can be leveraged as a feedback loop into business growth. Positive reviews can be 


**Data Preprocessing and Feature Extraction Techniques** To preprocess the data, we leveraged negation handling, lowercasing, removing punctuation, removing stop words, tokenization and stemming techniques. In addition, we iterated over both Bag-of-Words and TF-IDF feature extraction techniques to find the model that yields highest scores.

**Model Evaluation**
For each of the three datasets, each of the six models were evaluated with different hyper-parameters through gird search and evaluated for accuracy, precision and recall.

**Conclusions:**
Comparing the results of the three sections, with three different granularity levels in the dataset fitted to the models, we arrive at the following conclusions:

1. Logistic Regression performed the best for our NLP Text Classification Task. While SVM and Ensemble Models had high accuracy, precision, and recall scores, Logistic Regression had the highest scores and the second-fastest fitting time.

2. The performance score of the models improved when the data became more granular. For the first dataset, which had reviews across various categories, the Logistic Regression model achieved an accuracy of 87%. The score improved to 93% for the Grocery reviews and to 97% for the product-specific reviews. This reflects the significance of leveraging the appropriate training data when the models are used to classify sentiments at scale.

3. Features (keywords) associated with positive and negative sentiments became more specific as the training data became more granular. The keywords corresponding to the initial model trained on various product category reviews were more generic and can serve as a strategic direction for understanding what makes a customer happy or unhappy in e-commerce. The second dataset, focused on Grocery reviews, had specific keywords related to taste. The third dataset, which was product-specific, provided specific insights about the positives and negatives of the product itself.

**Recommendations**
While the model works with reasonable accuracy, precision, and recall scores, the performance will certainly improve with a better volume of training data. For this project, we had millions of reviews at our disposal, yet we had to select a 25k sample given the capacity of the personal computers at hand.

As described previously, the model is a powerful tool for categorizing new reviews as positive or negative sentiment. Specifically, this model can be used for analyzing customer reviews crawled from competitor sites that have no star rating for a given review.

Lastly, a key use case for this model is the feedback loop described previously. This tool makes it scalable for sellers selling on e-commerce websites to gain insight into what makes customers happy or unhappy about specific products. The positives can be echoed in marketing campaigns, while the negatives are specific areas for product improvement.




Contact and Further Information
Kayvan Nowrouzi
Email: kayvan.nowrouzi@gmail.com
LinkedIn: linkedin.com/in/kayvannowrouzi
