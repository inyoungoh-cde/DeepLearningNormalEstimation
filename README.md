# Enhanced Point Cloud Normal Estimation via Multi-Scale Geometric Feature Fusion and Attention Mechanism

This repo is implementation for enhanced learning-based normal estimation for point clouds in pytorch.

## Requirements
- Ubuntu 20.04
- PYthon 3.9.19
- Pytorch 1.11.0 with torchvision using the following command: pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113 (from the website, https://pytorch.org/get-started/previous-versions/)
- Numpy 1.26.4
- scipy 1.13.1
- tensorboardX 2.6.2.2
- scikit-learn 1.5.1
- Pytorch3d 0.7.4 (please follow the official installation: https://github.com/facebookresearch/pytorch3d/blob/main/INSTALL.md)

## Detailed usage guidelines

### Data praparation

You can download the PCPNet dataset by running
```
python get_data.py
```
or by visiting the following website: https://github.com/paulguerrero/pcpnet.

The FamousShape and SceneNN datasets can be downloaded from https://github.com/LeoQLi/SHS-Net. You can download the PCPNet dataset as well.

The downloaded datasets should be organized as follows:
```
data/FamousShape

data/pcpnet

data/SceneNN
```

### Train the proposed network

You can train the proposed network using the organized datasets by running the following command:
```
python train_our.py
```
On our desktop with an NVIDIA 3090 (24 GB), it takes about 1.5 to 2 days to train the network. The trained model will be saved in ```./log_ablation_noLw/test_LAB12345+GAB_order4/```.

### Test the proposed network

You can evaluate the trained model by following two commands:
```
python test_our.py
python evaluate.py
```
The results, including predicted normals and qualitative outcomes (e.g., summaries for six types—no, low, medium, and high noise levels, as well as gradient and striped densities—for the PCPNet dataset), will be saved in ```./log_ablation_noLw/test_LAB12345+GAB_order4/results/```.

Make sure that the default setting evaluates on a sparse set of patches. For example, in the PCPNet dataset, each point cloud contains 100,000 points, and 5,000 predicted normal vectors are generated per point cloud. If you want to evaluate on a full set of patches, please use the ```--sparse_patches False``` flag.

### Pretrained network

We provide the pretrained network, which is saved in ```./pretrained/test_LAB12345+GAB_order4/``` along with our evaluated results. Please place the .zip file in the specified directory.

## Acknowledgement

Our code is heavily based on MCPA ```https://github.com/CharlesLee96/NormalEstimation```, GraphFit ```https://github.com/UestcJay/GraphFit```, and SHSNet (CVPR 2023) ```https://github.com/LeoQLi/SHS-Net```.

Please cite our paper (sumbitted to The Visual Computer in February 2025) if you are interested in the proposed method. 

```
@article{DeepLearningNormalEstimation,
  title={Enhanced Point Cloud Normal Estimation via Multi-Scale Geometric Feature Fusion and Attention Mechanism},
  author={Inyoung Oh, Jinho Song, Minsung Kim, Dongho Yun, and Kwanghee Ko},
  journal={The Visual Computer},
  DOI={https://doi.org/10.5281/zenodo.14885564}
}
```
