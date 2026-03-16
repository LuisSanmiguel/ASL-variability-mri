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
 
## Human Pipeline ##
Deface step 
```sh
mri_deface \
  t1_mprage.nii \
  $FREESURFER_HOME/average/talairach_mixed_with_skull.gca \
  $FREESURFER_HOME/average/face.gca \
  t1_mprage_defaced.nii
```
```recon-all```: Creates a 3D map of the brain, identifying where gray and white matter are located (using the T1_mprage as input).

```sh
recon-all -s subject1_01 -i T1_mprage_sX.nii -all
```
