## A Light Weight Model for Active Speaker Detection
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/a-light-weight-model-for-active-speaker/audio-visual-active-speaker-detection-on-ava)](https://paperswithcode.com/sota/audio-visual-active-speaker-detection-on-ava?p=a-light-weight-model-for-active-speaker)

This repository contains the code and model weight for our [paper](https://arxiv.org/pdf/2303.04439.pdf) (Accepted by CVPR 2023):

> A Light Weight Model for Active Speaker Detection  
> Junhua Liao, Haihan Duan, Kanghui Feng, Wanbing Zhao, Yanbing Yang, Liangyin Chen


***
### Evaluate on AVA-Activespeaker dataset 

#### Data preparation
Use the following code to download and preprocess the AVA dataset.
```
python train.py --dataPathAVA AVADataPath --download 
```
The AVA dataset and the labels will be downloaded into `AVADataPath`.

#### Training
You can train the model on the AVA dataset by using:
```
python train.py --dataPathAVA AVADataPath
```
`exps/exps1/score.txt`: output score file, `exps/exp1/model/model_00xx.model`: trained model, `exps/exps1/val_res.csv`: prediction for val set.

#### Testing
Our model weights have been placed in the `weight` folder. It performs `mAP: 94.06%` in the validation set. You can check it by using: 
```
python train.py --dataPathAVA AVADataPath --evaluation
```


***
### Evaluate on Columbia ASD dataset

#### Testing
The model weights we trained on the AVA dataset have been placed in the `weight` folder. Then run the following code.
```
python Columbia_test.py --evalCol --colSavePath colDataPath
```
The Columbia ASD dataset and the labels will be downloaded into `colDataPath`. And you can get the following F1 result.
| Name |  Bell  |  Boll  |  Lieb  |  Long  |  Sick  |  Avg.  |
|----- | ------ | ------ | ------ | ------ | ------ | ------ |
|  F1  |  82.7% |  75.7% |  87.0% |  74.5% |  85.4% |  81.1% |


***
### Citation

Please cite our paper if you use this code or model. 

```
@inproceedings{liao2023light,
  title={A Light Weight Model for Active Speaker Detection},
  author={Liao, Junhua and Duan, Haihan and Feng, Kanghui and Zhao, Wanbing and Yang, Yanbing and Chen, Liangyin},
  booktitle={IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2023},
  organization={IEEE}
}
```

***
### Acknowledgments
Thanks for the support of TaoRuijie's open source [repository](https://github.com/TaoRuijie/TalkNet-ASD) for this research.

