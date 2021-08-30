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

MFLOPS - 10^6

GFLOPS - 10^9

TFLOPS - 10^12

https://pytorch.org/vision/stable/models.html
 
|model       | # Parameters  | # Params | Flops          | Flops(G) | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | 
|------------|---------------| ---------|----------------|--------- | ---------- | --------- |-----------|-----------| ----------|
|alexnet     | 61,100,840    | 61M      |    714,691,904 |  0.71 G  | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 
|vgg11       | 132,863,336   | 132.86M  |  7,616,566,272 |  7.62 G  | 224 x 224  | 69.020    | 88.628    | 30.980    | 11.372    | 
|vgg16       | 138,357,544   | 138.36M  | 15,483,862,016 | 15.48 G  | 224 x 224  | 71.592    | 90.382    | 28.408    | 9.618     |  
|vgg19       | 143,667,240   | 143.67M  | 19,646,964,736 | 19.65 G  | 224 x 224  | 72.376    | 90.876    | 27.624    | 9.124     | 
|resnet18    | 11,689,512    | 11.69M   |  1,819,066,368 |  1.82 G  | 224 x 224  | 69.758    | 89.078    | 30.242    | 10.922    | 
|resnet34    | 21,797,672    | 21.80M   |  3,671,263,232 |  3.67 G  | 224 x 224  | 73.314    | 91.420    | 26.686    | 8.580     | 
|resnet50    | 25,557,032    | 25.56M   |  4,111,514,624 |  4.11 G  | 224 x 224  | 76.130    | 92.862    | 23.870    | 7.138     | 
|resnet101   | 44,549,160    | 44.55M   |  7,833,971,712 |  7.83 G  | 224 x 224  | 77.374    | 93.546    | 22.626    | 6.454     | 
|resnet152   | 44,549,160    | 44.55M   |  7,833,971,712 |  7.83 G  | 224 x 224  | 78.312    | 94.046    | 21.688    | 5.954     | 


### Experiment via our training params at validation set

Imagenet

|model       | # parameters      | Flops              | Resolution | top-1 Acc | top-5 Acc | top-1 Err | top-5 Err | Training Time |
|------------|-------------------| ------------------ | ---------- | --------- |-----------|-----------| ----------|--------------| 
|alexnet     | -                 | -                  | 224 x 224  | 56.522    | 79.066    | 43.478    | 20.934    | 

```

torchvision params and Flops
Model | Params(M) | FLOPs(G)
---|---|---
alexnet | 61.10 | 0.71
densenet121 | 7.98 | 2.87
densenet161 | 28.68 | 7.79
densenet169 | 14.15 | 3.40
densenet201 | 20.01 | 4.34
googlenet | 6.62 | 1.50
inception_v3 | 23.83 | 5.73
mnasnet0_5 | 2.22 | 0.11
mnasnet0_75 | 3.17 | 0.23
mnasnet1_0 | 4.38 | 0.33
mnasnet1_3 | 6.28 | 0.54
mobilenet_v2 | 3.50 | 0.31
mobilenet_v3_large | 5.48 | 0.23
mobilenet_v3_small | 2.54 | 0.06
resnet101 | 44.55 | 7.83
resnet152 | 60.19 | 11.56
resnet18 | 11.69 | 1.82
resnet34 | 21.80 | 3.67
resnet50 | 25.56 | 4.11
resnext101_32x8d | 88.79 | 16.48
resnext50_32x4d | 25.03 | 4.26
shufflenet_v2_x0_5 | 1.37 | 0.04
shufflenet_v2_x1_0 | 2.28 | 0.15
shufflenet_v2_x1_5 | 3.50 | 0.30
shufflenet_v2_x2_0 | 7.39 | 0.59
squeezenet1_0 | 1.25 | 0.82
squeezenet1_1 | 1.24 | 0.35
vgg11 | 132.86 | 7.62
vgg11_bn | 132.87 | 7.63
vgg13 | 133.05 | 11.32
vgg13_bn | 133.05 | 11.35
vgg16 | 138.36 | 15.48
vgg16_bn | 138.37 | 15.51
vgg19 | 143.67 | 19.65
vgg19_bn | 143.68 | 19.68
wide_resnet101_2 | 126.89 | 22.80
wide_resnet50_2 | 68.88 | 11.43
```

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


