# Enhanced Point Cloud Normal Estimation via Multi-Scale Geometric Feature Fusion and Attention Mechanism

This repo is implementation for enhanced learning-based normal estimation for point clouds in pytorch.

## Requirements
- Ubuntu 20.04
- PYthon 3.9.19
- Pytorch 1.11.0 with torchvision using the following command: pip install torch==1.11.0+cu113 torchvision==0.12.0+cu113 torchaudio==0.11.0 --extra-index-url https://download.pytorch.org/whl/cu113 (https://pytorch.org/get-started/previous-versions/)
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

The FamousShape and SceneNN datasets can be downloaded from https://github.com/LeoQLi/SHS-Net?tab=readme-ov-file. You can download the PCPNet dataset as well.

The downloaded datasets should be organized as follows:
```
data/FamousShape

data/pcpnet

data/SceneNN
```
