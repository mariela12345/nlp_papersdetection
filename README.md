# NLP papers detection for virology/epidemiology
1. Clone the repository
2. Execute code from the notebook according to instructions/comments
3. The trained models are uploaded in this same report

# Preprocessing   
1. Run first the preprocessing steps with functions suggested <br/>
- The aim was stemming and lemmatization of the text fields (stop words removal, lowercasing, etc) - Abstract, Title, Journal/Book, First Author 
- In "Abstract" some empty values are replaced by unknown
- For other fields (non text) cleaning to put in a specific format/removing some
- Removing DOI, PMCID, NIHMS ID because does not seem relevant and adding noise based of null numbers computation
- Citation in specific format (volume (issue):pagination)

# Feature Engineering
2. Run feature engineering steps with functions suggested for Task2 <br/>
- Create the "text" field merging the Title with Abstract to have all the descriptive information of each paper in one single field
-  Some others features as splitting dates in more than one field. For example created date into created year, create month, created day (not mandatory but could be useful for evaluate trends/seasonality in data, etc)
   
# Task1
## Instructions and guidelines
1. Execute the similarity functions for filter out the articles that do not employ deep learning techniques: run functions suggested in notebook <br/>
1.1. First approach obtain the articles that only use deep learning using cosine similarity, obtaining the max value per article and getting the articles with a similarity score threshold of 0.3 : run functions suggsted  <br/>
1.2. Second approach () obtain articles that use only deep learning using cosine similarity but instead of threshold ranking them from high to low similarity scores and filter only 25% of the entire data: run functions suggested <br/>
2. Plotting the keywords related to deep learning (bar plots) of both approaches to show the DL techniques employed in the selected articles
   
## Solution components
- First approach: Stem-BERT model (Mini-) for embedding sentences and compare with reference words/sentences related to deep learning techniques,cosine similarity and maximum value of cosine computation per article
- Second approach: Using the same sentence embedding model (stem-BERT type), comparing also with deep learning methods words/sentences, after cosine similarity a ranking of the top articles that match (25% whole data) 
## Notes
- Second approach seems better obtaining a more number of articles that might follow deep learning techniques. A fast checking looking into the bar charts, second approach captures more deep learning keywords/articles.
- First approach capture less number of articles which does not seem that accurate comparing to the whole dataset.


# Task2
## Instructions and guidelines
1. Performing classification of articles to classify them in text mining, computer vision, both approaches or others.<br/>
2. An initial labeling of data was done (automatic labeling) - run function suggested <br/>
3. First approach: <br/>
3.1. A logistic regression method was employed to perform classification that get the "predicted category" - run function <br/>
3.2. Since the labeled data is imbalanced (both (less privileged), others, text ming, computer vision) then SMOTE is applied to augmented the number of "both" labels: run function <br/>
3.3. Once again after SMOTE to tackling imbalance is performed then logistic regression is applied once again reaching: acc:87,prec: ,f1, etc : run function suggested <br/>
3.4 Plots of performance : run functions suggested <br/>
4. Second approach:<br/>
4.1. A DistilBERT language model was used (it is less resource comsuption compared to a bigger model BERT) <br/>
4.2. DistilBERT was trained with the labeled dataset achieving 97% acc, pre , f1, recall, (better performance), the already trained model uploaded in repo <br/>
4.3 Unzip the trained model (run function) and run an inference to test the classification performance from a set of samples: run functions suggested <br/>
4.4. Test model performance using the metrics and plots: run functions suggested.<br/>
## Solution components
- Initial automatic labeling which is a label process based on keywords related to text mining, computer vision, both approaches keywords including multimodal & crossmodal techniques, others (generative ai, llms, etc)
- Component first approach: A SMOTE method to tackle imbalance (augmented more data of less privileged class - both),balanced data after SMOTE,a logistic regression model for classify categories (training & evaluation), reports/metrics
- Component second approach: Balanced data with SMOTE method, A DistiBERT model trained with the labeled dataset (train and evaluation), a trained DistilBERT method for inference of sample for online classification, metrics and charts

# Task3
## Instructions and guidelines
1. Report of the used approaches in task2 classification : a matching function created <br/>
3. For getting the related topics after classification task : run function suggested <br/>
4. For getting the plots of related topics : run function suggested <br/>
## Solution components
- Component 1: A matching method to identfy the subtopics of each relevant articles that use deep learning techniques: vectorization of text and apply cosine similarity to find the subtopics/methods after clasiffication
- Component 2: Bar charts that highlighted the top subtopics by each classified label (text mining, computer vision, both and others) and a global bar chart of all classified articles.

# Q & A
1. Which NLP tecniques for filtering papers were used?
   - Stem-BERT for sentences embeddings along with cosine similarity and max value of those/top ranking ones that match the articles following DL methods
3. Why is more effective than keywords-based filtering? (pros)
   - Using a model made for embeddings is capable to capture more smiliraties than simple filtering due to vectorize representations can capture more accurate similarities in meaning with reference DL techniques
5. What are the resultant dataset statistics for task1 and task2
   - Statistics for task 1: similarity scores after cosine similarities and max values/top ranking values also visual statistics as bar charts
   - Statistics for task 2: After training the DistilBERT/Logistic regression to measure performance using accuracy, precision, recall, f1 score and confusion matrices. For SMOTE method: resultant amount of balance data per class/label.
   
