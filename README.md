# **Predicting Liquidation Volumes**

Machine learning prediction of extreme cryptocurrency liquidation volume using market microstructure and sentiment features.

MSc Machine Learning and Data Science dissertation (MATH70105), Imperial College London. \
**Supervised by:** Dr Mikko S. Pakkanen.\
**Author:** Saad Sharif

## **Overview**

This project models forced liquidation volume on cryptocurrency perpetual futures markets. Three model families are compared against a naive baseline:

- Tweedie regression (Generalised Linear Model)
- LSTM (Recurrent Neural Network)
- XGBoost (Gradient Boosted Trees)

## **Data sources:**
**Amberdata API Features Groups:** Coin, Price and Volume, Order Book, Open Interest, Funding and Positioning\
**Santiment API Features Groups:** On-chain activity, Social\
**Timeframe:** 6TH August 2025 - 9th May 2025\
**Cryptocurrencies:** BTC, ETH, XRP, DOGE,ADA, BCH, LINK, LTC, AVAX

## **Repository Structure:**
**1. Data Extraction:** Extract the data from the source APIs into several .csv and .parquet files per coin and feature group\
**2. Data Consolidation:** Reads the .parquet files and merges them into one large dataset based on coin and timestamp\
**3. Data Imputation:** Handles missing values in the data and engineers additional features\
**4. Data Exploration:** Visualises the distribution of Liquidation volumes\
**5. Hyperparameter Tuning:** Tune the Hyperparameters based on the full feature set\ 
**6. Data Modelling:** Machine Learning model training and testing on full feature set and ablation scripts\
**7. Evaluation - Full Model and Ablation Study:** Consolidate evaluation metrics from Modelling scripts for comparison\
**8. Evaluation - Per Coin Analysis:** Breakdown of results by Cryptocurrency to assess performancy by coin

## **Data Availability:**
No datasets are included in this repository due to file sizes being too large for Github.\
In order to reproduce these results, Amberdata and Santiment API credentials will be required for the notebooks in the 1. Data Extraction folder.

## **Order of Steps to Reproduce Results:**
1. Execute the five notebooks in the 1. Data Extraction folder
2. Execute the Data Consolidation notebook in 2. Data Consolidation folder to produce crypto_master_dataset
3. Execute the Data Imputation notebook in 3. Data Imputation folder to produce crypto_master_dataset_imputed
4. Optionally execute the Distribution_of_Liquidation_volume notebook in 4. Data Imputation folder to create exploratory visualisations
5. Execute the Machine Learning Models-Tuning notebook in 5. Hyperparameter Tuning folder to obtain the hyperparameters for the models
6. Manually copy the hyperparameters into the 10 modelling notebooks in 6. Data Modelling folder and execute (includes full and ablation models)
7. Execute the Evaluation_Metrics_Results notebook in 7. Evaluation - Full Model and Ablation Study (using outputs of modelling notebooks in 5. Data Modelling folder)
8. Execute Evaluation_Metrics_Results_Per_Coin notebook in 8. Evaluation - Per Coin Analysis folder (using outputs of Machine Learning Models_Horizon12-Executed-Per_Coin_Results notebook from 5. Modelling folder)

