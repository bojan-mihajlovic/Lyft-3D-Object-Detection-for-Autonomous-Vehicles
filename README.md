# Lyft-3D-Object-Detection-for-Autonomous-Vehicles
Kaggle Lyft 3D Competition - Bronze Medal Solution

Use the following Kaggle API to download the dataset:<br/> 
    <ins>kaggle competitions download -c 3d-object-detection-for-autonomous-vehicles</ins>

## Overview

Self-driving technology presents a rare opportunity to improve the quality of life in many of our communities. Avoidable collisions, single-occupant commuters, and vehicle emissions are choking cities, while infrastructure strains under rapid urban growth. Autonomous vehicles are expected to redefine transportation and unlock a myriad of societal, environmental, and economic benefits. You can apply your data analysis skills in this competition to advance the state of self-driving technology.

Lyft, whose mission is to improve people’s lives with the world’s best transportation, is investing in the future of self-driving vehicles. Level 5, their self-driving division, is working on a fleet of autonomous vehicles, and currently has a team of 450+ across Palo Alto, London, and Munich working to build a leading self-driving system (they’re hiring!). Their goal is to democratize access to self-driving technology for hundreds of millions of Lyft passengers.

From a technical standpoint, however, the bar to unlock technical research and development on higher-level autonomy functions like perception, prediction, and planning is extremely high. This implies technical R&D on self-driving cars has traditionally been inaccessible to the broader research community.

This dataset aims to democratize access to such data, and foster innovation in higher-level autonomy functions for everyone, everywhere. By conducting a competition, we hope to encourage the research community to focus on hard problems in this space—namely, 3D object detection over semantic maps.

In this competition, you will build and optimize algorithms based on a large-scale dataset. This dataset features the raw sensor camera inputs as perceived by a fleet of multiple, high-end, autonomous vehicles in a restricted geographic area.

If successful, you’ll make a significant contribution towards stimulating further development in autonomous vehicles and empowering communities around the world.

## Data

What files do I need?

You will need the LIDAR, image, map and data files for both train and test (**test_images.zip, test_lidar.zip, etc.**). You may also need the train.csv, which includes the sample annotations in the form expected for submissions. The **sample_submission.csv** file contains all of the sample Ids for the test set.

The data files (**test_data.zip, train_data.zip**) are in JSON format.

What should I expect the data format to be?

The data comes in the form of many interlocking tables and formats. The JSON files all contain single tables with identifying tokens that can be used to join with other files / tables. The images and lidar files all correspond to a sample in sample_data.json, and the sample_token from sample_data.json is the primary identifier used for the train and test samples.

The annotations in **train.csv** are in the following format: center_x center_y center_z width length height yaw class_name

center_x, center_y and center_z are the world coordinates of the center of the 3D bounding volume.
width, length and height are the dimensions of the volume.
yaw is the angle of the volume around the z axis (where y is forward/back, x is left/right, and z is up/down - making 'yaw' the direction the front of the vehicle / bounding box is pointing at while on the ground).
class_name is the type of object contained by the bounding volume.
What am I predicting?

For the test samples, we're predicting the bounding volumes and classes of all of the objects in a given scene.

For example, in sample_token 97ce3ab08ccbc0baae0267cbf8d4da947e1f11ae1dbcb80c3f4408784cd9170c, we might be predicting the presence of a car (with confidence 1.0) and a bus (with confidence 0.5). The prediction would look like this:

**97ce3ab08ccbc0baae0267cbf8d4da947e1f11ae1dbcb80c3f4408784cd9170c,1.0 2742.152625996093 673.1631800662494 -18.6561112411676 1.834 4.609 1.648 2.619835541569646 car 0.5 2728.9634555684484 657.8296521874645 -18.54676216218047 1.799 4.348 1.728 -0.5425527100619654 bus
With all predicted objects on the same line.**

Note that confidence values are inserted prior to center_x center_y center_z width length height yaw class_name.

## Files

**train_data.zip and test_data.zip** - contains JSON files with multiple tables. The most important is sample_data.json, which contains the primary identifiers used in the competition, as well as links to key image / lidar information.
**train_images.zip** and **test_images.zip** - contains .jpeg files corresponding to samples in **sample_data.json**
**train_lidar.zip** and **test_lidar.zip** - contains **.jpeg** files corresponding to samples in **sample_data.json**
**train_maps.zip** and **test_maps.zip** - contains maps of the entire sample area.
**train.csv** - contains all sample_tokens in the train set, as well as annotations in the required format for all train set objects.
**sample_submission.csv** - contains all sample_tokens in the test set, with empty predictions.

