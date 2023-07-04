# Energy Demand Prediction Project

This project aims to predict electrictiy demand of at least on building type from the [Building Data Genome Project 2](https://github.com/buds-lab/building-data-genome-project-2) using a Gaussian Process regression model. For each of the building types an own model was trained based on the building and metering timeseries which show the higehst correlation with the electricity demand of our target building. 



## Project Structure

The project is organized into the following notebooks:

1. [Spearmans Correlation.ipynb](notebooks/Spearmans Correlation.ipynb): This notebook computes the Spearman's rank correlations between the target timseries and all other meterind timeseries in our dataset. This is computationally expensive and takes quite some time to finish computation. The correlation matrices for each building can be found in data/correlations

2. [Energy Demand Prediction.ipynb](notebooks/Energy Demand Prediction.ipynb): This notebook performs the actual electricity demand prediction using a Gaussian Process Regression model. It utilizes the n-highest correlated timeseries and applies the regression model to make predictions for the next steps based on the values of the other timeseries. The predictions can be found in data/predictions  

3. [Results and Errors.ipynb](notebooks/Results an Errors.ipynb): This notebook is for presenting the results in form of plots and shows the errors. A short comment on the performance of the model and a small discussion is given in the end.

## Requirements

To run the notebooks and reproduce the results, ensure you have the following dependencies installed:

- python 3.7 or higher
- numPy
- pandas
- scikit-learn
- scipy.stats
- matplotlib
- GPy
- tqdm
- pickle

There might be some problems with numpy and the GPy library. In case you run into problems, try the provided pip install --upgrade commands. Try to update numpy before GPy, as GPy will load the numpy version it needs to work. Also consider this during the imports. 

## Usage

1. Clone the repository:

   ```shell
   git clone https://github.com/mdeppner/energy_demand_prediction_for_buildings
