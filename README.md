# Face_Generation_What-s_under_the_Mask


In this project, our ideal goal is to take images of someone wearing a mask and replace the mask with an accurate representation of their actual face. We hope to have a high resolution output image that would be believable to the untrained eye. We would also like to use a variety of data to train our model. Faces are very unique and we would like to have a very general output.

We have a few constraints working against us. Those being time, data, and compute power. Due to these constraints, we also have a more modest goal. We should be able to generate unmasked images that, at the very least, look like a face. We also acknowledge that our only dataset, at this point, consists of celebrities and may not provide a generalized output. We may also have to reduce the resolution of our output images in order to speed up training.



Data set: [Celeb A Masked Dataset](https://drive.google.com/drive/u/0/folders/0AEwbUGNR0CrkUk9PVA)

We will be working with the CelebA dataset available to the public on Kaggle. Here is the URL to the dataset:https://www.kaggle.com/datasets/jessicali9530/celeba-dataset (accessed 11/28/2022). This source consists of 202,599, cropped and aligned, celebrity face images. This dataset also provides facial landmark data. This is important because we plan to create our own masked image dataset from CelebA. We will use an existing tool, ‘mask2face’ created by STRV to create this new masked face dataset. The tool is available to use by the public here: https://github.com/strvcom/strv-ml-mask2face. The tool will make use of the facial landmark data to position the synthetic mask onto the image taken from CelebA.

Initially it was ran the tool on the images and were able to generate about 7000 train and test images, though we only ended up using the train images since it takes up a lot of space.

Deep learning techniques/architectures:


At a high level we plan to use a GAN model to try and generate the face behind the mask. This will consist of two networks working together to produce a realistic image. There will be a Generator and a Discriminator network. They will be combined to form our GAN model. 

The generator will make use of various convolutional methods to produce an image derived from noise. The Discriminator will be acting as a sort of automated supervised learning. It will decide whether or not the Generator’s output is realistic enough to be accepted. We plan to use a convolutional image binary-classifier to achieve this functionality. The binary decision being whether or not the Generator’s output is real or not. We feel fairly experienced in the realm of image classification and are interested in using some of the methods we have used throughout this course. For example, implementing a discriminator using a Siamese network seems interesting.






