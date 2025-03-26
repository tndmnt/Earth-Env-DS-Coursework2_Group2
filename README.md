# Earth-Env-DS-Coursework2_Group2

This repository contains the coursework for Group 2 in the Earth and Environmental Data Science course. The project focuses on analyzing and predicting soil moisture levels using various data science techniques and models.

## Project Structure

The repository is organized as follows:

- **Notebooks**:
  - `01_Intro_to_Preprocessing.ipynb`: Introduction to data preprocessing techniques applied to the dataset.
  - `02_EDA.ipynb`: Exploratory Data Analysis to understand data distributions and relationships.
  - `03_External_Dataset.ipynb`: Integration and analysis of external datasets relevant to the study.
  - `04_Model_Prophet.ipynb`: Implementation of the Prophet model for time series forecasting.
  - `05_Model_XGBoost.ipynb`: Application of the XGBoost model for predictive analysis.
  - `06_XESMF_XGBoost_Predicted.ipynb`: Spatial analysis using XESMF on XGBoost predictions.
  - `07_Predicted_Soil_Moisture_2025_2080.ipynb`: Projections of soil moisture levels from 2025 to 2080.
  - `08_References.ipynb`: Compilation of references and resources used throughout the project.

- **Data Folders**:
  - `raw_data/`: Contains the original datasets used for analysis.
  - `raw_external_data/`: Includes external datasets incorporated into the project.

- **Figures**:
  - `figures/`: Directory for storing visualizations and figures generated during analysis.

- **Models**:
  - `model (unused)/`: Contains models that were explored but not utilized in the final analysis.

- **Environment Configuration**:
  - `environment.yml`: YAML file specifying the conda environment configuration for reproducing the computational environment.

- **Data Files**:
  - `merged_dataset.nc`: NetCDF file of the merged dataset used in the analysis.
  - `preprocessed_merged_dataset.nc`: NetCDF file of the preprocessed merged dataset.
  - `preprocessed_soil_ds.nc`: NetCDF file of the preprocessed soil dataset.
  - `xgboost_predictions_fixed.nc`: NetCDF file containing XGBoost model predictions.
  - `predicted_soil_moisture_2025_2080.nc`: NetCDF file with projected soil moisture data from 2025 to 2080.

## Getting Started

To set up the environment and run the notebooks:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/tndmnt/Earth-Env-DS-Coursework2_Group2.git
   ```

2. **Create the Conda Environment**:
   Navigate to the repository directory and create the environment using the provided `environment.yml` file:
   ```bash
   conda env create -f environment.yml
   ```

3. **Activate the Environment**:
   ```bash
   conda activate earth-env-ds
   ```

4. **Launch Jupyter Notebook**:
   Start the Jupyter Notebook server to access and run the notebooks:
   ```bash
   jupyter notebook
   ```

## Data Sources

The datasets used in this project include both raw data collected from various sources and external datasets integrated to enhance the analysis. Detailed information about each dataset, including acquisition methods and preprocessing steps, is documented within the respective notebooks.

## Results

The analysis culminates in the projection of soil moisture levels from 2025 to 2080, providing insights into potential future trends. These projections are visualized and discussed in `07_Predicted_Soil_Moisture_2025_2080.ipynb`.

## References

A comprehensive list of references and resources utilized throughout the project is available in `08_References.ipynb`.

## Contributors

This project was developed by Group 2 as part of the Earth and Environmental Data Science coursework.
