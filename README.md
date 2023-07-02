## Coding3 - Final Project - Ying Tao

#### Github Link：



#### Video Link：



#### Project Objectives

The training and testing of the pix2pix model based on CGAN aims to convert abstract character line drawings into Rembrandt-style paintings. Rembrandt was a great Dutch artist, known for his unique light and shadow effects, detailed portraits and expressive brushwork. By translating the character line drawings into Rembrandt's style, we were able to reinterpret Rembrandt's artistic style in new and interesting ways.

This project is significant in terms of artistic value. Artistic style transfer technology can provide artists and designers with a creative tool to help them realize artistic creation in a faster and more efficient manner. By transforming abstract line drawings of characters into Rembrandt-style paintings, we are able to create artistic and expressive images that bring a unique visual experience to the viewer. This artistic style transformation can not only provide entertainment and beauty, but also stimulate the imagination of creators and provide new possibilities for artistic expression.

Technically, the CGAN-based pix2pix model provides us with a powerful tool for artistic style transfer. By training the generator and discriminator networks, we are able to generate realistic and Rembrandt-like images through adversarial training. The generator network is responsible for converting the input character line drawing into an artistic style image, while the discriminator network is used to evaluate the realism of the generated image. This approach to generative adversarial learning allows us to train models capable of generating high-quality, artistic images.

#### Machine Learning Method

The pix2pix model based on Conditional Generative Adversarial Network (CGAN) is a deep learning model for image conversion tasks. It can convert an input image to a desired output image, such as converting a black and white line art image to a color image, converting a semantically segmented image to a real image, etc.

The basic idea of the pix2pix model is to achieve image transformation by training a generator network and a discriminator network. The generator network is responsible for converting the input image into an output image, while the discriminator network is responsible for judging whether the generated image is real or not. Through adversarial training, the generator and the discriminator compete with each other and make progress together to achieve the goal of generating realistic images.

#### Code Referenced

pix2pix：

https://phillipi.github.io/pix2pix/

https://github.com/phillipi/pix2pix/tree/master

https://github.com/hlzy/pix2pix-keras

Tool for pix2pix:

https://github.com/affinelayer/pix2pix-tensorflow

#### Data Set

The data set of Rembrandt's paintings is selected, which contains 300 Rembrandt's related paintings and corresponding abstract line drawings. The data set is divided into three parts: train, val, and test. The train data set contains 200 images of 512*256, in which the image is composed of abstract line drawings with a length and width of 256 and paintings with a length and width of 256. The val dataset contains 100 images of the same type as the train. The test data set consists of an image with a length and width of 256, which independently stores line drawings and paintings.

Each sample in the data set consists of a pair of images: an abstract line drawing and an original painting. In training, the left side is used as input and the right side is used as output to train a generative model that generates Rembrandt-style paintings from line drawings.

![0](.\photo\0.jpg)

original data set:

https://cmp.felk.cvut.cz/~tylecr1/facade/

The data set I used:

https://www.kaggle.com/datasets/grafstor/rembrandt-pix2pix-dataset

There are other similar datasets:

http://www.ipb.uni-bonn.de/projects/etrims_db/

#### Model Training

My code trains a Conditional Generative Adversarial Network (cGAN) for image-to-image translation tasks. The cGAN consists of two main components: a generator model and a discriminator model. The generator is based on a U-Net architecture that downsamples an input image into a compact latent representation and then upsamples it back to the original size, with "skip connections" between the corresponding down- and up-sampling layers to preserve spatial details. The discriminator is a PatchGAN, designed to classify if each image patch is real or synthesized. The models are trained concurrently, where the generator aims to fool the discriminator by generating realistic images while the discriminator tries to differentiate between real and generated images. This adversarial process leads to the generator improving its performance over time. Data augmentation techniques are applied to increase the diversity of training data. The loss function includes both the standard GAN loss (binary cross-entropy between real and fake predictions) and an L1 loss between the generated and target images, which encourages the generator to create images that are structurally similar to the target images. The entire process is iterated for several steps, with checkpoints saved periodically.

![0](.\photo\2.jpg)

#### Training results and testing

模型训练完成之后，可以恢复到最近的检测点方便后续继续使用模型。在模型测试环节，使用256*256的抽象线稿，由模型生成对应的图像画作，并与实际画作做对比。

在模型训练40000步之后，基本可以还原画作的大致样貌，只有少数的脸部细节尚且无法还原，可以需要更多的数据集以及更多的训练过程来继续完善模型。

![0](.\photo\1.jpg)

```

```

