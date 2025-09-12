# DAPI_PML

* **Developed by:** Thomas
* **Developed for:** Adèle
* **Team:** De Thé
* **Date:** September 2025
* **Software:** Python Notebook

### Images description

2D or 3D images.

3 channels:
  1. DAPI nuclei
  2. PML foci
  3. SUMO


### Plugin description

* Detect DAPI nuclei with Cellpose (Nuclei Model)
* Find focussed slices with a difference of variance method
* Segment PML foci with DoG filtering + automatic thresholding
* For each nucleus, provide:
  * PML foci number, area and PML,SUMO mean background-corrected intensity
  * SUMO diffuse signal (aka outside foci) mean and sum background-corrected intensity
* Background intensity is estimated on each z-slice by applying a Gaussian filter + Li thresholding, and measuring the mean intensity within the inverted mask (background region)

### Usage instructions

1. Log in to the WS3 workstation in the ORION image analysis room
2. Open the Command Prompt
3. Activate the Conda environment by running:
```
conda activate PML_SUMO
```
5. Launch Jupyter Notebook by running:
```
jupyter notebook
```
6. In your web browser, navigate to and open the `PML_SUMO.ipynb` notebook
7. Enter the required parameters in the designated cell
8. Run all cells to perform the data analysis
9. Run the visualization cells to review the results in Napari

### Dependencies

* Conda environment **PML_SUMO**


Both the **PML_SUMO** environment and the `nuclei` model are installed on the WS3 workstation in the ORION image analysis room.

To install the environment on another computer, use the `environment.yml` file provided in the repository. If you experience issues installing Cellpose v3.1.1 (preferably the GPU-enabled version), please follow the official installation instructions here: https://github.com/MouseLand/cellpose


### Version history

Version 1 released on September 12, 2025.
