# Brain Tumor Segmentation Using Deep Neural Networks

## Description
This project presents the use of deep learning and image processing techniques for the segmentation of tumors into different regions using a W-Net model architecture for tumor segmentation.

## 1. Dataset

1. Data released with multimodal brain tumor segmentation challenge by Medical Image Computing and Computer Assisted Intervention (MICCAI) is used for training.
2. 3D dataset consists of pre surgical MRI scans of 210 High-Grade Glioma (HGG) patients and 75 Low-Grade Glioma (LGG). However, only HGGs are used
3. The dataset has 4 modalities- T1-weighted (T1w), post-contrast T1-weighted (T1ce), T2-weighted (T2), Fluid Attenuated Inversion Recovery (FLAIR) and GT.
4. These images are manually segmented by expert neuroradiologist labelled as as enhancing tumor (label 4), peritumoral edema (label 2), and the core (label 1)

## 2. Pre-Processing

1. Each 3D volume of 4 has a size of 240×240×155 for all modalities and ground truth.
2. After slicing we will get 155 2D images of size 240×240 size.
3. Only 90 slices (slice no 30 to slice no 120) from each volume are selected.
4. These slices cropped to  192×192 (Background noise)
5. 18,900 2D images of each MRI modality. (210 HGG data × 90 slices = 18900)
6. Total images for all modalities will become 75,600. (210 HGG patient's data × 90 slices of each modality × 4 modalities = 75,600 2D images)

## 3. Training

The models were trained using W-Net model architecture for tumor segmentation.

## 4. Experimentation

1. HGG consists of data of 210 patients. The models were trained in batches of 50 patients.
2. Data split into 3:1:1- 60% images for training, 20% images for testing, and 20% for validation.
3. All the models are trained with batch size-8 and no of epochs-30.

## 5. Conclusion

1. Several Deep Learning and Image processing techniques were studied in the due course of the project. 
2. We completed research work with current usage of techniques in image preprocessing, image segmentation, common feature extraction and classification recently used were
   analyzed and studied. We choose in total 3 systems-
      
      i. SOBEL + MD-UNET (Dice score-0.9918)
      ii. 2D -VNET (Dice score-0.9947)
      iii. **WNET (Dice score-0.9964)**
3. The output received is of tumor region highlighted into three regions which are edema, enhancing tumor and non enhancing tumor. The dice score of
    99.64% was achieved
