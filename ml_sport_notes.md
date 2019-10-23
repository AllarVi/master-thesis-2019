# Machine Learning Sports Notes

## 1) A markerless motion capture technique for sport performance analysis and injury prevention: Toward a ‘big data’, machine learning future - J. Alderson

### Background

"From an applied perspective, an ideal solution to 3D sports biomechanical analysis lies in participant specific non-invasive markerless motion capture, enhanced by additional 3D scanning and imaging techniques."

### Methods

2 phases:

* Offline - t-pose of athlete with 3D scanner -> subject specific reference shape + skeleton = reference rigged template

* Online - min. 6 2D cameras -> multi-view 2D videos + merging = low fidelity 3D visual hull

* Previous results fitted to estimate "global joint kinematics"

* "refined global joint kinematics" = Obtained by feeding constrained mesh deformation functions by the "global joint kinematics" and the resulting error between the surface of deformed model and the visual hull is employed

### Results

### Discussion

## 2) Estimation of Knee Joint Forces in Sport Movements Using Wearable Sensors and Machine Learning

Advises wearable inertial measurement units (IMUs) combined with artificial neural networks (ANNs).

Used IMUs + marker-based motion capture system.

## 3) Classification of team sport activities using a single wearable tracking device

Used single wearable tracking device incorporating an accelerometer and a gyroscope.

## My observations

There is definitely potential for improving **non-invasive field-based methods** to quantify and monitor technical biomechanical movements for specific sports. Human cognitive skills give coaches with long history in specific sports the ability to recognize mistakes in technical movements. We believe that a coach with 20 years of experience in coaching can easily recognize when a player's two-handed backhand stroke has something lacking, for example the player's shoulders are not properly aligned for maximum stroke efficiency.

I believe recognizing these mistakes in athlete's techniques can be categorized under pattern detection problems and decoupled from humans to computers. Computers could potentially accumulate far more experience than any human ever.

