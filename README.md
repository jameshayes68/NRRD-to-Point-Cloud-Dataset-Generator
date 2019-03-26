# NRRD-to-Point-Cloud-Dataset-Generator
NRRD is a file format often used for storing 3D medical image data. Its main benefit over DICOM is that NRRD files are anonymized and contain no sensitive patient information. Furthermore NRRD files can store a medical scan in a single file, whereas DICOM data sets are usually comprised of a directory or directories. Thus, in many cases the NRRD file format is selected over DICOM for freely downloadable datasets (e.g. www.embodi3d.com). It is intended that the notebook provided can be used to open such NRRD files and generate a large training dataset of 2D images from a relatively small quantity of NRRD files containing 3D images. Specifically, the notebook contains the code that does the following

1. It opens a working directory subfolder of NRRD files, randomly selects an NRRD file within the folder and generates an array 3D array representation
2. Thresholding is applied so as to remove unwated information or noise, the 3D array is scaled to the desired resolution and converted to an array of xyz coordinates
3. The array of xyz coordinates is randomly streched/compressed/rotated as a data augmentation step
4. The array of xyz coordinates is randomly sampled with the addition of noise so as to generate a point cloud of the desired size 
5. Steps 1 to 4 are repeated. Each time that this process is repeated the x,y & z coordinates of the randomly generated surface samples are appended as a row of an array. Upon completion this array is saved as a csv file within the working directory.
