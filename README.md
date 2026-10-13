# AlexNet, Explained

**Live site:** https://fernfant.github.io/alexnet-explained/

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Fernfant/alexnet-explained/blob/main/build_your_own_alexnet.ipynb)

In 2012, Alex Krizhevsky, Ilya Sutskever and Geoffrey Hinton trained **AlexNet** for 5–6 days on two NVIDIA GTX 580 gaming cards. It cut the ImageNet top-5 error from 26.2% to 15.3% and kicked off the deep learning boom.

This repo explains how it works for a 15-year-old, then lets them build one.

## What's inside

| File | What it is |
|---|---|
| `index.html` | Six short animated episodes (canvas, no dependencies) with captions, optional narration, a 3-question quiz per episode, saved progress, and a hands-on Filter Lab |
| `build_your_own_alexnet.ipynb` | Episode 7: a hands-on PyTorch notebook for Google Colab's free GPU |

## The notebook (about 15 minutes on a free T4 GPU)

1. **Meet the real AlexNet:** load the pretrained model, classify your own photos, slide your own 3×3 filter over a photo, and view the 64 filters it learned.
2. **Build TinyAlexNet from scratch:** 5 conv + 3 dense layers, ReLU, dropout and data augmentation, trained on CIFAR-10.
3. **Real-world project, Pet Breed Detector:** transfer learning on the Oxford-IIIT Pet dataset (37 breeds), launched as a Gradio web app with a shareable link.

Each part has "Predict first" prompts and ends with a "Check yourself" quiz. Then come challenges: SGD vs AdamW, removing tricks to see overfitting, fine-tuning, ResNet-18, and training on your own photos.

## Run it

Click the Colab badge, then choose `Runtime → Change runtime type → T4 GPU` and run the cells in order.

## Facts used

- Krizhevsky, Sutskever & Hinton, *ImageNet Classification with Deep Convolutional Neural Networks*, NeurIPS 2012
- 8 learned layers, ~60M parameters, 650K neurons, 1.2M training images, 1,000 classes
- Note: torchvision's AlexNet is the single-GPU variant (64 first-layer filters instead of 96)

## Licence

MIT
