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
python test.py --input examples/breast001 --ckp breast001 --output results/breast001_cmit --sobel
```
### Options:
```--input```	Input folder name

```--ckp```	Model name

```--output```	Output folder name

```--input_dim```	Number of input channels, default: 3

```--sobel```	Whether use sobel feature

## Demo
### Low-SNR restoration of Planaria
```python
python test.py --input examples/planaria --ckp planaria --output results/planaria --input_dim 1
```
![alt text](https://github.com/weixingdai/CMIT/blob/c838e57612973f20286dc6be1900e3b98afb308d/examples/breast001/input_1.png)
![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_1.png)
![alt text](https://github.com/weixingdai/CMIT/blob/a8778cb8bade10d05895f90ace5db48bdca5e058/examples/breast001%20ground%20truth/gt_1.png)

Use the model in ./checkpoints/breast001 and test the images in ./examples, the results are as follows:
  
![alt text](https://github.com/weixingdai/CMIT/blob/c838e57612973f20286dc6be1900e3b98afb308d/examples/breast001/input_1.png)
![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_1.png)
![alt text](https://github.com/weixingdai/CMIT/blob/a8778cb8bade10d05895f90ace5db48bdca5e058/examples/breast001%20ground%20truth/gt_1.png)

![alt text](https://github.com/weixingdai/CMIT/blob/c838e57612973f20286dc6be1900e3b98afb308d/examples/breast001/input_2.png)
![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_2.png)
![alt text](https://github.com/weixingdai/CMIT/blob/b7159ba29fe4e928a5083ebc062a7b2b51bb0151/examples/breast001%20ground%20truth/gt_2.png)

![alt text](https://github.com/weixingdai/CMIT/blob/c838e57612973f20286dc6be1900e3b98afb308d/examples/breast001/input_3.png)
![alt text](https://github.com/weixingdai/CMIT/blob/7216a9843db737d8a3a243815ebe1f93c4214fb3/results/breast001_cmit/fake_cmit_input_3.png)
![alt text](https://github.com/weixingdai/CMIT/blob/c058d4fae0702f6d01a76f2f4334904577f2f712/examples/breast001%20ground%20truth/gt_3.png)

The first column are autoflourescence images, the second column are the fake H&E images generated by CMIT, and the third column are the ground truths.

