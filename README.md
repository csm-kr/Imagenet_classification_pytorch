# Imagenet classification pytorch

re-training of imagenet classification 

Alexnet : https://arxiv.org/abs/1708.02002
VGGnet :
Resnet :


### Setting

- Python 3.7
- Numpy
- pytorch >= 1.8.0 

### TODO List

- [x] Dataset
- [x] Model
- [x] Loss
- [x] Coder

### Experiment

Imagenet

|model       | # parameters      | Flops                  | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | Training Time |
|------------|-------------------| ---------------------- | ---------- | --------- |-----------|-----------| -----------|--------------| 
|alexnet     | COCOtrain2017     |  COCO test-dev         | 224 x 224  |  34.0     |52.5     |98   |
|vgg11       | COCOtrain2017     |  COCOval2017(minival)  | 224 x 224  |  34.3     |53.2     |98   |
|vgg16       | COCOtrain2017     |  COCO test-dev         | 224 x 224  |**34.7**   |**53.6** |67   |
|vgg19       | COCOtrain2017     |  COCOval2017(minival)  | 224 x 224  |**34.7**   |**53.5** |67   |


### Experiment via torchvision validation 

test_torchvision.py 

|model       | # parameters      | Flops                  | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | 
|------------|-------------------| ---------------------- | ---------- | --------- |-----------|-----------| ----------|
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|vgg11       | 507M              |  366                   | 224 x 224  | 69.020    | 88.628    | 30.980    | 11.372    | 

|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|alexnet     | 2714566           |  366                   | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 


### training options

- batch : 64
- scheduler : step LR
- loss : focal loss and smooth l1 loss
- dataset : imagenet ~(138M)
- epoch : 60
- gpu : nvidia geforce rtx 3090
- lr : 1e-2

### training

- dataset

    train : trainval35k == train2017
    test : minval2014 == val2017

- data augmentation

    1. Resize()
    2. CenterCrop()
    3. ToTensor()
    4. normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
    
### Reference

ssd tutorial : data augmentation and detection structure

https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Object-Detection

retina net pytorch

https://github.com/NVIDIA/retinanet-examples

https://github.com/yhenon/pytorch-retinanet

### Start Guide


