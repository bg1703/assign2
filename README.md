## File Type Identifiaction
Method used The steps used for building the required model are as follows
1. Dataset building :
We are given a dataset of C++, Java, Groovy, JavaScript, Python, XML, JSON, and YAML syntaxes in a different folder. First of all we have to organize files into a single dataset in form of dataframe. Dataframe is used to store path followed to access a particular file and context of file by traversing every possible paths. We have only those files which are utf-8 encoded as the can be decoded into text and will remove any files that are not UTF-8 encoded. As those files cannot be decode and their content is not accessible.
Next action is to identify the language possibly used in file with the help of its extension. Language.josn file is used in the task as it contains the names of languages in which file can be classified and this possible extension. For example Groovy file can have four (.groovy, .gvy, .gy, .gsh) possible extensions. Now our dataset is ready for the next step and it contains context, path, extension and possible language for the file in it and start building the mode by splitting our dataset into test and train sets.
2. Pre-Processing
In this step we would like pre-process out dataset by converting it into a structured data form an unstructured data. This has been achieved in two steps
      1) We will remove the word that are made of single characters and multiple same characters as they might be used as variable in the language 
      2) Next step is to do tokenization i.e. splitting an entire text document into smaller units, such as individual words or terms because in text the words are the         features. To apply tokenization we have used tfidfvectorizer.
TF-IDF stands for Term Frequency Inverse Document Frequency. This algorithm is used to tokenize the document into unigram, bigram, trigram and match those values to numerical value which
is used to represent it. This is achieved with the help of regular expressions. The values generate are also normalized.
Now we got out data into shape we needed.
3. Training:
We want to choose the best model get the best result for out testing dataset as no model is perfect for all the datasets. So we will apply pipeline to explore different models and then we will apply gird search to find the best model for out dataset.
Models used for training are randomforest classier, MLPClassifier and LogisticRegression. Pipeline is be used to chain multiple estimators into one and to assemble several steps that can be cross-validated together while setting different parameters. GridSearchCV is used for exhaustive search over specified parameter values for an estimator.
4. Testing:
To get the best model we have sort the models on the basis of their score and predicted the values of our testing data.
further we have printed the confusion matrix for the analysis of our final results.
Further to extend the model we can do is Parameters tuning of grid search to optimize models hyperparameters. We can also apply deep learning models like Convolutional Neural Networks , Long Short-Term Memory Networks and Recurrent Neural Networks etc. We can also explore models used for classification in library like TensorFlow etc.
The method is scalable, automated and industrially scalable. This method can be extended to wide range of languages by adding file type and their extensions to language.json file.
