Tags: #YOLOX #ImageAugmentation #Mosaic #Mixup
Vimwiki: :YOLOX:ImageAugmentation:Mosaic:Mixup:

______________________________________________________________________

# YOLOX

- __Description:__ Note for YOLOX
- __Author:__ Kuan-Hsien Wu
- __Contact:__ jordankhwu@gmail.com
- __Date:__

## Image Augmentation

### Exp

`/yolox/exp/default/yolox_base.py`

- Data loader
  - `get_data_loader`
- Multiple input_size training
  - multiscale_range
  - random_size

### Data Image Augmentation

`/yolox/data/datasets/mosaicdetection.py`

- If mosaic is activated (`random.random < self.mosaic_prob`):
  1. mosaic, here uses input_size = (320,320) as example
     1. resize 4 input images to 4 320x320 padded images
     1. concatenate 4 320x320 padded images to 1 640x640 image (x2 input_size)
     1. filter out labels that are outside the 640x640 image
  1. random affine transformation
     1. Rotation
     1. Scale
     1. Shear
     1. Translation
  1. mixup:
     - CopyPaste: https://arxiv.org/abs/2012.07177
  1. pre-process: `TrainTransform` in `/yolox/data/data_augment.py`
     1. Flip
     1. HSV augment (color jitter in HSV space)
- Else:
  1. pre-process: `TrainTransform` in `/yolox/data/data_augment.py`
     1. Flip
     1. HSV augment (color jitter in HSV space)
