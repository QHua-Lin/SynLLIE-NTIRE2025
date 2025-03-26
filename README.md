# SynLLIE-NTIRE2025

## 1. Create Environment

We suggest you use pytorch 1.11 to re-implement the results in our ICCV 2023 paper and pytorch 2 to re-implement the results in NTIRE 2024 Challenge because pytorch 2 can save more memory in mix-precision training.

### 1.1 Install the environment with Pytorch 1.11

- Make Conda Environment
```
conda create -n ntire python=3.7
conda activate ntire
```

- Install Dependencies
```
conda install pytorch=1.11 torchvision cudatoolkit=11.3 -c pytorch

pip install matplotlib scikit-learn scikit-image opencv-python yacs joblib natsort h5py tqdm tensorboard

pip install einops gdown addict future lmdb numpy pyyaml requests scipy yapf lpips
```

- Install BasicSR
```
python setup.py develop --no_cuda_ext

## 2. Testing

Download our models from [Baidu Disk](https://pan.baidu.com/s/13zNqyKuxvLBiQunIxG_VhQ?pwd=cyh2) (code: `cyh2`) or [Google Drive](https://drive.google.com/drive/folders/1ynK5hfQachzc8y96ZumhkPPDXzHJwaQV?usp=drive_link). Put them in folder `pretrain_weights`

```shell
# activate the environment
conda activate ntire

# run
python3 Enhancement/test_from_dataset.py --opt Options/NTIRE_LLIE2025.yml --weights pretrain_weights/NTIRE_LLIE2025.pth 
