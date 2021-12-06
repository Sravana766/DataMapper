# Tagup Technical Challenge
This is the solution to the Technical Callenge for the Data Engineer role at Tagup

# DataMapper

## Description
DataMapper imports data from a SQL database and maps it into arrays. This program was written in Python. The input used in the program is a time series data for all the machines utilized by the company ExampleCo, Inc. 

Features:
* Imports data from a SQL database
* Identifies and removes outliers
* Filters data using moving average filter
* Visualizes data using various plots
* Outputs the data as a Numpy array for further processing
* Saves Numpy array in AWS S3

## Prerequisites
Before you continue, ensure that you have the following installed on your computer:
* Python version 3.0
* Packages: Pandas, Numpy, Scipy, Sqlite3, Matplotlib

## Installation
In order to run the program download the ExampleCo_DataPipeline.ipynb notebook and run the file. For the program a sample data set was used: <a href="https://drive.google.com/file/d/1GejVDBoFFVNprqMeTGnXu8hrYLj4aS4q/view " target="_blank">Sample Data</a>. 

## How it Works
1. Imports the data from the **feat_0** table and imports the *timestamp*, *machine*, and *value* column into a Pandas Dataframe.
2. Analyzes the data for any outliers by computing Z-scores for each sample by using the **Scipy** function *stats.zscore()*.
3. The identified outliers are then removed from the dataset.
4. A Fourier Transform was used using the **Numpy** function *np.fft.fft()* to indetify any additional noise that may be part of the dataset.
5. After identify high frequency noise present in the data, a moving average filter was applied to smooth the function and remove the noise.
6. The newly filtered data is stored into a 3D Numpy array that contains the *timestamp*, *machine*, and the *value* collected. 
7. After creating the Numpy array, it was uploaded to AWS S3

## Credits
To write the program various tutorials and reference pages were used. Here is a list pages used to build the program:
1. <a href="https://towardsdatascience.com/fast-fourier-transform-937926e591cb" target="_blank">Fourier Transform</a>
2. <a href="https://towardsdatascience.com/moving-averages-in-python-16170e20f6c" target="_blank">Moving Averages</a>
4. <a href="https://www.investopedia.com/terms/c/central_limit_theorem.asp" target="_blank">Central Limit Theorem</a>
5. <a href="https://www.investopedia.com/terms/e/empirical-rule.asp" target="_blank">Empirical Rule</a>
6. <a href="https://towardsdatascience.com/ways-to-detect-and-remove-the-outliers-404d16608dba" target="_blank">Removing Outliers</a>
7. <a href="https://www.youtube.com/watch?v=JmrYZPjSDl4" target="_blank">Uploading To S3 Tutorial</a>


