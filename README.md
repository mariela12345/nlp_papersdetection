# nlp_papersdetection
1. Clone the repository
2. Execute code from the notebook
3. The trained models are uploaded in this same report

# Task1
1. Run first the preprocessing steps: <br/>
2. Execute the similarity functions for filter out the articles that do not employ deep learning techniques: <br/>
2.1. First approach () obtain the articles that only use deep learning using cosine similarity, obtaining the max value per article and getting the articles with a similarity score threshold of 0.3 <br/>
2.2. Second approach () obtain articles that use only deep learning using cosine similarity but instead of threshold ranking them from high to low similarity scores and filter only 25% of the entire data <br/>
3. Plotting the keywords related to deep learning (bar plots) of both approaches to show the DL techniques employed in the selected articles <br/>

# Task2
1. Performing classification of articles to classify them in text mining, computer vision, both approaches or others.<br/>
2. An initial labeling of data was done (automatic labeling) - run function <br/>
3. First approach: <br/>
3.1. A logistic regression method was employed to perform classification that get the "predicted category" - run function <br/>
3.2. Since the labeled data is imbalanced (both (), others(), text ming(), computer vision()) then SMOTE is applied to augmented the number of "both" labels: run function <br/>
3.3. Once again after SMOTE to tackling imbalance is performed then logistic regression is applied once again reaching: acc:87,prec: ,f1, etc : run function <br/>
3.4 Plots of performance : run <br/>
4. Second approach:<br/>
4.1. A DistilBERT language model was used (it is less resource comsuption compared to a bigger model BERT) <br/>
4.2. DistilBERT was trained with the labeled dataset achieving 97% acc, pre , f1, recall, (better performance), the already trained model uploaded in repo : ...zip <br/>
4.3 Unzip the trained model (run function) and run an inference to test the classification performance from a set of samples : run function <br/>
4.4. Test model performance using the metrics and plots: run function ... , run function ...<br/>
   
# Task3
1. Report of the used approaches in task2 classification : a matching ..... <br/>
3. For getting the related topics after classification task : run function <br/>
4. For getting the plots of related topics : run function <br/>
