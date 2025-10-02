# DAPI_PML_SUMO

* **Developed by:** Thomas & Héloïse
* **Developed for:** Adèle
* **Team:** De Thé
* **Date:** October 2025
* **Software:** Jupyter Notebook (for analysis) and Napari (for visualization)

### Images description

Images acquired on Zeiss LSM 800 confocal microscope with a 63x objective:

1. 2D images: 1x zoom, pixel size: 0.099 μm (XY)
2. 3D stacks: 2x zoom, voxel size: 0.055 μm (XY), 0.25 μm (Z)

3 channels:
  1. DAPI nuclei
  2. PML foci
  3. SUMO2 or another partner protein


### Notebooks description

#### DAMI_PML_SUMO_3D.ipynb

* Identify focused slices on PML channel using the Laplacian variance method
* Detect nuclei in 3D:
  * Perform maximum-intensity z-projection of DAPI channel
  * Detect nuclei in 2D using Cellpose
  * Extend nuclei into 3D across focused slices
* Detect PML foci in 3D using DoG filtering + Triangle automatic thresholding + opening
* Estimate background intensity in PML and SUMO2 channels as the median pixel intensity outside nuclei
* For each nucleus:
  * Compute the following parameters for each focus: volume, mean and sum of background-corrected intensity in PML channel, mean and sum of background-corrected intensity in SUMO2 channel
  * Compute mean and sum of background-corrected intensity in SUMO2 channel outside PML foci
 
#### DAMI_PML_SUMO_2D.ipynb

* Detect nuclei in 2D using Cellpose
* Detect PML foci in 2D using DoG filtering + Triangle automatic thresholding + opening
* Estimate background intensity in PML and SUMO2 channels as the median pixel intensity outside nuclei
* For each nucleus:
  * Compute the following parameters for each focus: area, mean and sum of background-corrected intensity in PML channel, mean and sum of background-corrected intensity in SUMO2 channel
  * Compute mean and sum of background-corrected intensity in SUMO2 channel outside PML foci

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
6. In your web browser, navigate to and open the `DAPI_PML_SUMO.ipynb` notebook
7. Enter the required parameters in the designated cell
8. Run all cells to perform the data analysis
9. Run the visualization cells to review the results in Napari

### Dependencies

* Conda environment **PML_SUMO**
* Cellpose 3 pretrained model `nuclei`

Both the **PML_SUMO** environment and the `nuclei` model are installed on the WS3 workstation in the ORION image analysis room.

To install the environment on another computer, use the `environment.yml` file provided in the repository. If you experience issues installing Cellpose v3.1.1 (preferably the GPU-enabled version), please follow the official installation instructions here: https://github.com/MouseLand/cellpose.


### Version history

Version 1 released on October 2, 2025.
