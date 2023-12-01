# MM-model
Files and Folders:
* alpha_image - image needed to create the images data
* csv - contains training csv data
* csv2 - contains testing csv data
* gojek - that contains parquet data for pre-processing (empty due to size)
* images - contains training image data
* images2 - contains testing image data
* locations - contains unique locations for regions. (intermediary output for 'preprocessing.ipynb')
* map - contains map data needed for notebooks
* micro - contains training micro csv data
* micro2 - contains testing micro csv data
* weights - contains weights for models in 'main_models.ipynb'
* main_models.ipynb - contains the main models
* preprocessing.ipynb - contains the preprocessing codes
* other_models.ipynb - contains other models for comparison

## Pre-processing
pre-processing.ipynb converts gojek demand and driver log parquet data into image format, csv format and micro format 

(run once for training dataset and once again for testing dataset):
* Image
  * Creates images for all regions
  * Ensure it saves into 'image' folder for training dataset and 'image2' for testing dataset
* CSV
  * Creates temporal csv data for all regions in select_regions = [myregions]
  * Ensure that the holiday dates for the month are entered properly in the code (search for the #holiday hashtag)
  * Ensure it saves into 'csv' folder for training dataset and 'csv2' for testing dataset
* Micro
  * Creates micro csv data for all regions in select_regions = [myregions] (have to set again, separately from the above CSV portion)
  * Contains 3 cells of codes
    * First cell gets all unique locations in the region and saves it as a json file. This cell searches the first 50 fifteen minute intervals for the locations.
      Should be enough to get all unique locations. Consider adjusting the code to search for more data, although should not be needed.
    * Second cell loads the unique locations json file, created in the first cell, to be used in the third cell. Adjust where needed.
    * Third cell creates the micro csv data.
    * Ensure it saves into 'micro' folder for training dataset and 'micro2' for testing dataset

## Main_model
Run all codes in the notebook.

Results can be viewed in the final cell.

Results for each model are output-ed in two rows. 
* The first row is the result of the model that is trained without loading the best weights from validation. (Risks overfitting)
* Second row is the result of the model with the best weights loaded from validation. 

## Other_models

'csv' folder contains training csv data

'csv2' folder contains testing csv data

'images' folder contains training image data

'images' folder contains testing image data

'micro' and 'micro2' folders are missing
