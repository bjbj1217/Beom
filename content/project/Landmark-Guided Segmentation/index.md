---
title: Landmark-Guided Segmentation
date: 2022-10-26
tags:
  - Landmark Detection
  - Image Segmentation
  - 3D Point cloud
  - Meshing
---

Develop a robust segmentation algorithm to create an accurate reconstruction of aortic valve using cardiac Computed Tomography (CT) scans
<!--more-->

**Problem**\
Develop a robust segmentation algorithm to create an accurate reconstruction of aortic valve using cardiac Computed Tomography (CT) scans

**Background**\
Typically presenting as a tri-leaflet structure, the aortic valve is a unidirectional valve located in the aortic root, the section of the aorta that attaches to the heart.
The aortic root consists of multiple structural components that function together to maintain the body's optimal blood flow.
Using commercial segmentation applications, manual segmentation of the aortic leaflet can take 30 minutes to over 1 hour for a trained engineer. 

**Methods**\
Given the complex structure of the aortic leaflets, the segmentation algorithm must be designed to account for the vast phenotypic heterogeneity that exists in
the patient population. 

**Result**\
A pipeline involving a landmark detection module and a point cloud registration module is developed. 

**Discussion**\
This method utilizes both the structural information obtained from the aortic landmarks and the intensity signal from the CT images to robustly segment the complex anatomy of the aortic valve. 


