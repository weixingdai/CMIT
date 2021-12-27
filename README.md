# Complex microscopic image transformation (CMIT) via weakly supervised deep generative modeling
This is a pytorch implementation of CMIT.

##  Train a model
```python
python train.py --ckp demo --dataroot datasets/demo
```

### Options

## Test a model
'''python
python test.py --i examples/breast001 --c breast001 --o results/breast001_cmit
'''
