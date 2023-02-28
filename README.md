## A Light Weight Model for Active Speaker Detection

This repository contains code and models for our [paper](https://ieeexplore.ieee.org/abstract/document/9746742):

> A Light Weight Model for Active Speaker Detection  
> Junhua Liao, Haihan Duan, Kanghui Feng, Wanbing Zhao, Yanbing Yang, Liangyin Chen


### Setup 

1) Download the model weights and place them in the `weights` folder:


Model weights:
- [ICASSP_Model.pth.tar](https://drive.google.com/file/d/1nJLdf1hqvx22LhD_uDOT5O0JeDmapSqN/view?usp=sharing)

2) Download the dataset and decompress it in the `data` folder:


Dataset:
- [OcclusionDataSet-MM20](https://junhua-liao.github.io/Occlusion-Detection/)

  
3) Set up dependencies: 

    ```shell
    pip install -r requirements.txt
    ```

### Usage 

1) Run occlusion detection model:

    ```shell
    python test.py
    ```

### Citation

Please cite our papers if you use this code or any of the models. 

```
@inproceedings{liao2023light,
  title={A Light Weight Model for Active Speaker Detection},
  author={Liao, Junhua and Duan, Haihan and Feng, Kanghui and Zhao, Wanbing and Yang, Yanbing and Chen, Liangyin},
  booktitle={CVPR},
  pages={},
  year={2023},
  organization={IEEE}
}
```
