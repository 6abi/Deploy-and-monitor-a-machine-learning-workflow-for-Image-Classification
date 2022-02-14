# Deploy and monitor a machine learning workflow for Image Classification #
An image-classification project for Udacity's AWS Machine Learning Nanodegree.

## Table of Contents ##
1. [Overview](#overview)
2. [File Descriptions](#file_descriptions)
3. [Results](#results)


## Overview<a name="overview"></a> ##
This is a project in Udacity’s AWS Machine Learning Engineer Nanodegree geared towards building an ML workflow.

The project use a sample dataset called CIFAR to simulate an image classification model. I deploy and monitor a machine learning workflow for Image Classification using AWS resources such as, sagemaker and boto3 SDKs, image-classification built-in algorithm, Lambda functions and Step Function Workflow, and SageMaker model monitor and endpoint. The CIFAR dataset is open source and can be downloaded at: https://www.cs.toronto.edu/~kriz/cifar-100-python.tar.gz
The goal of this project is to:
1. Build an image classification model that differentiates between bicycles and motorcycles;
2. Deploy the model for inference using AWS Lambda functions and AWS Step functions.

## File Descriptions<a name="file_descriptions"></a> ##
The main files of project are:

1. 'starter.ipynb' notebook file with complete solution and key results displayed;

2. Step Function in 'MyStateMachine-project2.json';

3. Four screenshots of the working Step Function;

4. Lambda functions as 'Lambda.py'.


## Results<a name="results"></a> ##

1.	The image classification model had a test accuracy of 0.82.
2. The step Function execution start with no Errors, as shown below:
![processing]()   
3.	The Step Function indicates success when the prediction probability meets or exceeds the acceptance threshold (set at 0.93) with all three Lambda functions with Green status, as shown below:
![success]()
      
4.	The Step Function fails when the prediction probability does not meet the threshold with the third Lambda function having a Red completion status as shown below:
![fail]()
      
5.  The following chart shows the prediction probability for a randomly selected set of test images against the threshold. The dotted green line is the acceptance threshold. Blue dots represent images classified with a probability above the acceptance threshold. The red dot represents an image classified with probability below the acceptance threshold:

![monitor]()

5. The chart below shows thatInferences are greater than 0.5 (above the dotted black line), i.e., motorcycle. The nferences have a confidence level above the threshold (bar is above the dotted green line)
![custon_visualization]()

A larger sample should be obtained (more test inferences should be run) to determine if the model is weak when it comes to identifying bicycles.

