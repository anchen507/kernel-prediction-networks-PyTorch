## Kernel Prediction  Networks and Multi-Kernel Prediction Networks
Reimplement of [Burst Denoising with Kernel Prediction Networks](https://arxiv.org/pdf/1712.02327.pdf) and [Multi-Kernel Prediction Networks for Denoising of Image Burst](https://arxiv.org/pdf/1902.05392.pdf) by using PyTorch.

The partial work is following [https://github.com/12dmodel/camera_sim](https://github.com/12dmodel/camera_sim).

## TODO
Write the documents.

## Requirements
- Python3
- PyTorch >= 1.0.0
- Scikit-image
- Numpy
- TensorboardX (needed tensorflow support)

## How to use this repo?

Firstly, you can clone this repo. including train and test codes, and download pretrained model at [https://drive.google.com/open?id=1Xnpllr1dinAU7BIN21L3LkEP5AqMNWso](https://drive.google.com/open?id=1Xnpllr1dinAU7BIN21L3LkEP5AqMNWso).

The repo. supports multiple GPUs to train and validate, and the default setting is multi-GPUs. In other words, the pretrained model is obtained by training on multi-GPUs.

- If you want to restart the train process by yourself, the command you should type is that
```angular2html
CUDA_VISIBLE_DEVICES=x,y train_eval_sym.py --cuda --mGPU -nw 4 --config_file ./kpn_specs/kpn_config.conf --restart
```
If no option of `--restart`, the train process could be resumed from when it was broken.

- If you want to evaluate the network by pre-trained model directly, you could use
```angular2html
CUDA_VISIBLE_DEVICES=x,y train_eval_syn.py --cuda --mGPU -nw 4 --eval
```
If else option `-ckpt` is choosen, you can select the other models you trained.

- Anything else.
  - The code for single image is not released now, I will program it in few weeks.
  
## Results
The following images and more examples can be found at [here](https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/).

<table>
<tr>
<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/1_gt.png"/ width="300"> </center> </td>

<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/1_noisy.png"/ width="300" height=width> </center> </td>

<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/1_kpn.png"/ width="300" height=width> </center> </td>
</tr>

<tr>
<td><center> Ground Truth </center></td>
<td><center> Noisy </center></td>
<td><center> Denoised </center></td>
</tr>

<tr>
<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/21_gt.png"/ width="300"> </center> </td>

<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/21_noisy.png"/ width="300" height=width> </center> </td>

<td> <center> <img src="https://github.com/z-bingo/kernel-prediction-networks-PyTorch/blob/master/eval_images/21_kpn.png"/ width="300" height=width> </center> </td>
</tr>

<tr>
<td><center> Ground Truth </center></td>
<td><center> Noisy </center></td>
<td><center> Denoised </center></td>
</tr>
</table>

##### If you like this repo, Star or Fork to support my work. Thank you.
