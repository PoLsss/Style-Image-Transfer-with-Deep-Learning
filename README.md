# Style Image Transfer with Deep Learning

Welcome to the Style Image Transfer project! This project showcases the application of deep learning techniques to transfer the style of one image onto another. The project includes a web-based demo that allows users to experience style transfer in real-time.

## Introduction
Style image transfer involves using neural networks to apply the artistic style of one image to the content of another image. This project leverages state-of-the-art deep learning models to achieve high-quality style transfer. The web demo allows users to upload images and apply different artistic styles to see the results in real-time.


## Demo

Demo 1vs1

https://github.com/PoLsss/DemoImg/assets/98370447/a5c2a35f-0507-411f-a562-dcf6ccd869c1

Demo 1vs1vs1

https://github.com/PoLsss/DemoImg/assets/98370447/1f936024-39b5-45ce-b2a8-0e6a80a6f391

And some generated result pictures.
| <div align="center">Style</div> | <div align="center">Content</div> | <div align="center">Generated</div> |
|:-|:-|:-|
|![1](https://github.com/PoLsss/DemoImg/assets/98370447/843f69d3-6ff1-458e-8837-8303b485d46d)| ![ori1](https://github.com/PoLsss/DemoImg/assets/98370447/48ffef5f-9e4f-47c2-b8e5-81b5b3dac261) |![1-result](https://github.com/PoLsss/DemoImg/assets/98370447/5e7d30c8-3f56-48ee-99de-6b3cd4812d97) |
|![2](https://github.com/PoLsss/DemoImg/assets/98370447/a99a5cf0-7cc7-493c-b743-22f565c7f621) | ![orri2](https://github.com/PoLsss/DemoImg/assets/98370447/29c9b7bf-f41c-4ed9-a9d6-67ef48c7dbe0)| ![re2](https://github.com/PoLsss/DemoImg/assets/98370447/e8615da4-733a-47d9-86c5-da147771b26a)|
|![3](https://github.com/PoLsss/DemoImg/assets/98370447/077b727b-770a-48d8-800d-77e14b65acdc)|![ori3](https://github.com/PoLsss/DemoImg/assets/98370447/0717d270-f323-4293-ab51-bfd6a47f797d) | ![re3](https://github.com/PoLsss/DemoImg/assets/98370447/308f4fdd-6ed3-4822-ac16-4656bc183bdb)|



## Neural Style Transfer

**Goal:** Transforming your photos into artistic style images is something that surprises and delights everyone. However, for those who have researched deep learning networks, this is a fairly familiar and basic technique of Deep Learning networks called Neural Style Transfer. (Refer to https://arxiv.org/abs/1508.06576)

**What is Neural Style Transfer?**


<img src="https://github.com/PoLsss/DemoImg/assets/98370447/ad3128f4-96ec-4a27-8fa8-586165ff28ca" alt="1-result" width="500" height="300"/>


To define it more specifically, initially, we will have two images: Content image (C) - containing the main content information, and Style image (S) - containing the texture style. Neural Style Transfer is a deep learning model that can combine these two images to create a generated image (G). **The generated image has the exact content of the Content image but embodies the style of the Style image.**

**Main idea:**
We will use a Convolutional Neural Network (CNN) to analyze the images and learn the deep features of the images. However, unlike other problems, with Neural Style Transfer, we will not try to optimize our neural network; instead, we will try to optimize our output (generated image). Our optimization will be based on minimizing the total loss of:
- The difference between the Content image and the Generated image (Content Image vs Generated Image)
- The difference between the Style image and the Generated image (Style Image vs Generated Image)
- The variation of the Generated image (Variation of Generated Image)

In other words, when our generated image achieves the smallest loss, it means it will definitely resemble both the content image and the style image. Depending on how we declare the coefficients for the components of the loss function, the generated image will differ. All three images are fed into a pretrained CNN model to extract deep features:
- For the content_image, extract the features called content_features
- For the style_image, extract the features called style_features
- For the generate_image, extract the features called generate_features

Based on these features, we calculate the distance or difference to determine the total loss between the images:
Loss = D(generate_features, content_features) + D(generate_features, style_features)

Where:
D(generate_features, content_features): is the difference between the generate_image and the content_image
D(generate_features, style_features): is the difference between the generate_image and the style_image

Use the Gradient algorithm to update the generate_image. The process will loop to optimize the value of the Loss function.  

** *The smaller the Loss function, the more similar the generated image is to the content and style images.* **



## Features
- Real-time Style Transfer: Apply different artistic styles to your images instantly.
- Multiple Pre-trained Models: Use various pre-trained models for different styles.
- User-friendly Interface: Easy to use web interface for uploading images and selecting styles.
- Customizable: Extend the project with your own style images and models.

## Technologies Used
- Python: Core programming language.
- TensorFlow / PyTorch: Deep learning frameworks used for model training and inference.
- HTML/CSS/JavaScript: Frontend technologies for the web interface.





