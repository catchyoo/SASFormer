# SASFormer : A Decoding Scheme With Successive Aggregation of Multi-Level Features For Light-Weight Semantic Segmentation (ICIP 2024)

### 📝[Paper](https://ieeexplore.ieee.org/document/10647675)

> #### Jiwon Yoo<sup>1</sup>, Jangwon Lee<sup>1</sup>, Gyeonghwan Kim<sup>1&dagger;</sup>
> <sup>&dagger;</sup>Correspondence

> <sup>1</sup> Sogang University

---

This repository contains the official PyTorch implementation of training & evaluation code and the pretrained models for SASFormer.

![SASFormer Architecture](https://github.com/user-attachments/assets/647b3761-ee28-4a79-bdf8-440e72a07070)

---

## Installation
For install and data preparation, please refer to the guidelines in [MMSegmentation v1.0.0](https://github.com/open-mmlab/mmsegmentation?tab=readme-ov-file)
Other requirements: pip install timm==0.9.12
An example (works for me): CUDA 11.8 and pytorch 2.0.1

```bash
pip install torchvision==0.16.0
pip install timm==0.9.12
pip install mmcv==2.1.0
pip install opencv-python==4.8.1.78
cd SASFormer && pip install -e . --user
```
## Evaluation
Download [SASFormer weights](https://drive.google.com/drive/folders/1vROj9k9Ax2LVDYwPZQA1BiEDnP7rmECi?hl=ko) into the ``/path/to/checkpoint_file``.

``local_configs/`` contains config files. 

Example : Evaluate ``SASFormer-B0`` on ``ADE20K``:

```bash
# Single-gpu testing
CUDA_VISIBLE_DEVICES=0 python ./tools/test.py local_configs/sasformer/B0/sasformer.b0.512x512.ade.160k.py /path/to/checkpoint_file

# Multi-gpu testing
CUDA_VISIBLE_DEVICES=0,1 bash ./tools/dist_test.sh local_configs/sasformer/B0/sasformer.b0.512x512.ade.160k.py /path/to/checkpoint_file <GPU_NUM>
```
## Training
Download backbone(MiT-B0 & MiT-B2) pretrained weights in [here](https://drive.google.com/drive/folders/1Wr4qiaH54IywMEIJ39w-5X3-MKVOxYi1?hl=ko).

Put them in a folder ``ckpt/``.

Example : Train ``SASFormer-B0`` on ``ADE20K``:

```bash
# Single-gpu training
CUDA_VISIBLE_DEVICES=0 python ./tools/train.py local_configs/sasformer/B0/sasformer.b0.512x512.ade.160k.py 

# Multi-gpu training
CUDA_VISIBLE_DEVICES=0,1 bash ./tools/dist_train.sh local_configs/sasformer/B0/sasformer.b0.512x512.ade.160k.py <GPU_NUM>
```

## Citation
```
@INPROCEEDINGS{10647675,
  author={Yoo, Jiwon and Lee, Jangwon and Kim, Gyeonghwan},
  booktitle={2024 IEEE International Conference on Image Processing (ICIP)}, 
  title={A Decoding Scheme With Successive Aggregation of Multi-Level Features For Light-Weight Semantic Segmentation}, 
  year={2024},
  volume={},
  number={},
  pages={1071-1077},
  keywords={Computer vision;Accuracy;Semantic segmentation;Computational modeling;Semantics;Computer architecture;Transformers;Semantic segmentation;Successive cross-attention;Transformer-based decoder;Aggregated semantics},
  doi={10.1109/ICIP51287.2024.10647675}}
```
