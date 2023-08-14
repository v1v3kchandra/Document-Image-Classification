
# Dataset

This repository uses the RVL-CDIP dataset for the task. The dataset can be downloaded using the following links:

- [Images (40 GB)](https://docs.google.com/uc?id=0Bz1dfcnrpXM-MUt4cHNzUEFXcmc&export=download)

After downloading, the dataset is provided in a compressed tar file format that needs to be extracted and uploaded to Google Drive.

# Setup

This project utilizes Google Colab Pro due to the requirements of higher RAM and a T4 GPU for training. To facilitate this setup, the following steps are taken:

1. Import the necessary packages for data extraction:
   
   ```python
   import shutil
2.  Unpack the downloaded tar file:
    ```
    shutil.unpack_archive('/content/drive/MyDrive/rvl-cdip.tar.gz', '/data')    
3.  Install required packages such as `timm` (if not already installed):
    ```bash
    !pip install timm
The extracted data is stored in the `/data` directory within the Google Drive memory. For local systems, the data can be extracted and the path adjusted accordingly.

# Training

To train the ViT model on the document images, run the 'ViT_Document_classification_train.ipynb' notebook. This script saves the model after each training epoch. After training, the model is saved on Google Drive and later loaded for feature extraction.

# Feature Extraction

For feature extraction, execute the `ViT_Document_classification_feature_extraction.ipynb` notebook. This notebook loads the ViT model that was saved during training and extracts features from the images. These features are utilized for training classifiers.

# Saved Weights

The saved ViT model weights can be found in the `weights` folder. These weights are useful for evaluation purposes. To conduct evaluations only, use the loaded models within your evaluation script.
The trained model can be found at this link :https://drive.google.com/file/d/1-RCsEX1euADZhGnV4HtPQt7Aif1RYNJy/view?usp=sharing

For any questions or clarifications, feel free to open an issue or contact us.


