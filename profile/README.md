## Carleton College Computer Science 2025 Comps: Computer Vision For Autonomous Driving

### Contributors

| Name           | Email                 |
| -------------- | --------------------- |
| Ben Zhao       | benzhao90@gmail.com   |
| Nathaniel Li   | lin@carleton.edu      |
| Julian Tanguma | tangumaj@carleton.edu |
| David Toledo   | dtoledo1125@gmail.com  |
| Ethan Masadde  | masaddee@carleton.edu |
| Josh Meier     | joshmeier456@gmail.com   |

For our Senior capstone project, or Comps as Carleton likes to call it, we dove into two specific tasks in the perception step of an autonomous driving car: Semantic Segmentation and Instance Segmentation. Then we investigated the impact of adverse weather on the performance of these tasks, and implemented multiple mitigation strategies to bring performance back up to the baseline. At the heart of this project was also the usage of the simulator CARLA to produce an image dataset with semantic segmentation ground truth values and a video dataset (of frames at 6 fps) with instance segmentation ground truths. 

The repositories inside this organization include all the code necessary to reproduce our project's data collection in CARLA, the training and evaluation of the semantic segmentation and instance segmentation models, and the domain adaptation, image processing, and sensor fusion strategies to improve the performance of those models.


### Data Collection in CARLA

- [cv4ad_CARLA_code](https://github.com/Carleton-Comps-CV4AD/cv4ad_CARLA_code): This repo holds the code we used to create the datasets that each team used. See its own documentation for more details on how the data is collected and how to reproduce it.

### Computer Vision Models

- [semantic-segmentation](https://github.com/Carleton-Comps-CV4AD/semantic-segmentation): This repo holds the code used to train and evaluate the semantic segmentation model we chose: an HRNETV2 encoder adapted from MIT's ADE20k implementations. See its own documentation for more details.

- [instance-segmentation](https://github.com/Carleton-Comps-CV4AD/instance-segmentation): This repo holds the code used to train and evaluate the instance segmentation model we chose: MaskTrack-RCNN which we use through the MMDetection open source object detection framework. See its own documentation for more details.

### Mitigating the Effects of Weather

- [domainTranslation](https://github.com/Carleton-Comps-CV4AD/domainTranslation): This repo holds the code used to perform Domain Translation: a preprocessing technique using a CNN to sharpen an image a remove granularity from it as a strategy to mitigate the effects of adverse weather on our models. See its own documentation for more details.


- [imageProcessing](https://github.com/Carleton-Comps-CV4AD/imageProcessing): This repo holds scripts used to apply LUTs to pictures. This is a preprocessing technique to improve performance of models only trained on clear day images being evaluated on night and foggy images. See its own documentation for more details.

- [sensor_fusion](https://github.com/Carleton-Comps-CV4AD/sensor_fusion): This repo holds the code used to integrate LIDAR data with RGB image data, a process called sensor fusion, into the semantic segmentation model to improve model performance on night and foggy images. See its own documentation for more details.

### Website

- [cv4ad_website](https://github.com/Carleton-Comps-CV4AD/cv4ad_website): This repo holds the code that will be hosted on the Carleton CS Comps Projects page to serve as a summary of our project and to point anyone interested in our code, data, or our presentation in the right direction.
