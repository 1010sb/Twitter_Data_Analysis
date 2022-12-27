# Twitter_Data_Analysis

Twitter is an essential platform for sharing news, ideas, and opinions, and it has become increasingly 
important for staying up to date with the latest trends both locally and internationally. Because information 
is delivered faster on Twitter than on traditional news sites, analyzing Twitter data can provide valuable 
insights into current events and emerging trends. This makes it an important tool for businesses, researchers, 
and individuals looking to stay informed and stay ahead of the curve.

In this project, my objective was to analyze a dataset of tweets collected from the city of Hannover, Germany, in order to identify the following:

- The five most active users
- The five most frequently used hashtags
- The five most discussed topics


![Concept](https://user-images.githubusercontent.com/96765388/203555514-1a7fbd27-622a-4885-b3fb-6504d6d58f00.jpg)


#### To create virtual enviroment and install dependencies by using config.yaml file use following conda command:
##### By using this command we are going create a virtual enviroment named 'twitter_env'
$ conda env create -f config.yaml

#### To activate virtual enviroment 
$ conda activate twitter_env

#### To deactivate an environment
$ conda deactivate

#### To launch jupyter notebook from virtual enviroment
(twitter_env) ......>jupyter notebook


### Additional Package Requirement
- Data collection will be conducted by using the Python snscrape package and saved to a csv file
- Topic Visualization with pyLDAvis
#### Use python package manager pip to install
- pip install snscrape
- pip install pyLDAvis

### Collecting Twitter data
To collect the data for this analysis, I used the snscrape library with an English language filter to extract tweets from Twitter. 
The snscrape library is a powerful tool for collecting and stor-ing large amounts of data from social media platforms, and the English language filter allowed 
me to ensure that I was only collecting tweets written in English.  

## Data Analysis - Entity Analysis
#### Most Active User
There is no data cleaning required for this entity analysis as username are unique part. So just by applying nltk frequency distribution to get most active user based on their number of tweets and plot the most active user result with seaborn bar chart and save as .png file.
![MostActiveUser](https://user-images.githubusercontent.com/96765388/209583491-5ba2076e-ecd3-49f9-9ae9-a4251a393948.png)



### Most frequently used hashtags
Using the python regex library, remove the # sign from the data and convert it to lowercase string data. With the help of counter function, create a dictionary of words where the key are words, and the number of occurrences is values. Then apply nltk frequency distribution to get most frequently used hashtags based on their occurrence and plot the most frequently used hashtags re-sult with seaborn bar chart and save as .png file. 
![PopularHashtag](https://user-images.githubusercontent.com/96765388/209583497-dffc69bd-dee3-4abb-ae87-5457c60ce3f7.png)


### Most prevalent topics
##### Data Processing Steps 
1. Converted the tweet data to lower case string data
2.	Used the Python regex library to clean the tweets text and remove non-character ele-ments such as usernames, URLs, special characters, and hash signs
3.	Removed stop words from the tweets data using the NLTK stopwords functionality
4.	Stemmed the tweets data using the NLTK PorterStemmer
5.	Lemmatized the tweets data using the NLTK WordNetLemmatizer to convert words to their base form
6.	Vectorized the tweets data using the CountVectorizer with a n-gram range of (1,3) to in-clude unigrams, bigrams, and trigrams
7.	Vectorized the tweets data using the TF-IDF with a n-gram range of (1,3) to include uni-grams, bigrams, and trigrams.

### Topic Modeling
After pre-processing the tweets data and extracting the relevant features, I applied natural language processing (NLP) techniques such as non-negative matrix factorization (NMF) Latent Dirichlet Allocation (LDA) to identify the most discussed topics in dataset.
NMF and LDA are both techniques that allow me to identify patterns and relationships within a dataset by decomposing it into a set of latent factors or topics. By applying these techniques to cleaned and pre-processed tweets data, I was able to identify the most important and relevant topics.

##### - by using Latent Dirichlet Allocation (LDA) with CountVectorizer
##### - by using Latent Dirichlet Allocation (LDA) with TF_IDF
##### - by using Non-Negative Matric Factorization (NMF) with CountVector
##### - by using Non-Negative Matric Factorization (NMF) with TF_IDF

### Result Comparison 
After comparing the results of Non-Negative Matrix Factorization (NMF) and Latent Dirichlet Allocation (LDA) on Twitter data, I found that NMF gave superior results. There are two main reasons why I prefer NMF over LDA for analyzing tweets data:
- NMF is more interpretable than LDA because the latent structure of the documents and words are represented by separate matrices, which can be examined and interpreted indi-vidually. This can be particularly useful for understanding the themes and topics that are prevalent in a set of tweets.
- NMF is more robust to noise and sparse data than LDA because it is based on a different matrix decomposition method that is less sensitive to these types of issues. This can be useful for analyzing Twitter data, which can be noisy and contain many rare words. NMF is less likely to be affected by these factors, making it a potentially more reliable method for extracting meaningful structure from the data.
![NMF_TD-IDF_result](https://user-images.githubusercontent.com/96765388/209583934-78fb60da-b154-454a-9f44-b8da0e781dd3.JPG)


### Combination of NMF with TF-IDF
The combination of non-negative matrix factorization (NMF) with term frequency-inverse doc-ument frequency (TF-IDF) has been found to be an effective approach for extracting topics from Twitter data. This is likely due to the ability of TF-IDF to identify the most relevant and significant terms in the corpus, which can be particularly useful when working with large, noisy datasets like those found on social media platforms. This combination approach is likely to be used for similar analyses in the future.

## Topic Visualization with pyLDAvis
To check the quality of the data analysis, I added pyLDAvis as a visual tool to help me inter-pret the results of the NMF model. By using pyLDAvis, I was able to see the topics that were extracted from the data and how they were related to each other. This allowed me to better understand the patterns and trends in the data and helped me identify any potential issues or errors in the analysis. Additionally, the visual representation provided by pyLDAvis made it easier for me to communicate the results of the analysis to others, as it provided a clear and concise way to represent the data. The use of pyLDAvis significantly improved the quality of the data analysis by providing a more intuitive and interactive way to explore the results.
![pyLDAvis](https://user-images.githubusercontent.com/96765388/209584107-f952326b-f9c1-4e31-b40a-9d9d8a49320a.JPG)
