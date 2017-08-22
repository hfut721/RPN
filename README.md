# Code and Demo For Fine-grained car recognition method based on region proposal networks [Under Review]
# Our trained caffemodel and training files will be release after paper be accepted.


This code modified from :
1. [py-faster-rcnn](https://github.com/rbgirshick/py-faster-rcnn)  
2. [faster-rcnn-resnet](https://github.com/Eniac-Xie/faster-rcnn-resnet)
3. [deep-residual-networks](https://github.com/KaimingHe/deep-residual-networks)


# Demo For Stanford Cars-196
![demo1](https://raw.githubusercontent.com/hfut721/RPN/master/demo/100630.jpg)
![demo2](https://raw.githubusercontent.com/hfut721/RPN/master/demo/100631.jpg)

# Installation

1. Clone this repository
  ```Shell
  git clone https://github.com/hfut721/RPN.git
  ```
  We'll call the directory that you cloned RPN `ROOT`

2. Clone the modified caffe-fast-rcnn

  ```Shell
  cd $ROOT/
  git clone 
  git clone https://github.com/Eniac-Xie/caffe-fast-rcnn.git
  ```

3. Build Cython module

  ```Shell
   cd $ROOT/lib/
   make
  ```

4. Build Caffe

  ```Shell
   cd $ROOT/caffe-fast-rcnn
   make all -j8
   make pycaffe
  ```
# Result

|                 | dataset          | accuracy  | 
|-----------------|:----------------:|:---------:|
|RPN, ResNet-101  | Stanford BMW-10  |   78.74%  |        
|RPN, ResNet-101  | Stanford Cars-196|   91.48%  |    


# Testing
Download our paper models and pretraining weights from:



then you can do as follow:

  ```Shell
   cd $ROOT/
   sh experiments/scripts/train_resnet101_bn_scale_merged_0712_end2end.sh
   make
  ```


# Training
Download resnet-101 pretrained model, note that we use a modified version in which batchnorm layer's parameters is
merged into scale layer's, you can download the model from [Baidu Yun](http://pan.baidu.com/s/1qX7VFjA) or [OneDrive](https://1drv.ms/u/s!AgkRygoHQVTXigBCR-5cnmAkfGfy)

then you can do as follow:
  ```Shell
   cd $ROOT/
   sh experiments/scripts/train_resnet101_bn_scale_merged_0712_end2end.sh
  ```
