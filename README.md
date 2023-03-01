## A Light Weight Model for Active Speaker Detection

This repository contains code and models for our [paper](https://ieeexplore.ieee.org/abstract/document/9746742):

> A Light Weight Model for Active Speaker Detection  
> Junhua Liao, Haihan Duan, Kanghui Feng, Wanbing Zhao, Yanbing Yang, Liangyin Chen


***
### Evaluate on AVA-Activespeaker dataset 

#### Data preparation

The following script can be used to download and prepare the AVA dataset for training.
```
python trainTalkNet.py --dataPathAVA AVADataPath --download 
```

#### Training
Then you can train model in AVA end-to-end by using:
```
python train.py --dataPathAVA AVADataPath
```
`exps/exps1/score.txt`: output score file, `exps/exp1/model/model_00xx.model`: trained model, `exps/exps1/val_res.csv`: prediction for val set.

#### Pretrained model
Download our model weight([ICASSP_Model.pth.tar](https://drive.google.com/file/d/1nJLdf1hqvx22LhD_uDOT5O0JeDmapSqN/view?usp=sharing)) and place it in the `weight` folder. It performs `mAP: 94.1` in the validation set. You can check it by using: 
```
python trainTalkNet.py --dataPathAVA AVADataPath --evaluation
```
***




### Citation

Please cite our papers if you use this code or model. 

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
