# Dorefa-net 
A pytorch implementation of [dorefa](https://arxiv.org/abs/1606.06160).The code is inspired by [LaVieEnRoseSMZ](https://github.com/LaVieEnRoseSMZ/AutoBNN) and [zzzxxxttt](https://github.com/kuangliu/pytorch-cifar).

## Requirements
* python > 3.5
* torch >= 1.1.0
* torchvision >= 0.4.0
* tb-nightly, future (for tensorboard)
* nvidia-dali >= 0.12 (faster [dataloader](https://docs.nvidia.com/deeplearning/sdk/dali-developer-guide/docs/index.html#))

## Cifar-10 Accuracy

Quantized model are trained from scratch

| Model | W_bit | A_bit | Acc |
| :-: | :-: | :-: |:-: |
| resnet-18      | 32   |   32     | 94.71%     |
| resnet-18      |   4   |   4      |  94.36%     |
| resnet-18      |   1   |   4      |  93.87%     |


## ImageNet Accuracy

Quantized model are trained from scratch

| Model | W_bit | A_bit | Top1 |Top5 |
| :-: | :-: | :-: |:-: |:-: |
| resnet-18      | 32   |   32     | 69.80%     |89.32%  |
| resnet-18      | 8   |   8     | ...     |...  |

## Usages
config your W_bit and A_bit in models/quant_dorefa.py   
* To train the model 
```
python3 cifar_train_eval.py    or    python3 imagenet_dali_loader.py
```
* To check the tensorboard log 
```
tensorboard --logdir='your_log_dir'
```
from the command line and then navigating to https://localhost:6006 should show the following.

<img src="https://github.com/Jzz24/dorefa_pytorch/blob/master/doc/tensorboard.png" width = "65%" height = "50%" alt="图片名称" align="center" />



## To do
- [x]    Train on imagenet2012
- [ ]    Fold bn
- [ ]    Test speedup from quantization and bn fold
- [ ]    Deploy models to embedded devices
- [ ]    ...
