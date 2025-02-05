# RRNN-RESPEL (Hazardous Waste Generator Registry) (English)
For the prediction of the generation of electrical and electronic waste (2021-2025) according to its behavior recorded by IDEAM in the Bases Animizadas (transformed databases) (2015-2020); the research is carried out in 4 steps.

1. Data understanding, field mapping, identification of the main COL cities and ISIC Codes.
2. Cleaning, filtering and categorization of the anonymized bases (2015-2020) for subsequent use in prediction.
3. Prediction by means of linear regression, by department, municipality and economic activity.
4. Prediction by means of neural network (RRNN), by department and municipality.
5. Understanding of the data by means of graphs.

# SUMMARY
This Python code is designed to perform machine learning tasks using neural networks to predict data based on time series. Below are the functions of each part of the code:

Data Loading (Dataloading):

First, a CSV file named 'DEPARTAMENTO_GrpConsolidado.csv' is loaded using pandas.
A copy of the original data is created.
The 'DEPARTAMENTO' column is removed, and the 'ANIO' column is set as the index, then formatted as a datetime data type and data are sorted by index.
Data Splitting (Datasplitting):

Data are split into training and testing sets based on the number of specified days for training.
Data is further split into inputs and outputs for training and validation models.
Input data is reshaped to be three-dimensional to be processed by the neural network.
Feedforward Neural Network Design, Training, and Prediction (FeedforwardNeuronalNetworkdesign, trainingandpredicting):

A function to create a sequential neural network model consisting of dense layers with 'tanh' activation function, flatten the output, and add a final dense layer.
The model is compiled with the 'mean_absolute_error' loss function and 'Adam' optimization, using mean squared error ('mse') and mean absolute percentage error ('mape') metrics.
The model is trained using the training dataset with a specific number of epochs and batch size defined by 'PASOS', and validated with the validation dataset.
After training, the average 'mse' and 'mape' from all epochs are calculated and added to lists for analysis.
Finally, the validation data is used to make predictions with the trained model.
