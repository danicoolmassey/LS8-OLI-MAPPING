# LS8-OLI-MAPPING
Mapping of rice growth phases and bare land using Landsat-8 OLI and machine learning algorithms


This is the steps to recreate the mapping. Please change the path of folder accordingly.

Folder SR_output_model_LS8_2018_indramayu_edit contains the results of the classification model

Folder SR-LS8-indramayu-utm contains the images of the classification results from the model

A. Download Data
1. Install Python and GEE login. Please refer to https://developers.google.com/earth-engine/python_install

2. Download data using dl_SR_LS8_path_row_utm_bands_batch_2018.py and dl_SR_LS8_path_row_utm_FMASK_batch_2018.py

3. Downloading LS8 values based on CCTV locations dl_SR_LS8_cctv_complete_utm.py and dl_SR_LS8_cctv_fmask_complete_utm.py 

4. Download CCTV images from http://katam.litbang.pertanian.go.id/

B. Building the model
1. Synchronize with according images and its interpretations of rice growth stages and bare land.

2. Create tabulation based CCTV images and LS8 value. Erase all FMASK<>322

3. Building the model using several classiers and tuning it using SR_Landsat8_ML_2018_indramayu_EDIT.R

4. Recap the classifier's result using recap_SR_output_model_LS8_2018_indramayu_edit.R

5. Copy the best model for eah classifier into MODEL folder

6. Run SR_Landsat8_indramayu_ML_classify1.R for classifying.R

7. Run SR_Landsat8_indramayu_ML_mask_clip_region_paddy_utm1.R for mergeing into one image

8. Run SR_Landsat8_indramayu_ML_change_detection_paddy_utm1.R for detecting change classes

8. Run SR_Landsat8_indramayu_ML_change_detection_paddy_utm_reclass1.R for reclass of change detection

