# Deep_STORM


## Paper Overview

### Abstract
1. Obtaining super-resolution images from stochastically blinking emitters used for localization microscopy
2. Deep-STORM uses a deep convolutional neural network that can be trained on simulated data or experimental measurements
3. The method achieves state-of-the-art resolution under challenging signal-to-noise conditions and high emitter densities and is significantly faster than existing approaches
4. No prior information on the shape of the underlying structure is required

### Introduction
1. Localization microscopy relies on acquiring a sequence of diffraction-limited images, each containing point-spread functions produced by a sparse set of emitting fluorophores
2. The emitters are localized with high precision
3. By combining all of the recovered emitter positions from each frame, a super-resolved image is produced

1. Regions with a high density of overlapping emitters pose an algorithmic challenge(overlapping PSFs)
2. All existing methods suffer from two fundamental drawbacks: data-processing time and sample-dependent parameter tuning

1. Here, we employ a fully convolutional neural network for super-resolution image reconstruction from dense fields of overlapping emitters
2. Our method, dubbed Deep-STORM, does not explicitly localize emitters. Instead, it creates a super-resolved image from the raw data directly
3. Deep-STORM is parameter free, requiring no expertise from the user, and is easily implemented for any single-molecule dataset, not dependent n prior knowledge of the sample

### Method
1. Deep-STORM utilizes an artificial neural net that receives a set of frames of (possibly very dense) point emitters
2. Outputs a set of super-resolved images (one per frame), based on prior training performed on simulated or experimentally obtained images with known emitter positions
3. The output images are then summed to produce a single super-resolved image.

## Installing Dependencies(Local environment)
1. An environment.yml file is given. Use ``` !conda env create --force -f environment.yml ``` in the terminal to make the environment. The name of the environment is *deep-storm*
2. Some issues I faced while installing were inconsistencies in the following: ```- icc_rt=2019.0.0```, ```- intel-openmp=2019.5```, ```- vc=14.1```, ```- vs2015_runtime=14.16.27012```. I also faced issues in resolving the environment hence used --force.
3. I made the following corrections to the environment.yml file as the environment was not getting resolved, the modified version is environment2.yml.

## Colab
1. Due to RAM limitations on colab, I changed the parameter of *num_patches_per_frame* from 500 to 200. *All* other parameters were kept the same.
2. The model created by the samle data, called *SampleData_model* is listed here for further use.

### 1st iteraton on Sample data BIN 10
1 This was run successfully with results saved in google drive folder *
