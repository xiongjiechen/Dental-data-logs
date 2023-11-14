# Data logs for dental disease detection

A diagram that provides an overview of the data repository on Teams can be found in [this google slide](https://docs.google.com/presentation/d/1CsW2adn97tSmq5DyrZnu1ePAUd11GN72_CcipZ8SqeM/edit#slide=id.p). A more detailed description can be found in [this google spreadsheet](https://docs.google.com/spreadsheets/d/1PwtbtwETX94yi6laZgHlAJY_YeR8rVdDJBKiJrUvJxI/edit#gid=276289149).

This document is created to record and explain the change of the data repository for the dental diseas detection project. The data repository contains dental X-rays and their annotations, along with some processing codes and ipynb files. The current version of this document will only cover the structure of the folder where the collected dental X-rays and annotations are stored in.  

Both dental X-rays and their annotations are stored at “**Dental Disease Detection Files/Documents/General/NEW DATASETS AND PROCESSING SCRIPTS/1. Disease Object Detection**” on Teams, referred as “**./**” below. The “**./**” folder consists of four subfolders:
- **1-RAW-DATA**
  - Contains all the dental X-rays.
- **2-COMBINED DATASETS**
  - Contains filtered dental X-rays, with overexposed and non-radiograph images removed. Some files in this subfoler also contains annotations.
- **3-LABELS**
  - Contains annotations collected from different sources, including dental experts, and Zoonivers public users.
- **4-PROCESSED-TO-USE-DATASETS**
  - Contains processed datasets for running specific experiments. E.g., balanced datasets with approximately equal number of bone loss and caries objects.

## 1-RAW-DATA

All the dental X-rays saved on Teams are from Jonathan. These images were sent to the research team at different times, and most of them were saved in the "**./1-RAW-DATA**" folder in different zip files:
- **Jonathan data 2020.zip**
  - Contains 908 JPG images, taken from VistaScan, collected from Guildford Dental Centre. This file also contains labels for the 908 images annotated by Jonathan using the offline version of the [via annotation tool](https://www.robots.ox.ac.uk/~vgg/software/via/). The research team received this set of data on 23/10/2020.
  - A subset of this dataset (100 images) was annotated by the members of the research team at the beginning of the project. Both the images and annotations of this subdataset are saved in "**./2-COMBINED-DATASETS/RawLabels_100_image_cs.zip**".
- **Jonathan data April 2021.zip**
  - Contains 2772 JPG images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 30/04/2021.
- **newXray.zip**
  - Contains 336 BMP images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 27/01/2022.
- **newXray v2.zip**
  - Contains 4489 BMP images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 28/01/2022.

## 2-COMBINED DATASETS
This subfolder includes combinations of different datasets contained in "**./1-RAW-DATA**". Some of their annotations were also saved in this subfolder.
- **1 Public ZOON.zip**
  - Contains images from **Jonathan data 2020.zip** and **Jonathan data April 2021.zip**, with overexposed and non-radiograph images removed. This dataset has 2641 images after removal. This dataset were posted on Zooniverse to collect annotations from Zooniverse public users.
  - There are two different groups of annotations collected from Zooniverse public users:
    - Easy annotations, where users were asked to annotate calculus, bone loss, and caries, saved in "**./3-LABELS/Dental-disease-labelling-easy-classifications.csv**", 59668 annotations in total.
    - Advanced annotations, where users were asked to annotate different stages of calculus, bone loss, and caries, saved in "**./3-LABELS/Dental-disease-labelling-advanced-classifications.csv**", 27711 annotations in total. 
- **2 Tutorial.zip**
  - Images used to train Zooniverse users in the Zonniverse tutorial session. No annotations are collected for this dataset.
- **3 Introduction.zip**
  - Images used in the Introduction of the Zooniverse project. No annotations are collected for this dataset.
- **4 Private ZOON.zip**
  - Contains images from **Jonathan data 2020.zip**, **Jonathan data April 2021.zip**, **newXray.zip**, and **newXray v2.zip**, with overexposed and non-radiograph images removed. This dataset has 6926 images after removal. This dataset was intended to be annotated by DR CAPS invited experts, but this hasn't started yet.
- **4 Private ZOON Anonymised.zip**
  - This is an anonymised version of **4 Private ZOON.zip**, with non-original names and metadata removed from it.
- **expert 183.zip** 
  - Contains a subset (183 images) selected from **4 Private ZOON Anonymised.zip** and their annotations (905 in total). Annotations are from Jonathan and can be found in the file itself, limited to bone loss and caries.
- **5 refined_dental_data_from_jonathan.zip**  
  - Contains images from **Jonathan data 2020.zip**, with overexposed and non-radiograph images removed. This dataset has 669 images after removal. Annotations of this dataset are from Jonathan and are saved in the file itself. The annotations are not limited to diseases, but also include tooth, gums, filling, crown, etc.
- **6 expert_669_image_yolo.zip**  
  - Contains the same images contained in **5 refined_dental_data_from_jonathan.zip**. This dataset has 669 images and 2757 annotations after removal. Annotations of this dataset are from Jonathan and are saved in the file itself. The annotations are limited to diseases (bone loss and caries).
- **6 expert_630_image_yolo.zip**  
  - Contains the same images and annotations contained in **6 expert_669_image_yolo.zip**, with healthy images (no bone loss or caries found) and their annotations (empty txt files) removed. This dataset has 630 images and 2718 annotations after removal.
- **RawLabels_100_image_cs.zip**
  - A subset (100 images) of **./1-RAW-DATA/Jonathan data 2020.zip** was annotated by the members of the research team at the beginning of the project. Both the images and annotations of this subdataset are saved in this file.

## 3-LABELS
- **dental-disease-labelling-easy-classifications.csv**
  - Easy annotations for the dataset **./2-COMBINED-DATASETS/1 Public ZOON.zip**, annotators need to specify the location and type of dental diseases, including calculus, bone loss, and caries.
- **dental-disease-labelling-advanced-classifications.csv**
  - Advanced annotations for the dataset **./2-COMBINED-DATASETS/1 Public ZOON.zip**, annotators are required to specify the stages of calculus, bone loss, and caries.
