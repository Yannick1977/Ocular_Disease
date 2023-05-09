# Ocular_Disease

These notebooks in this repo have been developed to create prediction models for the ODIR19 dataset.
This dataset is decomposed in the following way:
- an xls file describing the pathology of the patient and the name of the associated image files
- directory containing all the images

Each notebook has a role that will be detailed below.
 
## Annotation Preprocessing
 
The dataset xls file provides a diagnosis by an individual and an annotation for each eye.
The goal is to establish a diagnosis by eye from the annotations.
This analysis will be decomposed as follows:
- count the number of diagnoses per individual excluding the "Normal" diagnosis
- temporarily exclude individuals with multiple diagnoses
- List the keywords by pathology
- Exclude images with a poor quality description
- Creation of a new xls file 

## Image Preprocessing

This notebook will process the dataset images.
The images have different sizes and have been acquired by different equipments with different characteristics.
The processing of the images is decomposed in the following way:
- removal of unnecessary spaces: removes black pixels
- equalize the images in order to obtain identical contrasts 
- resize the images to 224 * 224 pixels

## Data Augmentation

As seen in the first step, it should be noted that the classes are unbalanced.
This notebook will reequilibrate these classes by using the generators of the keras library
All the images are saved in a numpy array for learning process

## Convolutionnal Network Learning

This notebook will allow you to learn the model from the previously created numpy tables.
It is possible to perform the learning either by defining a basic model or a list of basic models.
After the training, the model is saved.

## Model Performance

This notebook will calculate the performance for each model. It will then compute the confusion matrices of each model and compare the different performances of each model.
