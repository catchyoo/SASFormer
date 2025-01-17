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
