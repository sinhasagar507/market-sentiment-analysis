## Analyzing-Financial-News-Headlines
Sentiment Classification using Keyword-based approach and Point of Mutual Information(PMI)
* Unsupervised Classification using Turney's algorithm through Point of Mutual Information(PMI) and keyword extraction to generate training labels 
* Handling Imbalanced Dataset using Synthetic Minority Oversampling Technique(SMOTE)
* Machine Learning Techniques for Classification on Validation Data

## Motivation
Financial news data can be helpful in numerous ways. It can be used in NLP projects to understand the overall scenario of the current market, analyse historical data and find cyclic trends, etc. With regard to Indian markets in particular, it faces a lot of highs and lows on a recurring basis. While numbers help in various statistical interpretations and are also readily available, they do not reveal the complete story. It is also important to analyse the trends through news sources and predict the overall sentiment of the market.

## Dataset(s)
#### [Business Standard News Feeds](https://github.com/sinhasagar507/market-sentiment-analysis/tree/master/data)
The dataset contains 50K news headlines and descriptions dating back from 2003 to May 2020. It comprises three main columns:
1. **Date** - Date of the posted news article 
2. **Title** - Headline of news article 
3. **Description** - A small description about the news article 

## Workflow
#### Exploratory Data Analysis(EDA) and Feature Extraction 
   - Word Tokenization and Lemmatization 
   - Part Of Speech(POS) Tag Extraction 
   - Added lexical features such as word count, POS tags, etc.
   - Compiled a list of positive and negative sentiment keywords from the dataset and selected the most frequently occuring word(s)  
   - Caculated PMI and overall sematic orientation(SO) of the sentence with respect to these keywords. In original Turney’s work, the no. of  hits are calculated by issuing queries to a search engine(hence the IR in PMI-IR) noting the number of hits(matching documents). The author used AltaVista engine since it has a NEAR operator. Since the search engine has deprecated, we consider our corpus as our database from which we extract frequency counts of phrases. Using regular expressions, we implemented a NEAR operator which searches for the occurrence of phrases in the vicinity of keywords.
  
 
## Model 
   - Applied Multinomial Naive Byes, Random Forest, ANN and LSTMs for binary sentiment classification 
   - Achieved best Macro-F1 score of 0.76 and a recall score of 0.81 

   
## Limitations 
   - Less weighted F1-Score on label marked "0" - Data Augmentation with older news headlines can enhance the low F1-score of the 
   - Algorithm scalability - Deriving sentiment relies upon distance-based metrics for calculating semantic orientation, hence such a methodology is inefficient to account for larger semantic variation or large corpora 
   - Absence of neutral sentiment - Since it is a binary classification task, demarcation between negative and neutral sentiments is not entirely addressed 

#### PMI 
   ![PMI](images/pmi.png) 
   
## Visualization sample output 
   ![N-Gram Visualization](images/N-Grams.jpg) 

    
