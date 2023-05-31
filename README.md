## A Light Weight Model for Active Speaker Detection
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/a-light-weight-model-for-active-speaker/audio-visual-active-speaker-detection-on-ava)](https://paperswithcode.com/sota/audio-visual-active-speaker-detection-on-ava?p=a-light-weight-model-for-active-speaker)

This repository contains the code and model weights for our [paper](https://openaccess.thecvf.com/content/CVPR2023/papers/Liao_A_Light_Weight_Model_for_Active_Speaker_Detection_CVPR_2023_paper.pdf) (CVPR 2023):

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
The model weights trained on the AVA dataset have been placed in the `weight` folder. Then run the following code.
```
python Columbia_test.py --evalCol --colSavePath colDataPath
```
The Columbia ASD dataset and the labels will be downloaded into `colDataPath`. And you can get the following F1 result.
| Name |  Bell  |  Boll  |  Lieb  |  Long  |  Sick  |  Avg.  |
|----- | ------ | ------ | ------ | ------ | ------ | ------ |
|  F1  |  82.7% |  75.7% |  87.0% |  74.5% |  85.4% |  81.1% |

We have also provided the model weights fine-tuned on the TalkSet dataset. Due to space limitations, we did not exhibit it in the paper. Run the following code.
```
python Columbia_test.py --evalCol --pretrainModel weight/finetuning_TalkSet.model --colSavePath colDataPath
```
And you can get the following F1 result.
| Name |  Bell  |  Boll  |  Lieb  |  Long  |  Sick  |  Avg.  |
|----- | ------ | ------ | ------ | ------ | ------ | ------ |
|  F1  |  97.7% |  86.3% |  98.2% |  99.0% |  96.3% |  95.5% |


***
### Citation

Please cite our paper if you use this code or model weights. 

```
@InProceedings{Liao_2023_CVPR,
    author    = {Liao, Junhua and Duan, Haihan and Feng, Kanghui and Zhao, Wanbing and Yang, Yanbing and Chen, Liangyin},
    title     = {A Light Weight Model for Active Speaker Detection},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {22932-22941}
}
```

***
### Acknowledgments
Thanks for the support of TaoRuijie's open source [repository](https://github.com/TaoRuijie/TalkNet-ASD) for this research.

