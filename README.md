# Image Segmentaion for yeast cells using Mask-RCNN
**EPFL | [Machine Learning (CS-433)](https://www.epfl.ch/labs/mlo/machine-learning-cs-433/) | Fall 2019 | Project 2**  
**EPFL | [Laboratory of the Physics of Biological Systems](https://www.epfl.ch/labs/lpbs/)**

![Python 3.7](https://img.shields.io/badge/python-3.7-blue.svg)
![tensorflow 1.13.1](https://img.shields.io/badge/tensorflow-1.13.1-yellow.svg)
![keras 2.2.0](https://img.shields.io/badge/keras-2.2.0-red.svg)

## About
- This is our implementation of Mask-RCNN for yeast cells image segmentation. This is part of the second course project in the Machine Learning course at EPFL. The whole project is an interdisciplinary ‘Machine Learning for Science’ projects, where we cooperate with researchers at Laboratory of the Physics of Biological Systems to help them segment yeast cell bodies in microscope images using a hand-annotated image set through some machine leaning techniques.
  - **Team name**: DayDreamers_WXY
  - **Team members**: Wei Jiang: wei.jiang@epfl.ch; Xiaoyu Lin: xiaoyu.lin@epfl.ch; Yao Di: yao.di@epfl.ch
- Other methods: we also utilize U-Net for the same task, the code is provided [here](https://github.com/Jiang15/Machine-Learning-Project).
- [[report](report.pdf)]

## Methond Description
This is an implementation of Mask-RCNN method for yeast cell image segmentation. The model generates segmentation masks for each instance of yeast cell in the image. The implementation is based on [Mask-RCNN](https://github.com/matterport/Mask_RCNN).

## Instruction
### Requirements
- python 3.7, keras 2.2.0, tensorflow 1.13.1 
- other common packages listed in requirements.txt

### Folders and Files
- `codes`: contains python code developed for the project
  - `yeastSegHelpers`: contains helper file for segmentaion, tile and quality measurement
  - `train.py`: run this file to train the model
  - `detection.py`: run this file to apply the trained model to given image files in `dataset\test\frame` and save the generated mask in              `dataset\test\mask\results.tif`
  - `evaluation.py`: evaluation the generated mask by `detection.py`
  - `yeastcell.py`: condtains configuration of model training and some helper functions to load and pre-process data
- `logs`: contains logs of training
- `models`: contains models generated by `train.py`
- `dataset`: contains all the dataset for training, validation and test.
  - `test`: constains dataset for test, please place original frames in `frame` folder.
  - `train`: constains dataset for training, please place original frames in `frame` folder, and corresponding mask in `mask` folder
  - `validation`: constains dataset for validtion, please place original frames in `frame` folder, and corresponding mask in `mask` folder
  - **Note:** for train and validation datasets, the name of original frames shoud contain 'im' or 'frames' ,and the corresponding mask shoul replace 'im' or 'frames' by 'mask' and keep the rest of name the same. For example: *augoustina_first_im.tif* and *augoustina_first_mask.tif*.
  
## Getting Start

- Place datasets in the corresponding folders
- Run `train.py` train the model according to given dataset
- Run `detection.py` apply trained model on test dataset 
- Run `evaluation.py` get quality measurements of trained model.
