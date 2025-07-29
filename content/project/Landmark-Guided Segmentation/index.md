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
Typically presenting as a tri-leaflet structure, the aortic valve is a unidirectional valve located in the aortic root, the section of the aorta (the largest artery in the human body) that attaches to the heart.
The aortic root consists of multiple structural components that function together to maintain the body's optimal blood flow from the heart to the rest of the body. 
You can appreciate the complex anatomy of the root through Figure 1, where the schematic (left) delineates the main structures of root alongside an actual photo of the anatomy (right). 



<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="aortic_anatomy.png" alt="Aortic Root Anatomy" width="45%" style="margin-right: 10px;"/>
        <img src="aortic_photo.png" alt="Aortic Root Anatomy [1-2]" width="45%"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        <b> Figure 1: Aortic Root Anatomy </b> <br> 
    </div>
</div>

The 15 aortic landmarks altogether define the overall structures of aortic valve leaflets. Figure 2 displays an example of a set of aortic landmarks on a CT scan.

<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="landmarks.png" alt="Aortic Root Anatomy" width="65%" style="margin-right: 10px;"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        <b>Figure 2: Aortic Landmarks</b> <br>  [CP: Commissural points, C: Center point, L: Leaflet points, H: Hinge points, LCO: Left coronary ostium, RCO: Right coronary ostium] <br> 
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

**References**\
[1] Nagpal, Prashant & Agrawal, Mukta & Saboo, Sachin & Hedgire, Sandeep & Priya, Sarv & Steigner, Michael. (2020). Imaging of the aortic root on high-pitch non-gated and ECG-gated CT: awareness is the key!. Insights into Imaging. 11. 10.1186/s13244-020-00855-w.
 
[2] Anderson RHClinical anatomy of the aortic rootHeart 2000;84:670-673. 


