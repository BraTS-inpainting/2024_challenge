# Evaluation of Inpainting Submissions

During the challenge validation phase, the participant gets access to the validation dataset. The participant model then solves the inpainting tasks on this dataset and the resulting images can be uploaded (multiple times) to Synapse for evaluation. You can download the validation set [here](https://www.synapse.org/#!Synapse:syn51684975).

This sub-repository complements [the general Synapse wiki page](https://www.synapse.org/Synapse:syn53708249/wiki/627752) on validation submissions for our specific inpainting challenge. Make sure to also read through the general Synapse page!

## File Formatting

All files in the inpainting output folder should have the following format: ```BraTS-GLI-XXXXX-YYY-t1n-inference.nii.gz``` where XXXXX indicates the case ID and YYY the time point (compare to the Synapse submission tutorial).

An exemplary result folder could look like this:

```ASNR-MICCAI-BraTS2023-Local-Synthesis-Challenge-Validation-Results```
- ```BraTS-GLI-00000-000-t1n-inference.nii.gz```
- ```BraTS-GLI-00002-000-t1n-inference.nii.gz```
- ```BraTS-GLI-00003-000-t1n-inference.nii.gz```
- ```BraTS-GLI-00005-000-t1n-inference.nii.gz```
- ```BraTS-GLI-00006-000-t1n-inference.nii.gz```
- ...

For each folder in the given validation set, we expect the participant script to generate exactly one result file where the voided t1 file (```t1n-voided.nii.gz```) is in-painted. 
The result folder can then be uploaded to Synapse. For more information see [the Synapse submission tutorials](https://www.synapse.org/Synapse:syn53708249/wiki/627752).

## Evaluation Metrics
To measure the performance of the contributions, we will evaluate the quality of the inpainted regions. Among others, we will use the following well-established metrics to quantify how realistic the synthesized image regions are compared to real ones:
- [structural similarity index measure](https://torchmetrics.readthedocs.io/en/stable/image/structural_similarity.html) (SSIM)
- [peak-signal-to-noise-ratio](https://torchmetrics.readthedocs.io/en/stable/image/peak_signal_noise_ratio.html) (PSNR)
- [mean-squared-error](https://torchmetrics.readthedocs.io/en/stable/regression/mean_squared_error.html) (MSE)

The above metrics are only evaluated in the regions that are to-be-inpainted (the ```mask.nii.gz``` file).

## Requirements
- Download the training and/or validation dataset from [Synapse](https://www.synapse.org/Synapse:syn59809688) and unzip it into the root of this repository (```2024_challenge/```)
- Download the trained baseline model from [here](
https://syncandshare.lrz.de/dl/fiWmxMzsnrWyY3yAja85JE/lightning_logs.zip) and unzip it into ```2024_challenge/baseline/``` (this folder).
- Create a new python environment. We recommend python version 3.10
- Check your cuda version ```nvidia-smi``` (top right)
- Install required python packages:
  - ```torch``` and ```torchvision``` which are compatible with your cuda version (See https://pytorch.org/). Note however, that for ```pytorch<1.13```, you might encounter [issues](https://github.com/BraTS-inpainting/2023_challenge/issues/1) with our code. Use ```pytorch>=2.0.0``` if possible
  - ```pytorch-lightning```
  - ```matplotlib nibabel torch json yaml jupyter scipy tqdm inpainting```

## Getting Started

In ```evaluation.ipynb```, you will find exemplary code that lets you generate properly format result files based on your model (we use the baseline model as example). For transparency, we also demonstrate how the server side evaluation script works (this is completely optional).


