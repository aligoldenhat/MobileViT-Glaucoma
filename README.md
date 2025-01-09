# Glaucoma Detection with MobileViT and cdr

I Implemented a Glaucoma detection model using the MobileViT architecture, trained on the ORIGA dataset.

## Model Architecture
The model is based on the MobileViT architecture, Key components include:

- The model uses the pre-trained `apple/mobilevit-small` as its backbone
- unfreeze the final MobileViT encoder layer and its last convolutional layer for fine-tuning
- A global average pooling layer is applied to the feature maps outputted by MobileViT
- The classifier takes the pooled features and cdr (cup-to-disc ratio)
  - First layer: 640 + 1 input features (640 from MobileViT, 1 for `cdr`)
  - Second layer: 256 input features, 2 output features

## Dataset
The ORIGA dataset is used for training and validation. It can be downloaded from Kaggle:
https://www.kaggle.com/arnavjain1/glaucoma-datasets
