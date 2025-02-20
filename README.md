# Annual-Energy-Consumption-Prediction-Application-using-Machine-Learning-
This project is an energy prediction application which predicts annual energy consumption in KW/H after getting the user inputs from Homeowners/Renters. The model was trained on using EPC(Energy Performance Certificates) of Domestic Buildings Dataset of England and Wales. 

## 1. Problem Statement:
CO2 Emission and Energy Consumption are one of the major factors affecting the environment. As a homeowner or a renter it is really hard to get an estimate of what an annual energy consumption of their home will be like. Also apart from that it would be good if the user will get any suggestions to reduce their annual energy consumption which will help to reduce the amount of bills they are paying. Also , in this time of climate change it is essential to know the CO2 Emission from your home/building which is a major contributing factor of the environemental issues.

This project will be the attempt to predict/estimate the annual energy(KW/H) and CO2 emission of a residential building using the models trained on real world dataset, which I hope will help the end users find it useful to get valuable insights of their own homes and how to improve their energy consumption

## 2. Dataset :
The dataset we are using for this project is called `Energy Performance Certificate(EPC)` dataset from the website of the UK's official Department for Levelling Up, Housing & Communities. This is an open data published by the UK Government and had published the data from 2008 Oct 1, and are updated monthly. The data can be downloaded from here: https://epc.opendatacommunities.org

### 2.1 Dataset Description
This is a very big dataset which contains the Energy Performance data of each residential buildings in the England and Wales, and we have the option to download the data of each towns from the England and Wales.
The data are of two types :
* Domestic EPC (Residential Buildings and Houses)
* Non-Domestic EPC (Non-Residential Buildings, Offices, Businesses etc.)

Since we are focusing on Residential Buildings we are using the Domestic EPCs .

### 2.2 What is inside the Dataset?

The EPC dataset is a very big and comprehensive dataset which contains top to bottom details of a building , the dataset comes with a glossary of what's inside the data , which is a long list of details I will put here:


#### Glossary: Domestic EPCs
The glossary contains the what each column is and their respective column names and data types
The glossary can be found inside this notebook: https://github.com/mroshan454/Annual-Energy-Consumption-Prediction-Application-using-Machine-Learning-/blob/main/Energy_Prediction.ipynb
