# Tagup Technical Challenge
This is the solution to the Technical Callenge for the Data Engineer role at Tagup

# 

## Description
The objective of the program is to import data from a SQL database and map it into arrays. The input used in the program is a time series data for all the machines utilized by the company ExampleCo, Inc. 

The program performs the following features:
* Imports data from a SQL database
* Identifies and removes outliers
* Filters data using moving mean filter
* Visualizes data using various plots
* Outputs the data as a Numpy array for further processing

## Prerequisites
Before you continue, ensure that you have the following installed on your computer:
* Python version 3.0
* Packages: Pandas, Numpy, Scipy, Sqlite3, Matplotlib

## Installation
In order to run the program download the ExampleCo_DataPipeline.ipynb notebook and run the file. For the program a sample data set was used: . 

## How it Works
1. Imports the data from the **feat_0** table and imports the *timestamp*, *machine*, and *value* column into a Pandas Dataframe.
2. Analyzes the data for any outliers by computing Z-scores for each sample by using the **Scipy** function *stats.zscore()*.
3. The identified outliers are then removed from the dataset.
4. A Fourier Transform was used using the **Numpy** function *np.fft.fft()* to indetify any additional noise that may be part of the dataset.
5. After identify high frequency noise present in the data, a moving mean filter was applied to smooth the function and remove the noise.
6. The newly filtered data is stored into a 3D Numpy array that contains the *timestamp*, *machine*, and the *value* collected. 

## Credits
To write the program various tutorials and reference pages were used. Here is a list pages used to build the program:
1. <a href="https://www.google.com/" target="_blank">Google</a>
