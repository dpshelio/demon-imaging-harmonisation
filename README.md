# DEMON ECR lecture "Harmonisation strategies for multi-centre imaging studies"

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/HealthBioscienceIDEAS/demon-imaging-harmonisation/HEAD)

## Overview
This lecture will cover various techniques for hwo to appropriately handle imaging data acquired from multiple sites and scanners. 
Differences in hardware, software and acquisition parameters between scanners can lead to diferences in the resulting imagedata. 
These differences include:

* _Resolution differences_ in terms of what effective resolution a scanner is able to acquire data
* _Intensity/contrast differences_ in temrs of the signal to noise ratio and contrast between tissue types
* _Geometric differences_ in terms of changes in shape that occur due to various non-linearities in the gradient and shims.

These differences between scanners can ultimately lead to differences in the outcome measures, so if an individual
was scanned at site A and then again the next day at site B, there would be potential differences in the measurement.
While of course some of these differences would simpy be measurement error, there are also systematic differences between the sites that would lead
to bias and or differences in variability (heteroskedascity). 
Methods for reducing or removing these sources of systematic error arising from multiple scanners/sites are called harmonisation. 
There are many opportunities for harmonisation, from prospecitvely tuning the acquisition parameters from the different sites 
to ensure that the resulting images have properties that are as similar as possible to each other, to adaptive processing pipelines
that harmoinse the images before analysis to adjusting for these differences between sites/scanners through statsitical models.
Each approach has its place, with potential benefits and drawbacks, but they can also be used in a combined harmonisation strategy.

In the lecture below, we will:
* Give some example differences between scans from a single subject but acquired on a different scanner
* Show some visualisations of QC and pre-processing metrics that can help identify 
* Do a simple linear regression where site is included as a covariate
* Do a more advanced harmonisation approach using Combat

## Setup
This lecture is intended to be a [Binder-ready](https://mybinder.org/) repository (add links to Binder). This means that the repository with the Jupyter notebook will created as a 
Docker container and then accessible via the web. Thus it should not require any more requirements than a network connection.

If you are intereste in running this on your local environment, please investigate the local ennvironment page. The dependencies will be: 
* fsleyes - for viewing images within the notebook - if possible, otherwise use matplotlib or other image plotting libary
* niftyreg (C++) - for doing image registration
* nipype - for running registrations in python
* Python package for linear regression (pandas,scikit-learn?)
* [ComBat](https://github.com/Jfortin1/ComBatHarmonization) - for running harmonisation

## Difference in acquisition
Cover why images are different even if the same individual - physiological noise, instrument noise, differences in hardware, differences in software. The gold standard of identifying these differences is often a travelling head study, where a small handful of individuals are scanned at mulitple sites. 
The first part fo the demo will be to look at two scans from the same individual on a different scanner, regisgter them and then show shape/intensity/geometric differences.
Potential data sources: Cardiff traveling head data, UCL Prisma upgrade, GENFI examples.

## harmonisation of acquisition
The gold standard of doinf this is so that optimisation  will be included and matching the resulting images, not the parameters themselves, so ta
from multi-site studies. MRI and PET scanners. Talk about ADNI MRI core approach and TRACK-HD.

## Harmonisaiton of processing
Another aspect differences in resolution. Discuss ADNI approach of lowest common denominator of resolution in PET.
Example ADNI PET images before and after resolution smoothing.

## Basic example of linear regression using site as covariate
Show some exampels from GENFI VBM, take example spreadsheet from ADNI and show differences in site between PET scanners.

## COMBAT approach
Same as above, but showing advantages of COMBAT and why it woud be useful, especially when numbers are small. 

## References
List of papers and datasets.
