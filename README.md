<h1>CNN_LSTM Soil Moisture Prediction</h1>

This repository contains a research project focused on predicting soil moisture using satellite images and a hybrid deep learning model combining Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks. The goal is to process GeoTIFF files containing soil moisture data, prepare the data for training, and build an effective predictive model to forecast soil moisture values.</br> 

<i>Members : Nitesh Gautam, Shishir Chaulagain, Argaj Paudel, Manoj Lamichhane.</i></br> 

<h3>Overview:</h3>
This project leverages satellite images in GeoTIFF format to create a data pipeline and implement a CNN-LSTM model:</br> 
•	CNN: Extracts spatial features from soil moisture images.</br> 
•	LSTM: Captures temporal patterns to predict soil moisture for upcoming days.</br> 
The model combines these techniques to create an efficient and accurate prediction framework.</br> 


<h3>Requirements:</h3>
The following Python libraries are required to run the code:</br> 
•	os: For file handling and directory operations.</br> 
•	rasterio: To read and process GeoTIFF files.</br> 
•	numpy: For numerical computations.</br> 
•	matplotlib: To visualize data and results.</br> 
•	seaborn: For enhanced data visualization.</br> 
•	random: For generating random operations when required.</br> </br> 

o	To install these libraries, run:</br> 
<li>pip install rasterio numpy matplotlib seaborn</li></br> 

<h3>Data Description:</h3>
Input Data:</br> 
GeoTIFF files representing soil moisture values collected daily for the year 2022.</br> 
Directory Structure:</br> 
Place all GeoTIFF files in a folder named 2022_geotiffs within the repository directory.</br> 
Summary:</br> 
•	Total GeoTIFF files: 364</br> 
•	Data dimensions: The output shape is (number of files, height, width), representing the combined spatial and temporal data.</br> 



<h3>Implementation Steps:</h3>

1. Data Loading</br> 
•	Use the rasterio Python library to load GeoTIFF files.</br> 
•	Extract each GeoTIFF as a 2D NumPy array.</br> 
•	Handle missing values (NaN) by replacing them with 0.0. This ensures the model does not encounter invalid data during training.</br> 

3. Data Preprocessing</br> 
•	Combine all the individual 2D arrays from the GeoTIFF files into a single 3D NumPy array. The final structure will be: (number of files, image height, image width).</br> 
  Example: (364, 919, 1792) where 364 represents the days of the year.</br> 
•	Save this array for efficient reuse during the training phase.</br> 

4. Model Development</br> 
•	CNN (Convolutional Neural Network):</br> 
Extract spatial features from the soil moisture maps. Each GeoTIFF file represents a spatial distribution of soil moisture values, and CNN layers capture the spatial patterns effectively.</br> 
•	LSTM (Long Short-Term Memory):</br> 
Process temporal sequences of soil moisture maps. LSTM layers are designed for sequential data and help predict future values based on historical patterns.</br> 
•	Combine CNN and LSTM layers into a hybrid model that learns both spatial and temporal dependencies.</br> 

5. Prediction</br> 
•	Train the hybrid CNN-LSTM model using the preprocessed data.</br> 
•	Evaluate the model’s performance using metrics such as RMSE, MAE, or accuracy.</br> 
•	Use the trained model to predict soil moisture for future dates by inputting sequences of past GeoTIFF data.</br> 
