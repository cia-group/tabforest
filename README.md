# tabforest
Predicting the relevance of titles + abstracts from agroforestry studies

Title + Abstract Team Members & Information:

Laura Vaiurus (Linear Model + Mini Bert)
    contact: 

    https://www.linkedin.com/in/lauravairus/

    * Linear (naive bayes) model had performance of 0.81 recall and 0.33 precision.
    * Mini Bert model had performance of 0.54 recall and 0.53 precision.


Alyssa Wu (SPECTER 1 layer + SPECTER 3 layer models)
    contact: zjwualyssa@gmail.com

    https://www.linkedin.com/in/zjwualyssa/

    * Trained SPECTER-1Layer model had performance of 0.770	recall and 0.331 precision.
    * Trained SPECTER-3Layer model had performance of 0.956 recall and 0.222 precision.

Wendi Zheng (wzheng folder) 

    https://www.linkedin.com/in/wendi-zheng-442588235/

    Completed the Following Tasks: 
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

TO USE ANY OF THE MODELS CREATED...
    1. Download the /tabforest/run_model.ipynb as an ipynb and run on Google Colab.
    2. Upload your own csv with TAB column (including title + abstract info) and Label column of 1s and 0s (1 for relevant and 0 for irrelevant) to Google Colab.
    3. Follow the intstructions in the Colab notebook. 

