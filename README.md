# Epi_correction

This repository is a torch implementation of "Unsupervised cycle-consistent network using restricted subspace field map for removing susceptibility artifacts in EPI"

## Pretrained Models
you can download a pretrained version of FlowNetS (from caffe, not from pytorch) [here](https://drive.google.com/open?id=0B5EC7HMbyk3CbjFPb0RuODI3NmM). This folder also contains trained networks from scratch. Thanks to [Kaixhin](https://github.com/Kaixhin).

### Note on networks loading
Directly feed the downloaded Network to the script, you don't need to uncompress it even if your desktop environment tells you so.

## Prerequisite
these modules can be installed with `pip`

```
pytorch >= 1.2
tensorboard-pytorch
tensorboardX >= 1.4
spatial-correlation-sampler>=0.2.1
imageio
argparse
path.py
```

or
```bash
pip install -r requirements.txt
```

Default HyperParameters provided in `main.py` are the same as in the caffe training scripts.

* Example usage for UCRSF-Net :

```bash
python main.py 
```

## Visualizing training
[Tensorboard-pytorch](https://github.com/lanpa/tensorboard-pytorch) is used for logging. To visualize result, simply type

```bash
tensorboard --logdir=/path/to/checkoints
```
	
## Running inference on a set of image pairs

If you need to run the network on your images, you can download a pretrained network [here](https://drive.google.com/open?id=0B5EC7HMbyk3CbjFPb0RuODI3NmM) and launch the inference script on your folder of image pairs.

Your folder needs to have all the images pairs in the same location, with the name pattern
```
{image_name}1.{ext}
{image_name}2.{ext}
```

```bash
python3 run_inference.py /path/to/images/folder /path/to/pretrained
```

## Acknowledge
Thanks to the strong and flexible [FlowNetPytorch](https://github.com/ClementPinard/FlowNetPytorch) codebase maintained by Dosovitskiy et al.
