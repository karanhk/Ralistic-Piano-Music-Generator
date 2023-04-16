# Disclaimer

I admit that the video or gameplay used is obtained through youtube and may under copyright protection. Such usage is completly inadvertent. It is quite possible that i overlooked to give full scholarly credit to the copyright owners. I believe that the non-commercial, only-for-education use of the material may allow the video in question fall under fair use of such content.

# About

## Abstract

This repository proposes a model which can generate realistic piano music without human interaction using General Adversarial Network (GAN) proposed by Ian Goodfellow in 2014. This model generates piano music of 37 seconds from a latent vector of size 14. It is trained on <a href="https://www.kaggle.com/datasets/jackvial/themaestrodatasetv2">MAESTRO V2 dataset </a>. The model is built with `Tensorflow` and completly implemented in `Python`.

This generated music has many applications. In below video, i used generated music as background music for mario game.


https://user-images.githubusercontent.com/76246981/232266962-758e25b0-41e8-472e-9cc9-409ef7dab781.mov

## Detailed

This repository proposes a deep learning model which generates realistic piano music without human interaction from a latent vector of size 14 using General Adversarial Network (GAN). The `midi2img.ipynb` convertes midi files to image, this image is the pitch vs time distribution of that midi file in the `png` format. The `midi2image.ipynb` takes 300 notes of midi and generates distribution accordingly, the number of notes can be changed as per convience. These `png` images is the training dataset for model. The model generates `png` image and this image is converted to `midi` using image2midi.
The `midi2image.ipynb` and `image2midi.ipynb` files are taken from <a href="https://github.com/mathigatti/midi2img">midi2image</a> repository.

This images are fed to proposed model. The generator learn the distribution and generates the fake distribution, on the other hand discriminator discriminates between real (actual) and fake (generated) distribution. The training is stopped when if the discriminator classifies each distribution with probabiility 0.5 (approximatly after 3000 iterations). At this point the generator perfectly learns the distribution and can generate new identical distribution.

The GAN has two models, generator and discriminator. The generator has 3 Convolutional layers, 3 Upsampling layers and one dense layer with leaky ReLU activation. The generator takes input as latent vector of size 14, then generates the images of size 106x300x1. The discriminator discriminator between real and fake distributions, it has 5 Convolutional layers and one dense layer with Leaky ReLU and sigmoid activation. The discriminator takes input images of size 106x300x1 and classifies it as real or fake.

# Highlights

Full Video <a href="https://drive.google.com/file/d/1NYg_Z4_gVGdsUMXpheTuY6lZz2jrWhcM/view?usp=sharing"> Link </a>

The generated `midi` file   <a href="https://drive.google.com/file/d/1xqsWSK9aoe1HrTNwekgMcjeRkvuOYn4i/view?usp=sharing"> Link </a>

The generated `wav` file    <a href="https://drive.google.com/file/d/1N1_APalG3YtQVYZkLdZk49K1zgXDu_1Y/view?usp=sharing"> Link </a>

The generator model   <a href="https://drive.google.com/file/d/1JBs3Hoa3dm5aGrNrPfWSqmGeW0Yxro0D/view?usp=sharing"> Link </a>

Pitch vs time distribution of generated file

<img width="497" alt="Screenshot 2023-04-13 at 2 26 12 PM" src="https://user-images.githubusercontent.com/76246981/231954874-40aa4d35-4aba-4a16-927e-565b1975c558.png">

The generator

<img width="512" alt="Screenshot 2023-04-13 at 2 30 24 PM" src="https://user-images.githubusercontent.com/76246981/231955239-ab1404e8-d28f-4ec0-932d-05897e2cbf21.png">

The discriminator

<img width="521" alt="Screenshot 2023-04-13 at 2 30 45 PM" src="https://user-images.githubusercontent.com/76246981/231955277-f8071be6-196f-4483-959b-7193b52190a5.png">

# Prerequisites

`Python>=3.6`

# Getting started

1. Download the repository and unzip it.
2. Install necessary packages using `pip install -r requirements.txt`.
3. Run the `load_model.ipynb` to generate `png` images and after that run `img2midi.ipynb` to convert it into `midi` files.
4. If you want to convert midi to wav, run `midi2wav.ipynb` file.
5. Read the `instructions.txt` for better understanding of repository.

# Future work

In future, i'm looking forward to generate realistic music with multiple instruments.

# Credits
<a href="https://github.com/mathigatti/midi2img">midi2img</a> repository for midi to image and image to midi.

# Connect with me

Give your feedback at : karanhadiyal65@gmail.com
