This project consists of three stages:
1. EDA
2. Feature Engineering
3. Modeling

Each stage is implemented in a separated jyputer notebook. I used *colab.google.com* to implement all stages.
For a good experience, I recommend you to test this project using *colab.google.com*.

You need to get a username and token form kaggle and inject them in the notbooks to be able to download the contest data.
I used googel drive to store and read output data from different stages.

If you want to use colab.google.com to run this project, make sure you have this folder structure in your google driver(Colab Notebooks):

.
+-- models

+-- submissioms

+-- data

|    +-- prep

+-- modeling.ipynb

+-- feature_engineering.ipynb

+-- eda.ipynb

If you want to use you machine to run this project, make sure you have the prvious folder structure, but you need 
to change to value of the global variables(model_path, data_path, sub_path) in each notbook to suit the new location in your local machine.



**EDA**:

In this stage we explore the data, clean it and perform some prepocessing to textual data.
input: contest data
output: cleaned, preprocessed contest data

**Feature Engineering**:

In this stage we generate all possible features from the data
input: cleaned, preprocessed contest data
output: train, validation and test set combianed in one grid

**Modeling**:

In this stage, we build 6 base models(lightGBM, Catboost, LinearRegression, LassoRegression, NerualNetwork, XGBoost)
Then we stack them using Linear Regression meta model.
To test stage, you need to generate the training set (grid_full.pkl) from the previous stage.
You don't need to train the base models (I uploaded them for you)
Generating meta features will take so much time (~12) hours. I don't recommend you to go through it. 
input: training gird
output: trained base models, meta feature(training, validation, test)
