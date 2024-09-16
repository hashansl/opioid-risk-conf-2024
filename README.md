Here’s a clean and clear README file for your opioid overdose prediction project:

---

# Opioid Overdose Prediction Using Persistence Images

This project aims to predict high-risk areas for opioid overdose using socioeconomic and geospatial data. The analysis is based on Topological Data Analysis (TDA) techniques to generate persistence images and classify high-risk areas using machine learning models.

## Project Overview

This repository contains the code to:
- Process Social Vulnerability Index (SVI) data.
- Generate persistence images from adjacency complexes.
- Combine features for training.
- Train models to classify high-risk opioid overdose areas.

## Data

Before running any scripts, you need to download the required datasets:

1. **SVI Data**: Download the Social Vulnerability Index (SVI) data for the desired year from the CDC website and place it in the `raw_data` folder.
   
2. **Opioid Overdose Data**: Download opioid overdose data as a CSV file and store it in the `raw_data` folder.

---

## Data Processing Steps

### 1. **SVI Data Cleaning**
   
   - Use the script `process_svi_data_census_minmax_scaled.py` to clean and scale the SVI data.
   - Ensure that the SVI census file path is correctly specified in the script.
   - This script will handle missing values and perform min-max scaling on the SVI data.

### 2. **Generate Persistence Images**
   
   - Run `adjacency_complex_census_npy_generation_h0h1.py` to generate persistence images for each variable in the dataset.
   - The output will be saved as `.npy` files, with each variable stored in a separate folder.

### 3. **Combine Persistence Images**
   
   - Use the script `adjacency_combining_features.py` to combine the `.npy` files (representing different variables) into single files for each county.

### 4. **Annotation Filtering**
   
   - Run the Jupyter notebook `annotation_percentile_us.ipynb` to create the annotations for the generated persistence images.
   - All variables must generate persistence images to be included in the annotation.

---

## Model Training

Once the data is prepared and annotations are created, you can train the model:

### 1. **Training the Model**

   - Use the script `train.py` to start the training process.
   - Adjust any parameters in the script as needed to fine-tune the training process.

---

## Results

This project uses persistence images generated from the socioeconomic and geospatial data to predict opioid overdose risk areas, with a focus on classifying high-risk regions. The trained model can provide valuable insights into the spatial distribution of overdose risks across counties.


---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Contact

For questions or further information, please contact hfernand@vols.utk.edu.

---

This README provides clear instructions on data preparation, processing, and model training for the opioid overdose prediction task.