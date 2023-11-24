# Transfer learning of medical images for White Blood Cell classification task.

The objective of this project seeks to evaluate the effectiveness of applying transfer learning to the task of developing a classification system capable of differentiating between five classes of WBC: basophil, eosinophil, lymphocyte, monocyte, and neutrophil. 

Images from the Camelyon16 and pRCC (papillary renal cell carcinoma) datasets as well as additional mask information from WBC dataset will be used to pretrain a ResNet-18 model.

WBC1, 10, 50, 100 denote proportion of original dataset (i.e. WBC50 means 50% of original dataset). 


| Model   | Metric             | WBC1    | WBC10   | WBC50   | WBC100  |
|---------|--------------------|---------|---------|---------|---------|
| Baseline| Test accuracy      | 53.88%  | 92.48%  | 95.54%  | 96.06%  |
|         | Weighted F1 score  | 0.54    | 0.93    | 0.96    | 0.96    |
|         | Macro F1 score     | 0.35    | 0.84    | 0.91    | 0.92    |
| Enhanced| Test accuracy      | 73.84%  | 93.40%  | 96.35%  | 97.33%  |
|         | Weighted F1 score  | 0.76    | 0.94    | 0.96    | 0.97    |
|         | Macro F1 score     | 0.63    | 0.88    | 0.93    | 0.95    |

The experiments have successfully demonstrated the effectiveness of applying transfer learning to improve deep learning’s performance, particularly in scenarios where datasets are limited in size. 

The baseline classifier performed well on WBC datasets larger than 10%, and it achieved reasonably good results on the WBC_1. This can be attributed to the ResNet architecture used, data augmentation techniques, data normalization and class weights applied to loss function to avoid overfitting. 

The performance of the transfer learning is robust across all WBC subsets, with at least a F1 score of 0.76 on WBC_1. Pretraining using pRCC and CAM16 datasets and finetuning on WBC dataset with longer training and lower learning rate allowed the model to outperform the baseline classifier for all WBC subsets.

This project is done as part of CS5242 coursework from National University of Singapore.