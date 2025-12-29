# Satellite Property Valuation
This project aims to estimate property prices by leveraging both structured housing attributes and satellite imagery. 
We start with Exploratory Data Analysis (EDA) to examine price distributions and assess how factors such as geographic location, built-up area, and room count relate to property value. 
Guided by these insights, tabular model XGBoost was developed.

To enrich the model with visual context, a convolutional neural network based on ResNet18 was trained on satellite images. 
This relatively lightweight backbone was selected to balance performance with computational constraints while still learning relevant spatial patterns. 
To improve transparency, Grad-CAM was employed to highlight image regions that most strongly influenced the CNN's predictions.

In the final stage, a fusion framework was constructed by combining outputs from the tabular XGBoost model and the image-based CNN. 
These predictions were stacked and fed into a meta-learner, yielding better results than either modality alone. 
Overall, the multimodal setup illustrates how integrating numerical data with visual information enhances both accuracy and interpretability in property valuation tasks.

## Dataset
Because the dataset is too large for direct GitHub hosting, it must be downloaded separately.
data set URL:
**Train dataset:**
https://onedrive.live.com/:x:/g/personal/8CF6803ADF7941C3/IQBue1q4w4TETL_7xWMGhcD_AejALtdsXTBejVUjRA9qeM8?resid=8CF6803ADF7941C3!sb85a7b6e84c34cc4bffbc5630685c0ff&ithint=file%2Cxlsx&e=kWdglC&migratedtospo=true&redeem=aHR0cHM6Ly8xZHJ2Lm1zL3gvYy84Y2Y2ODAzYWRmNzk0MWMzL0lRQnVlMXE0dzRURVRMXzd4V01HaGNEX0FlakFMdGRzWFRCZWpWVWpSQTlxZU04P2U9a1dkZ2xD
**Train dataset:**
https://onedrive.live.com/:x:/g/personal/8CF6803ADF7941C3/IQAwCVfSggmjQ4DJH51zJK-tARwRQWE9fl0bPlwo1mRF2PQ?resid=8CF6803ADF7941C3!sd2570930098243a380c91f9d7324afad&ithint=file%2Cxlsx&e=h3frFB&migratedtospo=true&redeem=aHR0cHM6Ly8xZHJ2Lm1zL3gvYy84Y2Y2ODAzYWRmNzk0MWMzL0lRQXdDVmZTZ2dtalE0REpINTF6SkstdEFSd1JRV0U5ZmwwYlBsd28xbVJGMlBRP2U9aDNmckZC

## Structure:
```text
data/
├── images/
│   ├── train/
│   └── test/
├── train.csv
└── test.csv
