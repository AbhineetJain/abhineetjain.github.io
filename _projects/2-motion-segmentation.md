---
layout: page
title: Dynamic Semantic Motion Segmentation
description: Spring 2016, Undergraduate Researcher, IIIT Hyderabad
img: /assets/img/DynamicSegmentation.jpeg
importance: 3
category: robotics
---

Worked on implementing incremental surface reconstruction and tracking in dynamic scenes.

##### Approach
- To segment moving objects in a given frame, we used epipolar constraint with stereo camera and joint inference with semantics using Dense CRF formulation for improving motion labelling.
- For tracking and fusion, we used [InfiniTAM library](https://www.robots.ox.ac.uk/~victor/infinitam/){:target="\_blank"}. The library was used to return rotational (R) and translational (T) parameters between two consecutive frames from [KITTI car dataset](http://www.cvlibs.net/datasets/kitti/){:target="\_blank"}.
- We used these parameters to represent the scene in a voxel grid. The idea was to fuse and find the surface of the moving object in an incremental fashion in these voxels after every frame using TSDF ray casting.
- We used keypoint matching using SIFT features, and R & T parameters from the library to reconstruct the static scene by taking a weighted sum of both.
- We applied Medioni’s transformation to reconstruct the object in motion, separately.

##### Conclusion
The project could not achieve the desired results as the R & T so obtained in voxel space were only accurate up to a scale, given less features on a moving object and hence, point cloud registration failed for moving objects.
