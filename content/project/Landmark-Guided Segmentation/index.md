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

**Clinical Background**\
Typically presenting as a tri-leaflet structure, the aortic valve is a unidirectional valve located in the aortic root, the section of the aorta (the largest artery in the human body) that attaches to the heart.
The aortic root consists of multiple structural components that function together to maintain the body's optimal blood flow. 
You can appreciate the complex anatomy of the root in Figure 1, where the schematic (left) delineates the main structures of root alongside an actual photo of the anatomy (right). 

<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="aortic_anatomy.png" alt="Aortic Root Anatomy" width="45%" style="margin-right: 10px;"/>
        <img src="aortic_photo.png" alt="Aortic Root Anatomy [1-2]" width="45%"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        <b> Figure 1: Aortic Root Anatomy </b> <br> 
    </div>
</div>

The geometric properties of the delineated structures such as the annulus, sinotubular junction, and the sinus of Valsalva are all carefully considered in clinical procedures for treating valvular diseases.
There are two main types structural valvular disease: **Regurgitation and Stenosis**. Figure 2 illustrates the structural mechanisms of the two types. Regurgitation (insufficiency) refers to a condition where the valve does not close completely, leading to a backward 
flow of blood. Stenosis is a condition where the opening of the valve narrows, hindering the heart's ability to pump blood effectively. The focus of this project and its motivation is aortic stenosis and
its treatments.

<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="stenosis-regurgitation.jpg" alt="Valvular Disease" width="65%" style="margin-right: 10px;"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        <b>Figure 2: Valvular Disease: Stenosis and Regurgitation</b> 
    </div> 
</div>

The most common treatment options for aortic stenosis include surgical aortic valve replacement (**SAVR**) and transcather aortic valve replacement (**TAVR** or **TAVI**). Transcather aortic valve replacement 
is a non-invasive alternative procedure typically recommended for patients with higher surgical risk level. While SAVR involves an open-heart surgery for the doctor to manually excise and replace the diseased valve with
a new prosthetic valve, TAVR delivers a Transcatheter Heart Valve (THV) through a catheter that is inserted through a blood vessel (i.e. femoral artery). The following video effectively demonstrates the TAVR procedure.

{{< youtube Jtek8004jAA&ab >}}
<div style="margin-top: 1px; font-size: 0.90em; color: #999;">
    <b>TAVR Procedure</b> 
</div> 

In both SAVR and TAVR, the clinical pre-procedural planning based on CT images plays a critical role in minimizing the chances of adverse events such as coronary obstruction, which can be critical for patient outcome. 
Specifically, CT-based clinical measurements of aortic structures like the aortic annulus remains the gold standard for pre-procedural planning of TAVR. 
More recently, 3D reconstruction of the aortic root has been used for computational fluid dynamics (CFD) simulation of the blood flow through the anatomy to understand the hemodynamics and potentially predict the procedural outcome, 
showing that patient-specific simulations of the TAVR procedure can be effectively utilized to minimize procedural risks. 
Both processes of extracting clinical measurements and 3D reconstruction involve the segmentation of the complex aortic root anatomy.
However, manual segmentation of an individual’s aortic root is a demanding and time-consuming task. 
Therein lies the goal of this project: an automatic method to reconstruct the aortic valve from CT scans to enable a more efficient pipeline for a pre-procedural planning of aortic stenosis treatment.


**Methods**\
Given the complex structure of the aortic leaflets, the segmentation algorithm must be designed to account for the vast phenotypic heterogeneity that exists in

The 15 aortic landmarks altogether define the overall structures of aortic valve leaflets. Figure 2 displays an example of a set of aortic landmarks on a CT scan.

<div style="text-align: center;">
    <div style="display: flex; justify-content: center; gap: 20px; flex-wrap: wrap;">
        <img src="landmarks.png" alt="Aortic Root Anatomy" width="65%" style="margin-right: 10px;"/>
    </div>
    <div style="margin-top: 1px; font-size: 0.90em; color: #999;">
        <b>Figure 3: Aortic Landmarks</b> <br>  CP: Commissural points, C: Center point, L: Leaflet points, H: Hinge points, LCO: Left coronary ostium, RCO: Right coronary ostium <br> 
    </div> 
</div>


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
 
[2] Anderson RHClinical anatomy of the aortic rootHeart 2000;84:670-673.\   

[3] Heart valve disease. Heart Foundation NZ. (n.d.). https://www.heartfoundation.org.nz/your-heart/heart-conditions/heart-valve-disease\  

[4] Nucleus Medical Media. (2020, February 5). Aortic valve stenosis animation – Part 1 – Normal heart anatomy [Video]. YouTube. https://www.youtube.com/watch?v=Jtek8004jAA\   

[5] Ribeiro, Henrique B., John G. Webb, Raj R. Makkar, Mauricio G. Cohen, Samir R. Kapadia, Susheel Kodali, Corrado Tamburino, et al. "Predictive Factors, Management, and Clinical Outcomes of Coronary Obstruction Following Transcatheter Aortic Valve Implantation." Journal of the American College of Cardiology. 62, no. 17 (2013): 1552-62. https://doi.org/10.1016/j.jacc.2013.07.040.\  

[6] Hellmeier, Florian, Jan Brüning, Simon Sündermann, Lina Jarmatz, Marie Schafstedde, Leonid Goubergrits, Titus Kühne, and Sarah Nordmeyer. "Hemodynamic Modeling of Biological Aortic Valve Replacement Using
Preoperative Data Only." Frontiers in cardiovascular medicine 7 (2021). https://doi.org/10.3389/fcvm.2020.593709. \   

[7]