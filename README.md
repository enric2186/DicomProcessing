# DicomProcessing
Dicom imaging and Deep learning processing set of tools for a specific database of CT scans used to extract anatomic landmarks
--

_______

<b>Step 1</b> - Analize the server database path structure, compare the patients Id / name with our previously labelled information and extract the different series associated with each patient to a designated location

<b>Step 2</b> - Semiautomatic refinement of the database for removing undesired series. Most of the series are automatically discarded, but visual confirmation for a proper landmark location is required.

<b>Step 3</b> - Automatic preprocessing of the database:<br>
    -Image resampling   - normalize image spacing to (1.0,1.0,1.0) mm per volex<br>
    -ROI extraction     - creates a mask where blank space- air is not considered <br>
    -GT extraction      - creates a labelled mask where a 3x3x3voxels cube encloses a particular craniofacial landmark                                 (19 different classes)<br> 
    -Image normalization - normalize intensity distribution for every image<br>
    -NiFTi extraction   - saves the dicom images in NiFTi format using nibabel<br>
    -DeepMedic configuration files creation
        
<b>Step 4</b> - Visualization and error distances calculation for the predicted landmarks in the test dataset
