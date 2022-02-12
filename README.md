# BRATS2018 - Brain Tumor Segmentation

# Introduction

Gliomas are the most frequent primary brain tumor in adults, but the diagnosis of gliomas tumor is poor. In clinical studies, the images are qualitatively assessed, or assessed based on some rudimentary quantitative measures. An accurate, reproducible, and automated brain tumor analysis tool would improve the diagnosis of tumors. The BRATS2018 dataset given contain 4 MRI contrasts : T1 (T1 weighted native image), T1ce (T1 weighted, contrast enhanced), T2 ( T2 weighted) and FLAIR ( T2 weighted flair image). The images were manually annotated into 4 types of intra-tumoral structures : edema, non-enhancing core, necrotic core and enhancing core. According to manual annotation flair outlines whole tumor, T2 outlines core region and T1CE outlines the active tumor region. The task on hand is to segment “whole tumor” – including all 4 tumor structures. The dice score is used as evaluation metrics.

# ITK implementation

Python Implementation of 6 ITK segmentation algorithms provided for BRATS2018 brain tumor segmentation task.

1.  The region growing segmentation algorithms 
    1. Isolated connected
        
        ![IC_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/IC_1.png)
        
    2. Connected threshold
        
        ![CC_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/CC_1.png)
        
    3. Confidence connected
        
        ![conf_conn_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/conf_conn_1.png)
        
    4. Neighborhood connected
        
        ![NC_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/NC_1.png)
        
2. Watershed
3. Level set segmentation
    1. Canny level set segmentation
        
        ![canny_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/canny_1.png)
        
    2. Fast March
        
        ![fastmarch_1.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/fastmarch_1.png)
        

# U-Net Segmentation algorithm

A deep learning model – U-Net was implemented for automatic segmentation.  Deep learning-based segmentation algorithm automates the segmentation process. Segmentation using ITK required several iterations of fine tunings for each parameter such as seed, lower threshold, upper threshold, etc. In most case these parameters are chosen by trial-and-error approach, which consumed massive amount of time and also requires prior knowledge. A well trained and well generalized U-Net architecture doesn’t consume much time for segmentation rather can be used for real-time segmentation and prior knowledge regarding the medical images (threshold values/ seed points) are not required. 

![4.png](BRATS2018%20-%20Brain%20Tumor%20Segmentation/4.png)