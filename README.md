# Detecting depression via tweets

## Introduction
Based on World Health Organisation (WHO), depression is a common mental disorder. Globally, more than 264 million people of all ages suffer from depression. Depression is different from usual mood fluctuations and short-lived emotional responses to challenges in everyday life. Especially when long-lasting and with moderate or severe intensity, depression may become a serious health condition. It can cause the affected person to suffer greatly and function poorly at work, at school and in the family. At its worst, depression can lead to suicide. 

Depression is highly treatable. When depression is recognised and treated, a person’s quality of life can be greatly improved.

### Problem Statement
We can leverage social media to detect depression. One good platform is Twitter as users can easily create an account by remaining anonymous since it doesn't require personal information. 

Users are able to express their thoughts freely without worrying about being judged on twitter . My objective is to detect signs of depression via tweets so we can encourage these individuals to seek help and treatment. 

Using data from other sources, I selected 3 classification models and LSTM + CNN model to train the data, and will select the best model based on accuracy for further evaluation. 

I will also look at if the model can still predict with good accuracy even after removing the top feature word.


### Data collection
I use datasets from these two sources and did further cleaning manually to get the final set of depressed tweets.<br>


*   [Depression Detection with Boosting Ensemble Learning Classifiers](https://github.com/Harshita9511/Depression-Detection-with-Boosting-Ensemble-Learning-Classifiers)
*   [Detecting Depression in Tweets](https://github.com/viritaromero/Detecting-Depression-in-Tweets)

For positive tweets, I use a sample of tweets labeled positive from<br>

*   [Sentiment140 Kaggle dataset](https://www.kaggle.com/kazanova/sentiment140)

After which, I combine both depressed and positive tweets which make up the final dataset.


### Summary
I cleaned the data by removing unnecessary words and punctuations, drop duplicate values and also lemmatize to get the root word to minimise word duplicates.<br><br>
I evaluate via 4 different models - Logistic regression, Random forest, Multinomial Naive Bayes, LSTM + CNN. For the first 3 models, I use GridSearchCV to search the best parameters that can give the best score. 



### Conclusion and recommendations

In conclusion, based on the initial modeling results, Random Forest is the best model that can detect tweets with signs of depression as it has a high 98% accuracy score and low false negatives as well. It would be good to look into what is the data that causes the false negatives so I can improve the model further and lower false negatives. 

After removing the word 'depression', accuracy dropped by 20% which means that if there are depressed tweets that does not contain this keyword, the model might not be able to label correctly. I would consider to look at how to improve the model when top keywords are not present so that the model can still work well.

I would also consider to explore LSTM + CNN further by using pretained word embedding such as GloVe and see if results can be better.

As depression is only one of the types of mental health disorder, I would also consider to look at other common mental health disorder such as anxiety as well.<br>
At a global level, I would recommend Twitter to consider having such model to monitor tweets worldwide and reach out to local organisations if they find any tweets that are of concern. 

Local organisations such as Institute of Mental Health (IMH) Samaritans of Singapore (SOS), Singapore Association for Mental Health (SAMH) or even goverment organisation - Health Promotion Board can also consider looking at using the model to monitor tweets that are of red flags and render help to individuals if required.


 
