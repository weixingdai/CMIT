# Complex microscopic image transformation (CMIT) via weakly supervised deep generative modeling
This is a pytorch implementation of CMIT.

## Quick Start Examples
##  Train a model
```python
python train.py --ckp demo --dataroot datasets/demo
```

### Options:
```--ckp```	Model name to be saved in ./checkpoints

```--dataroot```	The folder of dataset for training

```--tol```	Tolerance size, i.e. the size of exculsive regions, default: 256

```--overlap_size```	Overlapping size among the exculsive regions, default: 64

```--batch_size```	Batch size, default: 2

```--lr```	Initial learning rate, default: 0.0002

```--n_epochs```	Number of epochs for keeping the initial learning rate, default: 40

```--n_epochs_decay```	Number of epochs for decaying learning rate, default: 40

```--input_size```	Input size of the network, default: 256

```--input_dim```	Number of input channels, default: 3

```--iter```	Number of iterations per epoch, default: 2000

```--sobel```	Whether use sobel feature, default: True

```--save_mode```	Save mode, simple | full, default: simple

```--tv_dir```	The folder for displaying the results during training

## Test a model
```python
python test.py --input examples/breast001 --ckp breast001 --output results/breast001 --sobel
```
### Options:
```--input```	Input folder name

```--ckp```	Model name

```--output```	Output folder name

```--input_dim```	Number of input channels, default: 3

```--sobel```	Whether use sobel feature
### Low-SNR restoration of planaria
```python
python test.py --input examples/planaria --ckp planaria --output results/planaria --input_dim 1
```
![alt text](https://github.com/weixingdai/CMIT/blob/ab8537d8ab55bf15d2b12e0df6b199901a4c915b/examples/planaria/input.png)
![alt text](https://github.com/weixingdai/CMIT/blob/94d5b8cc787bdf0c04446403c4d1c1f6f71c36cd/results/planaria/fake_cmit_input.png)
![alt text](https://github.com/weixingdai/CMIT/blob/f58098440e8f84e6970808851e2c76fc53b07e06/examples/planaria%20ground%20truth/gt.png)

Left: low-SNR image of planaria. Middle: image restored by CMIT.  Right:  ground truth.

### H&E virtual staining of breast cancer tissue
```python
python test.py --input examples/breast001 --ckp breast001 --output results/breast001 --sobel
```
![alt text](https://github.com/weixingdai/CMIT/blob/c838e57612973f20286dc6be1900e3b98afb308d/examples/breast001/input_3.png)
![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_3.png)
![alt text](https://github.com/weixingdai/CMIT/blob/c058d4fae0702f6d01a76f2f4334904577f2f712/examples/breast001%20ground%20truth/gt_3.png)

Left: autoflourescence image. Middle: fake H&E images generated by CMIT.  Right:  ground truth.

