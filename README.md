# 2D Convolution-Neural-Network-Blood-Cells-Classification
Blood Cell Image Classifier using 2D Convolution Neural Network(PyTorch,Numpy,SkImage)




A Convolution Neural Network built around the data containing "images" about blood cells.

This dataset contains 12,500 augmented images of blood cells (JPEG) with accompanying cell type labels (CSV). There are approximately 3,000 images for each of 4 different cell types grouped into 4 different folders (according to cell type). The cell types are Eosinophil, Lymphocyte, Monocyte, and Neutrophil. This dataset is accompanied by an additional dataset containing the original 410 images (pre-augmentation) as well as two additional subtype labels (WBC vs WBC) and also bounding boxes for each cell in each of these 410 images (JPEG + XML metadata). More specifically, the folder 'dataset-master' contains 410 images of blood cells with subtype labels and bounding boxes (JPEG + XML), while the folder 'dataset2-master' contains 2,500 augmented images as well as 4 additional subtype labels (JPEG + CSV). There are approximately 3,000 augmented images for each class of the 4 classes as compared to 88, 33, 21, and 207 images of each in folder 'dataset-master'.

Source : https://www.kaggle.com/datasets/paultimothymooney/blood-cells?datasetId=9232&sortBy=dateRun&tab=profile

Image Batches are random using valid "SubsetRandomSampler" and have been tranformed to "Tensors" and random variations have been included by "Transforms.Compose([])".

The Architecutre contains a 

PART-1 :

  IMAGE_BATCH -> CL1 -> BN1 -> RA_1 -> MP_1 -> CL2 -> BN2 -> RA_2 -> MP_2 ->  CL3 -> BN3 -> RA_3 -> MP_3 -> CL4 -> BN4 -> RA_4 -> MP_4 -> FEATURES EXTRACTED
  
  CL = CONVOLUTION_LAYER,BN = BATCH NORMALIZATION LAYER FOR REGULARIZATION,RA = ReLU_ACTIVATION, MP = MAX_POOLING LAYER.
  
PART-2 :

  EXTRACTED_FEATURES -> FLATTENING_INTO 1D TENSOR INPUTS -> FC1 -> FC2 -> FC3 -> OUTPUT_LAYER
  
   FC = FULLY CONNECTED LAYERS
   
 OPTIMIZERS USED ARE 'STOCHASTIC GRADIENT DESCENT'.
 ERROR_METRIC IS MEASURED USING 'CROSS_ENTROPY'
 
 --------------------------------------------
 TRAIN SCORE ACHIEVED : Accuracy of the network on the 7468 train images: 87.35940010712373 %
 VALID SCORE ACHIEVED : Accuracy of the network on the 2489 validation images: 86.54077942948976 %
 TEST SCORE ACHIEVED : Accuracy of the network on the 2487 test images: 75.6735022114998 %
 
TOTAL DATA(IMAGES USED) : TRAIN = (7468 + 2489), TEST = 2487 = 12,444 RGB IMAGES OF (240,320,3) ---> (HEIGHT,WIDTH,CHANNELS)


 
 
