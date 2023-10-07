# Training a Custom YOLOv4 Object Detector

This repository provides a step-by-step guide for training your own custom YOLOv4 object detector to recognize any classes or objects you desire. Follow this comprehensive tutorial to create your custom YOLOv4 model efficiently.

## Table of Contents

1. [**Step 1: Gathering and Labeling a Custom Dataset**](#step-1-gathering-and-labeling-a-custom-dataset)
   - [Method 1: Using Google's Open Images Dataset (RECOMMENDED)](#method-1-using-googles-open-images-dataset-recommended)
   - [Method 2: Manually Labeling Images with Annotation Tool](#method-2-manually-labeling-images-with-annotation-tool)
   
2. [**Step 2: Moving Your Custom Datasets Into Your Cloud VM**](#step-2-moving-your-custom-datasets-into-your-cloud-vm)

3. [**Step 3: Configuring Files for Training**](#step-3-configuring-files-for-training)
   - [i) Cfg File](#i-cfg-file)
   - [ii) obj.names and obj.data](#ii-objnames-and-objdata)
   - [iii) Generating train.txt and test.txt](#iii-generating-traintxt-and-testtxt)
   
4. [**Step 4: Download pre-trained weights for the convolutional layers**](#step-4-download-pre-trained-weights-for-the-convolutional-layers)

5. [**Step 5: Train Your Custom Object Detector!**](#step-5-train-your-custom-object-detector)

6. [**Step 6: Checking the Mean Average Precision (mAP) of Your Model**](#step-6-checking-the-mean-average-precision-map-of-your-model)

7. [**Step 7: Run Your Custom Object Detector!!!**](#step-7-run-your-custom-object-detector)

## Step 1: Gathering and Labeling a Custom Dataset

To train a custom object detector, you need a labeled dataset. You can acquire your dataset through one of two methods:

### Method 1: Using Google's Open Images Dataset (RECOMMENDED)

Gather a large dataset and auto-generate labels using Google's Open Images Dataset and the OIDv4 toolkit. This method is efficient and provides access to thousands of labeled images for over 600 classes.

### Method 2: Manually Labeling Images with Annotation Tool

Manually draw labels using an annotation tool like LabelImg. This method is suitable if you cannot find the desired images or classes in Google's Open Images Dataset.

## Step 2: Moving Your Custom Datasets Into Your Cloud VM

Upload your 'obj' (training) and 'test' (validation) datasets as zip files to your Google Drive and copy them to your cloud VM. This process will speed up dataset transfer.

## Step 3: Configuring Files for Training

Configure various files to train your custom detector:

### i) Cfg File

Edit the '.cfg' file according to your custom object detector requirements. Adjust parameters such as 'width,' 'height,' 'max_batches,' 'steps,' and 'filters' based on the number of classes you are training for.

### ii) obj.names and obj.data

Create 'obj.names' with one class name per line, matching your classes from the dataset generation step.

### iii) Generating train.txt and test.txt

Generate 'train.txt' and 'test.txt' files with relative image paths for training and validation datasets using provided scripts.

## Step 4: Download pre-trained weights for the convolutional layers

Download pre-trained weights ('yolov4.conv.137') for the convolutional layers. These weights enhance model accuracy and speed up convergence.

## Step 5: Train Your Custom Object Detector!

Train your custom YOLOv4 object detector using the following command. Adjust the flags based on your specific requirements.

```bash
!./darknet detector train <path to obj.data> <path to custom config> yolov4.conv.137 -dont_show -map
Training may take hours, so consider running it overnight or during idle times.

**Step 6: Checking the Mean Average Precision (mAP) of Your Model**
Evaluate the model's accuracy by running mAP calculations on saved weights files. This step helps you select the most accurate weights for your model.

**Step 7: Run Your Custom Object Detector!!!**
Now, your custom YOLOv4 object detector is ready for action. Test it on images or videos to detect the objects or classes you trained it for.

Enjoy your custom object detection journey!

Feel free to customize this README.md file to include specific details about your project and any additional information you want to provide to users.


You can copy and paste this Markdown content into your GitHub repository's README.md file, and customize it further to fit your project's specific details and requirements.




