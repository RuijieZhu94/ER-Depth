<h3 align="center"><strong>ER-Depth: Enhancing the Robustness of Self-Supervised Monocular Depth Estimation in Challenging Scenes</strong></h3>

  <p align="center">
    <a href="https://indu1ge.github.io/ziyangsong">Ziyang Song*</a>,  
    <a href="https://ruijiezhu94.github.io/ruijiezhu/">Ruijie Zhu*</a>,
    <a href="https://chuxwa.github.io/">Chuxin Wang</a>,
    <a href="https://github.com/JiachengDeng">Jiacheng Deng</a>,
    <a href="https://github.com/Hevans123">Jianfeng He</a>,<br>
    <a href="http://staff.ustc.edu.cn/~tzzhang/">Tianzhu Zhang</a>,
    <br>
    *Equal Contribution.
    <br>
    University of Science and Technology of China
    <br>
    <b>TOMM 2025</b>

</p>

<div align="center">
 <a href='https://arxiv.org/abs/2310.08044'><img src='https://img.shields.io/badge/Paper-arXiv-red'></a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<!-- <a href='https://arxiv.org/abs/[]'><img src='https://img.shields.io/badge/arXiv-[]-b31b1b.svg'></a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -->
 <a href='https://ruijiezhu94.github.io/ERDepth_page/'><img src='https://img.shields.io/badge/Project-Page-Green'></a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 <a href='https://github.com/RuijieZhu94/EC-Depth?tab=MIT-1-ov-file'><img src='https://img.shields.io/badge/License-MIT-blue'></a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 <a href='https://paperswithcode.com/sota/unsupervised-monocular-depth-estimation-on-7?p=ec-depth-exploring-the-consistency-of-self'><img src='https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/ec-depth-exploring-the-consistency-of-self/unsupervised-monocular-depth-estimation-on-7'></a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
</div>


<p align="center">
<img src="assets/overview.jpg" width="97%"/>
</p>

> The two-stage training framework of ER-Depth. In the first stage, we train DepthNet and PoseNet with the perturbation-invariant depth consistency loss. In the second stage, we leverage the teacher network to generate pseudo labels and construct a distillation loss to train the student network. Notably, we propose a depth consistency-based filter (DC-Filter) and a geometric consistency-based filter (GC-Filter) to filter out unreliable pseudo labels.

## News
- **16 Dec. 2023**: The code is now available.
- **28 Nov. 2023**: The [project website](https://ruijiezhu94.github.io/ERDepth_page/) was released.
- **12 Oct. 2023**: [ER-Depth](https://arxiv.org/abs/2310.08044) released on arXiv. 

## Installation
Please refer to [dataset_prepare.md](./docs/dataset_prepare.md) for dataset preparation and [get_started.md](./docs/get_started.md) for installation.

## Running

We provide example bash commands to run training or testing. Please modify these files according to your own configuration before running.

### Training

First stage training:

```bash
bash train_first_stage.sh train first_stage_model 2 4 
```
Second stage training:

```bash
bash train_second_stage.sh train second_stage_model 2 4 
```

### Testing

Evaluate the model on KITTI dataset：

```bash
bash evaluate_kitti.sh
```

Evaluate the model on KITTI-C dataset：

```bash
bash evaluate_kittic.sh
```

## Results
We provide the official weights of ER-Depth (the first stage model) and ER-Depth* (the second stage model) on [Google Drive](https://drive.google.com/drive/folders/1UCmVxb640s4xukMyGZx5ib67SQgpmquI?usp=drive_link). Their experimental results on KITTI and KITTI-C are as below. 

### KITTI
| Methods  | AbsRel  | SqRel  | RMSE  | RMSE log  | a1  | a2  | a3  |
| :----: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| ER-Depth  | 0.100 | 0.708 | 4.367 | 0.175 | 0.896 | 0.966 | 0.984 |  |
| ER-Depth*  | 0.100 | 0.689 | 4.315 | 0.173 | 0.896 | 0.967 | 0.985 |

### KITTI-C
| Methods  | AbsRel  | SqRel  | RMSE  | RMSE log  | a1  | a2  | a3  | 
| :----: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| ER-Depth  | 0.115 | 0.841 | 4.749 | 0.189 | 0.869 | 0.958 | 0.982 |  |
| ER-Depth*  | 0.111 | 0.807 | 4.651 | 0.185 | 0.874 | 0.960 | 0.983 |

## Bibtex

If you find our work useful in your research, please consider citing:

```
@article{song2025er,
  title={Er-depth: Enhancing the robustness of self-supervised monocular depth estimation in challenging scenes},
  author={Song, Ziyang and Zhu, Ruijie and Wang, Jing and Wang, Chuxin and He, Jianfeng and Deng, Jiacheng and Yang, Wenfei and Zhang, Tianzhu},
  journal={ACM Transactions on Multimedia Computing, Communications and Applications},
  volume={21},
  number={12},
  pages={1--23},
  year={2025},
  publisher={ACM New York, NY}
}
```

## Acknowledgements

The code is based on [MonoDepth2](https://github.com/ldkong1205/RoboDepth), [MonoViT](https://github.com/zxcqlf/MonoViT), and [RoboDepth](https://github.com/ldkong1205/RoboDepth). 
