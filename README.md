# ASL-variability-mri
Pipeline Code to: 
1. Sort DICOM images with DICOM sort.
2. Convert DICOM images to .nii.
3. [**Human**]: 
    - Use Freesurfer to create a 3D map of the brain.
    - Use FSL to register ASL and M0 images with the Freesurfer output. 
4. [**QASPER**]:
    - Use FSL to register ASL and M0 images.
5. Compare perfusion values for **Human** and **QASPER** in different sessions using Python.
 
