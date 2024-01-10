# Data logs for dental disease detection

A diagram that provides an overview of the data repository on Teams can be found in [this google slide](https://docs.google.com/presentation/d/1CsW2adn97tSmq5DyrZnu1ePAUd11GN72_CcipZ8SqeM/edit#slide=id.p). A more detailed description can be found in [this google spreadsheet](https://docs.google.com/spreadsheets/d/13ffydSqYmcbXFMbpCg4VaaYvdrQI9EgjUI8YaQEzLxE/edit#gid=0).

This document is created to record and explain the change of the data repository for the dental diseas detection project. The data repository contains dental X-rays and their annotations, along with some processing codes and ipynb files. The current version of this document will only cover the structure of the folder where the collected dental X-rays and annotations are stored in.  

Both dental X-rays and their annotations are stored at “**Dental Disease Detection Files/Documents/General/NEW DATASETS AND PROCESSING SCRIPTS/1. Disease Object Detection**” on Teams, referred as “**./**” below. The “**./**” folder consists of four subfolders:
- **1-RAW-DATA**
  - Contains all the dental X-rays.
- **2-COMBINED DATASETS**
  - Contains filtered dental X-rays, with overexposed and non-radiograph images removed. Some files in this subfolder also contains annotations.
- **3-LABELS**
  - Contains annotations collected from different sources, including dental experts, and Zoonivers public users.
- **4-PROCESSED-TO-USE-DATASETS**
  - Contains processed datasets for running specific experiments. E.g., balanced datasets with approximately equal number of bone loss and caries objects.

## 1-RAW-DATA

### X-rays collected from Guildford Dental Centre
All the dental X-rays from Guildford Dental Centre are provided by Jonathan. These images were sent to the research team at different times, and uploaded to the "**./1-RAW-DATA**" folder in different zip files:
- **Jonathan data 2020.zip**
  - Contains 908 JPG images, taken from VistaScan, collected from Guildford Dental Centre. This file also contains labels for the 908 images annotated by Jonathan using the offline version of the [via annotation tool](https://www.robots.ox.ac.uk/~vgg/software/via/). The research team received this set of data on 23/10/2020.
  - A subset of this dataset (100 images) was annotated by the members of the research team at the beginning of the project. Both the images and annotations of this subdataset are saved in "**./2-COMBINED-DATASETS/RawLabels_100_image_cs.zip**".
- **Jonathan data April 2021.zip**
  - Contains 2772 JPG images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 30/04/2021.
- **newXray.zip**
  - Contains 336 BMP images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 27/01/2022.
- **newXray v2.zip**
  - Contains 4489 BMP images, taken from VistaScan, collected from Guildford Dental Centre. The research team received this set of data on 28/01/2022.

### X-rays collected from University of Sao Paulo
The University of Sao Paulo (USP) dataset consists of 719 JPG format dental X-rays and their annotations. Among the 719 images, 183 of them are healhty images (no diseases in the image), 536 are unhealthy images (caries found in the image). The research team received this set of data on 13/10/2023. Annotaion types in the dataset include dental caries level 2-5. Images in this dataset are stored in the following zip files in the "**./1-RAW-DATA**" folder:
- **USP_imgs_with_healthy.zip**
  - Contains all 719 images provided by the University of Sao Paulo.
- **USP_imgs_no_healthy.zip**
  - Contains only 536 unhealthy images, 183 healthy images were excluded from this file.

### X-rays collected from King's College London
All the dental X-rays from King's College London (KCL) are provided by Alex. The KCL dataset contains 3200 images in total and is compressed into the following zip files and uploaded to the "**./1-RAW-DATA**" folder:
- **Alex data.zip**, this zip file contains 9 zip files:
  - **Alex Yonqn X rays.zip**: 26 JP2 images and 462 JPG images.
  - **Folder 1**: 852 JPG images.
  - **Folder 2** 284 JPG images.
  - **Folder 3** 326 JPG images, this folder has been uploaded to DR CAPS for collecting annotations.
  - **Folder 4** 294 JPG images.
  - **Folder 5** 252 JPG images.
  - **Folder 6** 250 JPG images.
  - **Folder 7** 222 JPG images.
  - **Folder 8** 226 JPG images, 3 JPEG images, 3 PNG images.

A copy of the KCL dataset can be found in the folder **General/Radiographs/from KCL/** in the **NIHR i4i - Internal** channel on Teams.

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
- **USP_imgs_labels_with_healthy.zip**
  - Contains all 719 images and 941 annotations collected from the University of Sao Paulo. Annotaion types in the dataset include dental caries level 2-5. 
- **USP_imgs_labels_no_healthy.zip**
  - Contains only 536 unhealthy images and 941 annotations collected from the University of Sao Paul, 183 healthy images were excluded from this file. Annotaion types in the dataset include dental caries level 2-5.


## 3-LABELS
- **dental-disease-labelling-easy-classifications.csv**
  - Easy annotations for the dataset **./2-COMBINED-DATASETS/1 Public ZOON.zip**, annotators need to specify the location and type of dental diseases, including calculus, bone loss, and caries.
- **dental-disease-labelling-advanced-classifications.csv**
  - Advanced annotations for the dataset **./2-COMBINED-DATASETS/1 Public ZOON.zip**, annotators are required to specify the stages of calculus, bone loss, and caries.

# Todolist:
- Upload USP data to Teams.
- Remove redundant data if necessary.
- Include **4-PROCESSED-TO-USE-DATASETS** into this document and the diagram if necessary.
