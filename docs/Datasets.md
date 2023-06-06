---
layout: default
title: Datasets
nav_order: 3
has_children: false
permalink: /docs/datasets
---

# Datasets

---

[Original dataset source](https://www.kaggle.com/datasets/mostafaabla/garbage-classification)

- 15,150 images (unlabeled)
- 12 different classes of household garbage: paper, cardboard, biological, metal, plastic, green-glass, brown-glass, white-glass, clothes, shoes, batteries, and trash.

## What we did

- Applied downsampling such that each class has ~700 raw waste images (>8000 total images) to prevent model's bias toward majority classes.
- Designed a data preprocessing pipeline that automatically annotates and segments all wastes in the images. (more detail in the method section)
- Various data augmentation techniques were employed to improve the model's ability to learn from data effectively. Resizing, random cropping, and several affine transformations (e.g., horizontal flip, rotation) were applied to introduce variations in the training set. Additionally, resizing and normalizations are applied to ensure all images have the same dimensions and similar pixel value distributions before being fed into the model. For validation and training sets, similar resizing and normalization are performed but without any random transformations to preserve the original data integrity.
- Divided dataset into training, validation, and test sets, following an approximate ratio of 80:10:10, respectively.

<br>

Data augmentation code:
```
# Create data loaders: Use PyTorch's DataLoader to create data loaders for the training, validation, and testing sets.
batch_size = 32

from torchvision.transforms import functional as F

class ResizeNormalizeForImage(object):
    def __init__(self, size, mean, std):
        self.size = size
        self.mean = mean
        self.std = std

    def __call__(self, img):
        img = F.resize(img, self.size)
        img = F.to_tensor(img)
        img = F.normalize(img, self.mean, self.std)
        return img

img_transforms_train = transforms.Compose([
    transforms.Resize(256),
    transforms.RandomCrop(224),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(degrees=15),
    transforms.RandomAffine(degrees=15, translate=(0.1, 0.1), scale=(0.8, 1.2), shear=15),
    ResizeNormalizeForImage(224, mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
])

# For validation and testing, we should apply the same resizing and normalization transformations,
# but without data augmentation:
img_transforms_val_test = transforms.Compose([
    transforms.Resize(256),
    transforms.CenterCrop(224),
    ResizeNormalizeForImage(224, mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
])

mask_transforms = transforms.Compose([
    transforms.Resize(256),
    transforms.CenterCrop(224),
    transforms.ToTensor()
])
```