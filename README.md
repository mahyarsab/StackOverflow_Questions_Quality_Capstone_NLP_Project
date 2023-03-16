# StackOverflow Questions Quality Capstone NLP Project

Author : Mahyar Sabouniaghdam

Email : saboonimahyar@gmail.com

![image](https://user-images.githubusercontent.com/122119114/225556215-a469d406-f794-4887-a921-00253b1c107e.png)

<img align=right src="https://user-images.githubusercontent.com/122119114/225575101-06ab10a4-0c4c-4f7c-8bc4-a44e0d7a029b.png">

## :book:  Overview :




The objective of this capstone project was to create a machine learning model that predicts the quality of questions posted on Stack Overflow, a popular question and answer platform for software developers. Our goal was to maintain a high-quality, organized repository of programming knowledge for all users to benefit from. To achieve this, we analyzed a dataset of 60,000 Stack Overflow questions and their corresponding quality ratings.


Stack Overflow receives millions of questions each year, and it is crucial to determine the quality of these questions to maintain the platform's reputation as a reliable source of information. About 6% of all new questions end up being closed, which can negatively impact the user experience. Our project aims to predict the quality of questions to reduce the time and effort required to filter through low-quality questions.


Improving the quality prediction of questions on question and answer platforms is a relevant problem area to apply data science techniques. Our project adds business value by enhancing the user experience of Stack Overflow users.




## 🗃 Contents :


1. Notebook 1 Main: Cleaning, Exploratory Data Analysis(EDA), Feature Engineering, Vectorization and Modeling Notebook

2. Notebook 2 Deeplearning: Deep Learning and Advanced Modeling Notebook 

3. A business report pdf file summarizing the capstone project

4. A presentation file in both PDF and PowerPoint formats, which was created for Demo Day

5. A READ_ME file 

Notes for the notebooks:

- The first notebook uses the base conda environment from the BrainStation curriculum. The second notebook uses the deep_learning conda environment from the same curriculum.

- To run the second notebook, the first notebook must be run to completion (the necessary code block is located above part 4 of the first notebook).


## 💾 Data Source :

The data was obtained from Kaggle and was split into train and validation sets by the dataset owner. The dataset can be found URL links below:

- https://www.kaggle.com/datasets/imoore/60k-stack-overflow-questions-with-quality-rate

- https://github.com/Moradnejad/StackOverflow-Questions-Quality-Dataset

I used an original dataset of 60,000 Stack Overflow questions from 2016-2020, classified into three categories: high-quality posts without a single edit, low-quality posts with a negative score and multiple community edits that remain open, and low-quality posts that were closed by the community without a single edit. I preprocessed the dataset by dropping the ID column and creating new columns such as Hour, weekday, month, year, number of words in the question, number of tags, and code availability.

## 🔮 EDA & Feature Engineering 🛠 :

After analyzing the dataset of questions and creating new columns by feature engineering, the following observations were made. Firstly, the majority of questions were created between 10-14 with the peak being between 12-1 pm. Secondly, more questions were created on weekdays compared to weekends. Additionally, the number of questions in the beginning months was higher, which could be due to the fact that 2020 only had January and February as months. Furthermore, 2016 had the highest number of questions. Most titles had between 4-6 words, and most questions had 2 tags.

![Shot 0002](https://user-images.githubusercontent.com/122119114/225566822-0c2a8d01-48d9-4ca8-ac3d-8be21cab93d3.png)



The lower number of questions had codes in them, and questions with shorter and fewer words and characters had a higher chance of being low-quality. The number of titles was denser than the body and were all gathered between 4-7 words. Questions created at night were more likely to be closed. The more tags a question had, the higher the chance of it being high-quality. Additionally, questions with code in them had the highest chance of being high-quality, whereas those without had the lowest chance.


![Shot 0003](https://user-images.githubusercontent.com/122119114/225566377-5b3ad2ef-c287-432b-9559-3444e6772bb4.png)

Due to a large number of tags, a hardcode was written to categorize them. Lastly, the most repeated words in the text of questions with the JavaScript tag were identified as the top tag.

![Shot 0001](https://user-images.githubusercontent.com/122119114/225567203-3864c623-1e48-438c-b677-17d9aa802dea.png)


## 📈 Insights, Modeling and Results 📉 :

In this step, I cleaned the text and created a correlation matrix. To avoid Memory Error and tackle data imbalance, I sampled and used TF-IDF to vectorize the data. My baseline Regression model scored 74.7% and I found that advanced technical words are most predictive for high-quality questions, while general words are more predictive for closed questions. JavaScript and PHP titles were also among the top predictive words for closed questions due to a higher chance of low-quality questions.

![Shot 0006](https://user-images.githubusercontent.com/122119114/225569041-8b7fd7b1-bdc8-49b8-b76b-c5ebb02975b1.png)

The optimization of the models involved scaling with Min Max Scaler and creating a PCA model to determine the optimal number of components. However, there was no significant improvement in the results of the PCA model, so dimension reducers were not used when moving on to advanced modeling. An ML Pipeline with Grid Search was run to find the best model with optimal hyperparameters. The models that were optimized were Logistic Regression, SVM, Random Forrest, and XG Boost. XG Boost was the best model in manual optimization, with a test accuracy score of 84.6% with n_estimators = 40 / max_depth = 6. Advanced modeling and Grid Search gave the same results, and the XG Boost model was again the best. Deep-learning models were also tried, such as ANN and Multi Class NNs, but the test accuracy score for the XG Boost model was still better at 79.43%. The NNs models had lower test scores than the XG Boost model and could not be further explored due to computational limits.

![image](https://user-images.githubusercontent.com/122119114/225577957-27e94aa3-ca6e-4313-b88d-339a868b6249.png)


## 🔆 Final Remarks 🕯 :

In the supplementary notebook for deep learning, it was found that XG Boost is still the best model. The next step was to determine the optimal threshold value by plotting precision and recall scores for a range of threshold values. The optimal threshold value was found to be between 0.2 and 0.4. To further evaluate the XG Boost model, the Receiver Operating Characteristic (ROC) curve was plotted to compare the true positive rates (TPR) and false positive rates (FPR) and check the Area Under the Curve (AUC) value. The AUC score of ~0.88 indicates a high probability that the classifier will correctly classify a randomly chosen high-quality question, which is a good result and indicates that the model performs well for the high-quality question recognizer.

![image](https://user-images.githubusercontent.com/122119114/225573162-96d9b959-0d5e-4917-b854-0a9666e6f4ea.png)

## ⏳ Next Steps 🪄 :

- Search for less biased data.
- Conduct a Word Embedding analysis.
- Explore more advanced NLP Models.
- Run an extensive ML Pipeline with GridSearch via AWS.
- Develop an API to predict the quality rating of the questions.


![image](https://user-images.githubusercontent.com/122119114/225555861-25ad0ed0-7e09-4222-a8c9-4329b45e5099.png)
