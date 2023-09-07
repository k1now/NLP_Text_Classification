# NLP-Text-Classification
**NLP Text Classification techniques used for Sentiment Classification of Amazon Customer Reviews**

**Note** There are three notebooks in this repository. Each notebook is associated with a different dataset that the models are fitted on (see the Dataset section below). While the analysis is similar, there is valuable insight into each dataset and the specific usecase they can address. It is recommended to follow the order when reviewing the notebooks.

**Project Overview:** The objective of this project is to utilize Natural Language Processing (NLP) text classification techniques to analyze customer review sentiments on Amazon products. The primary goal is to develop a model for classifying reviews as either positive or negative and identifying the features and key words that are most associated with each of the sentiments. Six different machine learning models, including Logistic Regression, Decision Tree, Naive Bayes, Support Vector Machines (SVM), and Random Forest and AdaBoost Ensemble Models were evaluated as part of this project to identify the top performer. In conclusion, Logistic Regression performed best, as measured by accuracy, precision and recall scores, on three different datasets.

**Dataset:** We fitted the models on three different datasets of customer reviews: 1) Mix of reviews across variaous product categories, 2) Grocery product category reviews, 3) Reviews associated with a specific product. We compared the model performance, and more importantly, the insight we got into features (key words) associated with a positive or negative review for each dataset.

The data processing comprised of reducing the data into two columns: the review and the sentiment. The sentiment was derived from the star ratings associated with each review, where 4 or 5 stars were considered 'positive', 1 and 2 stars were considered negative, and 3 star was considered neutral and ommitted from the analysis.

**Data source:**

Reviews across various categories: https://www.kaggle.com/datasets/kritanjalijain/amazon-reviews (look for the train.csv file)</br>
Grocery and product-specific datasets: https://www.kaggle.com/datasets/cynthiarempel/amazon-us-customer-reviews-dataset?select=amazon_reviews_us_Grocery_v1_00.tsv (look for the amazon_reviews_us_Grocery_v1_00.tsv file)</br>

**Instructions for downloading the notebooks and making Datasets available for upload into the Jupyter files** </br>
1. From the 'code' menu on this repository page, select 'Download ZIP'. Upon unzipping the downloaded folder, there will be three .py files along with a readme file.</br>
2. Within the unzipped folder, create a new folder and name it "Data".</br>
3. Download both files listed in the Data Source section. These are the datasets leveraged for training the models.</br>
4. Move both files to the 'Data' folder created in step 2.</br>
5. Rename the 'amazon_reviews_us_Grocery_v1_00.tsv' file to 'amazon_grocery.tsv'.</br>

All three of the notebooks will be ready to run after completing these steps.</br>

**Project Objective:** Key usecases to the Sentiment Analysis conducted in this project through NLP Text Classification are as follows:

1. <u>Sentiment Prediction:</u> The fitted model scales customer review insight analysis by automatically classifying reviews as positive or negative, eliminating the need to read through each review.

2. <u>Feature Importance Analysis:</u> The model coefficients can provide various layers of insight into the keywords or phrases that are strongly associated with positive or negative sentiment. The generic dataset, which entailed customer reviews across various product categories, provides strategic insight into the characteristics of a happy or unhappy e-commerce customer. The product-specific review dataset provides insight into specific reasons customers are happy or unhappy with a given product. 

3. <u>Sentiment-based Feedback Loop:</u> Once the features of positive and negative sentiment are identified, they can be leveraged as a feedback loop into business growth. Features associated with positive reviews can be echoed in marketing campaigns or be leveraged as guidelines for future product developments. Features associated with negative reviews can be leveraged for product enhancement and corrective measures. 


**Data Preprocessing and Feature Extraction Techniques** To preprocess the data, we leveraged negation handling, lowercasing, removing punctuation, removing stop words, tokenization and stemming techniques. In addition, we iterated over both Bag-of-Words and TF-IDF feature extraction techniques to find the model that yields highest scores.

**Model Evaluation**
For each of the three datasets, each of the six models were evaluated with different hyper-parameters through grid search and evaluated for accuracy, precision and recall. </br>

