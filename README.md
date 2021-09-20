# MAPNet: Multiscale Attention-guided Pyramid Network for Single Image Dehazing

Haze causes vision degradation and also produces smooth images. Single Image dehazing attempts to achieve haze removal from a hazy image and sharpened objects to obtain a high-visibility result. This is a model designed for haze removal which is implemented in PyTorch.

## Dependencies and Installation
* python3.8  
* PyTorch=1.6  
* NVIDIA GPU+CUDA  

## Dataset Preparation
Datasets
We have trained and tested on the released datasets from NTIRE chanllenges:I-Haze, O-Haze, Dense haze and NH-Haze. The following links are these four real-world datasets.  
* I-Haze: https://data.vision.ee.ethz.ch/cvl/ntire18/i-haze/  
* O-Haze: https://data.vision.ee.ethz.ch/cvl/ntire18/o-haze/  
* Dense-Haze: https://data.vision.ee.ethz.ch/cvl/ntire19//dense-haze/  
* NH-Haze: https://data.vision.ee.ethz.ch/cvl/ntire20/nh-haze/

## Experimental Details
#### Train
If you want to train network on real-world datasets. The names for trainset, valset, and testset will change according to the datasets, such as, 'ihaze_train', 'ohaze_val', etc. 
 ```shell
 python main.py --net='map' --crop_size=256 --blocks=24 --gps=3 --bs=2 --lr=0.001 --trainset='dataset_train' --valset='dataset_val' --testset='dataset_test' --epochs=250 --eval_epoch=5
 ```
 * Expand bs, crop_size, blocks will reach better evalution results.  
 
 #### Test
 The names for task will change according to the datasets, such as, 'ihaze', 'ohaze', etc. test_imgs is the folder of test images.
 ```shell
 python test.py --task='dataset' --test_imgs='datasets\dataset\test'
 ```

