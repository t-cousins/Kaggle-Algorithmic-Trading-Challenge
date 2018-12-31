I thought it would be interesting to analyse the data from this, now closed, 2011 [Kaggle competition](https://www.kaggle.com/c/AlgorithmicTradingChallenge/).

The aim was to develop a model to predict the short term response of a limit-order book to a liquidity shock.

I still have a lot more work to do on it but the jupyter notebook chronicles my attempts thus far.

I explored the data and developed models in AWS using S3 storage and SageMaker. S3 is treated as the true repository of data whereas local instances are just used for temporary storage.

You should begin by creating the following folder structure in your S3 bucket:

* **/data**: this is where training and testing data are stored in addition to the various encodings required for different models. Download the competition data set called *training.csv* and store it in this directory under the name *kaggle_data.csv*.

* **/models**: serialised models are stored here with the format *modelName_predict.model*.

* **/predictions**: prediction templates are stored here alongside predictions from each model in the format *modelName_predict.csv*

* **/testing**: errors for each individual price for each prediction are stored here for later analysis in the format *errors_modelName_predict.csv*

Full setup details are included in the notebook.

The notebook is best rendered in the browser using nbviewer at this [link](https://nbviewer.jupyter.org/github/t-cousins/Kaggle-Algorithmic-Trading-Challenge/blob/master/Algorithmic_Trading_Challenge.ipynb) rather than GitHub.