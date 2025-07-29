---
title: Landmark-Guided Segmentation
date: 2022-10-26
tags:
  - Landmark Detection
  - Segmentation
  - 3D Point cloud
  - Meshing
---

**Objective:**\
Develop a robust segmentation algorithm to create an accurate reconstruction of aortic valve using cardiac Computed Tomography (CT) scans
<!--more-->

**Background**\
Typically presenting as a tri-leaflet structure, the aortic valve is a unidirectional valve located in the aortic root, the section of the aorta that attaches to the heart.
The aortic root consists of multiple structural components that function together to maintain the body's optimal blood flow.

<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="aortic_anatomy.png" alt="Aortic Root Anatomy" width="45%" style="margin-right: 10px;"/>
        <img src="aortic_photo.png" alt="Aortic Root Anatomy [1-2]" width="45%"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        Aortic Root Anatomy <br> 
    </div>
</div>

Using commercial segmentation applications, manual segmentation of the aortic leaflet can take 30 minutes to over 1 hour for a trained engineer. 


**Methods**\
Given the complex structure of the aortic leaflets, the segmentation algorithm must be designed to account for the vast phenotypic heterogeneity that exists in
the patient population. 

```markmap {height="200px"}
- Aortic Components
  - Aortic Leaflets
  - Calcium Nodules
  - Aortic Root Wall
```


**Result**\
A pipeline involving a landmark detection module and a point cloud registration module is developed. 

**Discussion**\
This method utilizes both the structural information obtained from the aortic landmarks and the intensity signal from the CT images to robustly segment the complex anatomy of the aortic valve. 


