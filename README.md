# Sketch To Face
Turn your sketches into realistic portraits

![teaser](https://user-images.githubusercontent.com/102770811/236662164-b0f79cfa-a4d3-4bd4-b037-6a4f6d31589d.jpg)

# Abstract

An AI model that uses deep learning techniques to generate high-quality face images from freehand sketches. The model is trained on a large dataset of sketch-image pairs, which enables it to learn how to convert rough sketches into realistic face images. The system employs a multi-stage synthesis pipeline that gradually adds more details and textures to the generated images. This pipeline consists of multiple stages that refine the image at increasing levels of detail, resulting in a final output that closely matches the input sketch.
To ensure that the generated images are of high quality, It uses a perceptual loss function that encourages the generated images to match the features of real face images. This function is based on a deep neural network that is trained to recognize human faces, and it helps the system produce images that are visually appealing and realistic. Additionally, it uses a smoothness constraint that promotes smooth transitions between neighboring pixels, which helps to eliminate artifacts and other visual imperfections in the generated images.

# Installation

1.System
- Ubuntu 16.04 or later

- NVIDIA GPU + CUDA 9.2

2.Software
- Python 3.7

- Jittor

```
sudo apt install python3.7-dev libomp-dev

sudo python3.7 -m pip install git+https://github.com/Jittor/jittor.git

python3.7 -m jittor.test.test_example
```

- Packages

```
sh install.sh
```

# How to use

To use the sketch to image interface, you will need to download a pre-trained model and place it in the correct directory. Follow these steps:

- Download the pre-trained model from either [Baidu](https://pan.baidu.com/s/1f1S9t4T5X5J0CDZ7AqTfMg) or [Google Drive](https://drive.google.com/drive/folders/15I41zrFr_srq03YnijLSEsy5byGOLsyZ). If you downloaded from Baidu, the password to access the file is "wiu9".

- Extract the downloaded file and locate the model file. The file should have an extension of .pt.

- Create a directory called "Param" in the root directory of the project.

- Place the downloaded model file into the "Param" directory.

```
python3.7 demo.py
```

# Project Details

```
├──  heat - this foler cointains the face structure images
│    
│
├──  configs - This folder contains autoencoder model, facial part codes and the main Functions.
│    └── AE_Model.py
|    └── Combine_Model.py
|    └── networks.py 
│    
│
├──  options - This folder contains configuration files for the model.
│    └── AE_face.py 
│    └── parts_combine.py  
|
|
├──  params - This folder contains saved model parameters obtained by training a the model.
│    └── AE_whole 
|    └── Combine
│
│
├──  test_input - This folder contains the input images of the model.
│
│
├──  test_output - This folder contains the output images of the model.
```

# Project Structure

A deep neural network architecture that consists of multiple layers. The model takes as input a freehand sketch of a face and generates a high-quality image of a face that closely matches the sketch. The network architecture includes several key components, which described below.

- Sketch Encoder: The first component of the network is a sketch encoder, which takes the input sketch and encodes it into a high-dimensional feature vector. This encoder is typically a convolutional neural network (CNN) that has been trained to extract features from images.

- Residual Blocks: The second component of the network is a series of residual blocks, which are used to refine the generated image at increasing levels of detail. Each residual block consists of multiple convolutional layers, which help to extract features from the input and produce a more detailed output.

- Texture Encoder: The third component of the network is a texture encoder, which is used to capture the texture features of the generated image. This encoder is also typically a CNN that has been trained to extract texture features from images.

- Decoder: The fourth component of the network is a decoder, which takes the output of the residual blocks and the texture encoder and produces the final output image. The decoder typically consists of several upsampling layers, which increase the resolution of the image, and several convolutional layers, which help to refine the output.

- Perceptual Loss: The fifth component of the network is a perceptual loss function, which is used to ensure that the generated image closely matches the input sketch and real face images. This loss function is based on a pretrained deep neural network that has been trained to recognize human faces.

- Smoothness Constraint: The final component of the network is a smoothness constraint, which is used to promote smooth transitions between neighboring pixels in the generated image. This constraint helps to eliminate artifacts and other visual imperfections in the output.

# Contribution

Henry Azer made a valuable contribution to the project by cleaning up the original code and fixing some issues. By doing so, Henry likely improved the readability, maintainability, and overall quality of the codebase. This type of contribution can be particularly valuable in large or complex projects, where code can become difficult to read and understand over time.

# Citation

```
@article{chenDeepFaceDrawing2020,
    author = {Chen, Shu-Yu and Su, Wanchao and Gao, Lin and Xia, Shihong and Fu, Hongbo},
    title = {{DeepFaceDrawing}: Deep Generation of Face Images from Sketches},
    journal = {ACM Transactions on Graphics (Proceedings of ACM SIGGRAPH  2020)},
    year = {2020},
    volume = 39,
    pages = {72:1--72:16},
    number = 4
}
```
