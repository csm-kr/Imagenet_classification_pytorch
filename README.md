# Imagenet classification pytorch

experiments torchvision pretrained and re-trained params of imagenet classification 

### Setting

- Python 3.7
- Numpy
- pytorch >= 1.8.0 

### TODO List

- [x] Dataset
- [x] Model
- [x] Loss
- [x] Coder

### Experiment via torchvision pretrained params at validation set

test_torchvision.py 

|model       | # parameters      | Flops              | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | 
|------------|-------------------| ------------------ | ---------- | --------- |-----------|-----------| ----------|
|alexnet     | 2714566           |  366               | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|vgg11       | 507M              |  366               | 224 x 224  | 69.020    | 88.628    | 30.980    | 11.372    | 
|vgg16       | 528M              |  366               | 224 x 224  | 71.592    | 90.382    | 28.408    | 9.618     | 
|vgg19       | 548M              |  366               | 224 x 224  | 72.376    | 90.876    | 27.624    | 9.124     | 



### Experiment via our training params at validation set

Imagenet

|model       | # parameters      | Flops              | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | Training Time |
|------------|-------------------| ------------------ | ---------- | --------- |-----------|-----------| ----------|--------------| 
|alexnet     | -                 | -                  | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 



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

    train : Imagenet training dataset
    test : Imagenet validation dataset

- data augmentation

    1. Resize()
    2. CenterCrop()
    3. ToTensor()
    4. normalize(mean=[0.485, 0.456, 0.406], std=[0.229, 0.224, 0.225])
    
### Reference

Alexnet : https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf

VGGnet : https://arxiv.org/abs/1409.1556

Resnet :

### Start Guide