&nbsp;&nbsp;&nbsp;&nbsp;**Image 1:** Comparing the Accuracy, Precision and Recall Scores for Models fitted on reviews across various categories</br>

![plot_one](https://github.com/k1now/NLP_Text_Classification/assets/130093844/b8304534-8272-4d49-b4ee-4459f9e85b79)


&nbsp;&nbsp;&nbsp;&nbsp;**Image 2:** Comparing the Accuracy, Precision and Recall Scores for Models fitted on reviews across Grocery only categories</br>

![plottwo](https://github.com/k1now/NLP_Text_Classification/assets/130093844/494b9ee8-b9d8-4352-bf18-33104f2a5067)


&nbsp;&nbsp;&nbsp;&nbsp;**Image 3:** Comparing the Accuracy, Precision and Recall Scores for Models fitted on reviews of a specific product</br>

![plotthree](https://github.com/k1now/NLP_Text_Classification/assets/130093844/02e22e8c-75ae-402c-862d-e366263c7660)


**Conclusions:**
Comparing the results of the three sections, with three different granularity levels in the dataset fitted to the models, we arrive at the following conclusions:

1. Logistic Regression performed the best for our NLP Text Classification Task. While SVM and Ensemble Models had high accuracy, precision, and recall scores, Logistic Regression had the highest scores and the second-fastest fitting time.

2. The performance score of the models improved when the data became more granular. For the first dataset, which had reviews across various categories, the Logistic Regression model achieved an accuracy of 87%. The score improved to 93% for the Grocery reviews and to 97% for the product-specific reviews. This reflects the significance of leveraging the appropriate training data when the models are used to classify sentiments at scale.

3. Features (keywords) associated with positive and negative sentiments became more specific as the training data became more granular. The keywords corresponding to the initial model trained on various product category reviews were more generic and can serve as a strategic direction for understanding what makes a customer happy or unhappy in e-commerce. The second dataset, focused on Grocery reviews, had specific keywords related to taste. The third dataset, which was product-specific, provided specific insights about the positives and negatives of the product itself.

&nbsp;&nbsp;&nbsp;&nbsp;**Image 4:** Top Features (or keywords) associated with Positive and Negative Sentiments for Models fitted on reviews across various categories</br>

![image_four](https://github.com/k1now/NLP_Text_Classification/assets/130093844/98f8775a-5dbf-4362-82bb-32ede44bcd07)



&nbsp;&nbsp;&nbsp;&nbsp;**Image 5:** Top Features (or keywords) associated with Positive and Negative Sentiments for Models fitted on reviews across Grocery only categories</br>

![image_five](https://github.com/k1now/NLP_Text_Classification/assets/130093844/a318cdd3-bda6-40f4-9530-72030c217feb)



&nbsp;&nbsp;&nbsp;&nbsp;**Image 6:** Top Features (or keywords) associated with Positive and Negative Sentiments for Models fitted on reviews corresponding to a specific Product</br>

![image_six](https://github.com/k1now/NLP_Text_Classification/assets/130093844/8869e848-acbc-4815-a0c0-9610be492b88)




**Recommendations**
While the model works with reasonable accuracy, precision, and recall scores, the performance will certainly improve with a better volume of training data. For this project, we had millions of reviews at our disposal, yet we had to select a 25k sample given the computation capacity of the PC at hand.

As described previously, the model is a powerful tool for categorizing new reviews as positive or negative sentiment. Specifically, this model can be used for analyzing customer reviews crawled from competitor sites that have no star rating for a given review and prepare benchmark reports.

Lastly, a key use case for this model is the feedback loop described previously. This tool makes it scalable for sellers selling on e-commerce websites to gain insight into what makes customers happy or unhappy about specific products. The positives can be echoed in marketing campaigns, while the negatives are specific areas for product improvement.




**Contact and Further Information** </br>
Kayvan Nowrouzi </br>
Email: kayvan.nowrouzi@gmail.com </br>
LinkedIn: linkedin.com/in/kayvannowrouzi </br>
