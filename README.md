# varcity_ruemonge
a fresh take on the classic ruemonge 2014 challenge


# 3D Semantic Segmentation and Procedural Modelling Challenge

There is an increasing interest in semantically annotated 3D urban models, e.g. cities.
The typical approaches start with the semantic labelling of all the images used for the 3D model.

In this challlenge, we provide a new dataset and tasks for pushing the limits of 3D modelling.

So far this is the largest and most detailed dataset available including a dense surface and semantic labels for urban classes.
The dataset consists of 700 meters along a street annotated with pixel-level labels for facade details such as windows, doors, balconies, roof, etc.

We provide the images, labels and indexes to the 3D surface together with evaluation source code for comparing different tasks.
Tasks are 3D mesh/pcloud and 2D image labeling, view selection and will further be extended in the future with more.


## Overview

TODO: insert image on View Reduction!


This dataset allows the evaluation of semantic classification methods in the following tasks:

* TASK 1 - Image Labelling - vanilla 2d img labelling task
* TASK 2 - Mesh Labelling - collect or reason in 3d to label mesh
* TASK 3 - Pointcloud Labelling - collect or reason in 3d to label point cloud / mesh
* TASK 4 - View selection - reason which images to skip for features &classification via view reduction (ECCV paper)
* TASK 5 - Scene Coverage - reason which images to skip for features & classification via scene coverage (ECCV paper)

## Downloads

TODO: insert image on data overlay protocol
TODO: insert image on ETHZ CVL RueMonge 2014 dataset


If you are interested, enter this dataset request form and I will contact you.
https://docs.google.com/forms/d/1SiU9M6Bb6fh0Zs7GGvlYRmT6qhRRKBGX5bGoUBWrokA/viewform


This dataset comes with the following data:
* 2D images for training and testing, labelled in 8 classes
* 3D mesh (faces, vertices) as a 3D representation
* Index files for faces to pixels in each image
* Training / testing splits as txt files
* Sample files for classification results
* Sample source code for loading and evaluation (see below)

This sample source code allows the following functions
* Evaluate 2D/3D labeling results by (classwise or PASCAL IOU) accuracy.
* Examples for loading 2D image data into the 3D mesh (color, labels, probabilities)
* Fusion of multiview data by the SUMALL principle (see paper)
* Mesh labelling optimization via a graphcut approach.

Various helper tools
* The protocol for training / testing is:
* 2D Training images are 113 files in 2D (see above: north side)
* 2D Testing images are the 106 (labelled) images (south side) (on pixel level)
* 3D Training images are 113 files (see above: north side)
* 3D Testing images are 106 (labelled) and 202 RGB images (south side) (on mesh face)

## Results for ETHZ CVL RueMonge 2014 for the different tasks are:

<a href="http://goo.gl/forms/AbbYzw7WZq">Submit your results here!</a>

|Source         |  TASK1     |   TASK2	  |   TASK3    |   TASK4	 |   TASK5   |
|               | [2D IOU %] | [3D IOU %]	| [3D IOU %] | [Speedup] | [Speedup] |
|---------------|------------|------------|------------|-----------|-----------|
|[1] MAP        |  38.72%    |	35.77%	  |   -	       |   -       |           |
|[1] GCO        |  40.92%    |	37.33%	  |   -        |   11.9x   |   7.1x    |
|[1] GCO+recode |  41.34%	   |  41.92%	  |  42.32% 	 |  -	       |     -     |


[1] Learning Where To Classify In Multi-View Semantic Segmentation, H. Riemenschneider, A. Bodis-Szomoru, J. Weissenberg, L. Van Gool, ECCV 2014


<iframe src="https://docs.google.com/spreadsheets/d/1iy17jfjyJwWyW9zdkLWZRAnb4tPiuYdUgbowSDSoEsk/pubhtml?gid=194606980&single=true&widget=true&headers=false" width="1000" height="500"></iframe>


<br>
<br>
<br>

<p>This page has been edited by <a href="mailto:hayko(funkystuff)vision.ee.ethz.ch">Hayko Riemenschneider</a></p>

