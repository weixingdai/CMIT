# Complex microscopic image transformation (CMIT) via weakly supervised deep generative modeling
This is a pytorch implementation of CMIT.

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
python test.py --input examples/breast001 --ckp breast001 --output results/breast001_cmit
```
### Options:
```--input```	Input folder name

```--ckp```	Model name

```--output```	Output folder name

```--input_dim```	Number of input channels, default: 3

```--sobel```	Whether use sobel feature, default: True

## Demo
Use the pre-trained model in ./checkpoints/breast001 and test the images in ./examples

![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_1.png)
