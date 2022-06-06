# <p align="center">Openpilot-reimplementation</p>
**<p align="center">Level 2 Autonomous Driving on a Single Device: Diving into the Devils of Openpilot</p>**
![image](https://github.com/caizhitian/openpilot-reimplementation/blob/master/pic/arXiv_fig1.png)
> arXiv link: [arXiv](https://www.overleaf.com/project/626954666328026cc3d14c98)
***
# Introduction
We test the openpilot system in some real-world cases and find it can indeed achieve level 2 autonomous driving on a single device.   
We reimplement the key supercombo model of openpilot from scratch, and test it on public datasets. The reimplemented model is comparable with the original one. !

* [Directory Structure](#directory-structure) 
* [Changelog](#changelog) 
* [Quick Start](#quick-start-examples) 
    * [Installation](#installation)
    * [Dataset](#dataset)
    * [Training](#training)
    * [Demo](#demo)
* [Citation](#citation) 
* [License](#license)  

***
# Directory Structure

```
openpilot-reimplementation 
├── tools           - Generate image data from comma2k19 and nuScenes.  
├── utils_comma2k19 - comma2k19 dataset processing code.  
├── data            - link to the nuscenes-all/comma2k19 dataset 
```
***
# Changelog

2022-6-10: We released the v1.0 code for Openpilot-reimplementation.

***
# Quick Start Examples
Before starting, you can read the [arXiv](https://www.overleaf.com/project/626954666328026cc3d14c98) paper to understand the details of our work.
## Installation
Clone repo and install requirements.txt in a [Python>=3.7.0](https://www.python.org/) environment, including [PyTorch>=1.7](https://pytorch.org/get-started/locally/).

```
https://github.com/OpenPerceptionX/openpilot-reimplementation.git  # clone
cd openpilot-reimplementation
pip install -r requirements.txt  # install

```
## Dataset
We train and evaluate our model on two datasets, [nuscenes](https://www.nuscenes.org/nuscenes) and [Comma2k19](https://github.com/commaai/comma2k19).
The table shows some key features of them.

## Training
By default, the batch size and the learning rate are set to be 48 and 1e-4, respectively. A gradient clip of value 1.0 is applied. During training, you can use 4 or 8 NVIDIA V100 GPUs(Multi-GPU times faster). Since there is a GRU module, you need to initialize its hidden state by filling zeros. When using 8 V100 GPUs, it takes approximate 120 hours to train 100 epochs on Comma2k19 dataset . On a single NVIDIA GTX 1080 GPU, the network can inference at a speed of 100 FPS.

## Demo

***
# Citation
Please use the following citation when referencing our repo or [arXiv](https://www.overleaf.com/project/626954666328026cc3d14c98).
```
TODO

```
***
# License
All code within this repository is under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0).
***

