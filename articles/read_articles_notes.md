# Read articles notes 

## 1) Average trajectory springer

[article](sven/average_trajectory_springer.pdf)

**Average trajectory** - pair of trajectory and pipe-shaped neighborhood

* trajectory - shape of the joint motion
* pipe-shaped neighborhood - variability of the observed motions

## 2) Clustered Pose and Nonlinear Appearance Models for Human Pose Estimation

[article](pose\ estimation/johnson10bmvc.pdf)

* an extension of ‘pictorial structure model’ (PSM) is proposed
* complex pose estimation in images

## 3) A markerless motion capture technique for sport performance analysis and injury prevention: Toward a ‘big data’, machine learning future - J. Alderson

* "From an applied perspective, an ideal solution to 3D sports biomechanical analysis lies in participant specific **non-invasive** markerless motion capture, enhanced by additional 3D scanning and imaging techniques."

### Methods

2 phases:

* 1) Offline - t-pose of athlete with 3D scanner -> subject specific reference shape + skeleton = reference rigged template
* 2) Online - min. 6 2D cameras -> multi-view 2D videos + merging = low fidelity 3D visual hull
* Previous results fitted to estimate "global joint kinematics"
* "refined global joint kinematics" = Obtained by feeding constrained mesh deformation functions by the "global joint kinematics" and the resulting error between the surface of deformed model and the visual hull is employed

## 4) Estimation of Knee Joint Forces in Sport Movements Using Wearable Sensors and Machine Learning

* Advises wearable inertial measurement units (IMUs) combined with artificial neural networks (ANNs).
* Used IMUs + "marker-based motion capture" system.

## 5) Classification of team sport activities using a single wearable tracking device

Used single wearable tracking device incorporating an accelerometer and a gyroscope.