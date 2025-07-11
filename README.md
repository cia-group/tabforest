# tabforest
Predicting the relevance of titles + abstracts from agroforestry studies

Title + Abstract Team Members & Information:

Wendi Zheng (wzheng folder) 
    contact: wendizheng06@gmail.com 

    https://www.linkedin.com/in/wendi-zheng-442588235/

    Completed the Following Tasks, FAQ Below and Contact for Questions: 
        Trained BERT precision model had performance of 0.6977 precision and 0.2655 recall
            - Note: The model was trained on agroforesty data. Therefore, it will predict the relevance of papers to agroforestry 
                    (the '1' label indicates paper is relevant to agroforestry, '0' label indicates irrelevant)
            - To train your own model using your own data for predicting relevance of another type of relevance (e.g. carbon data) you can use the /tabforest/wzheng/BERT_Maximize_Precision.ipynb file. Simply add in your own csv (with TAB column and Label column, TAB including title + abstract info and Label including 1 or 0, 1 for relevant and 0 for irrelevant). Make sure to change the csv name within the script during csv loading step to your csv file's name. Otherwise, name your csv 'TAB.csv'
        Created run_saved_model.ipynb for using trained BERT model to predict custom csv (contact if more explanations are needed)
            - To run predictions on your own csv, go to /tabforest/wzheng/run_saved_model.ipynb
            - Upload your csv under the contents folder, choose BERT as your model and run each cell, following directions
            - Note: 1. you have to create your own csv (eg by downloading your excel sheet as a csv)
                    2. you need to have a column with title + abstract information and name the column 'TAB' or have separate columns with title + abstract information and name them "title" and "abstract" respectively
                    3. you should download the /tabforest/wzheng/run_saved_model.ipynb as an ipynb and run on google collab
        For example of csv format, see TAB_binaryLabel.csv (you need the TAB column and that is it)

