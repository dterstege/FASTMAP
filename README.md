FASTMAP
=======
**FASTMAP** (**F**lexible **A**tlas **S**egmentation **T**ool for **M**ulti-**A**rea **P**rocessing) is a tool for the registration of biological images to custom atlas plastes and the segmentation of labels of interest within atlas regions.  This tool operates as an *ImageJ Plugin* that draws upon versatile and powerful image analyses tools in *ImageJ* and presents them as a clean, concise, and easy to follow plugin. 

FASTMAP was created by Dylan Terstege, a Neuroscience PhD candidate in the Epp Lab at the University of Calgary.

<a name="toc"/>

## Table of Contents

| Section  | Description | 
| ------------- | ------------- | 
| [1. Installation Instructions](#installation)   | How to install on macOS and Windows.  |
| [2. Image Processing Tutorial](#processing)   | How to process a sample image set  |
| [3. Atlas Plate Customization](#atlas)  | How to build your own atlas plates for custom projects  |
| [4. Additional Resources](#resources)  | Helpful links for atlas plate construction  |
| [5. Troubleshooting](#ts) | Potential complications and how to overcome them |
| [6. Citation](#cite) | How to cite FASTMAP |
| [7. Contact Us](#contact)  | Where to reach us with questions  |

<a name="installation"/>

## 1. Installation Instructions

FASTMAP was designed with ease-of-use at the forefront of our minds.  The installation process reflects this with a simple 3-step approach:

- **1.1 Install *ImageJ***. Ensure that ImageJ is installed.  If it was not previously installed, it can be downloaded [here](https://imagej.nih.gov/ij/download.html).

- **1.2 Download the Appropriate Version of FASTMAP.**  Download the appropriate version of FASTMAP for your operating system: [macOS](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_macOS) or [Windows](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_windows).  Linux has not yet been tested.

- **1.3 Install Plugin in *ImageJ***.  Before installing, see [settings](#settings) section to determine whether the plugin should be modified in any way to better suit your project prior to installation. Once satisfied with the settings, open *ImageJ* and select "Plugins > Install...".  Navigate to the newly downloaded version of FASTMAP and allow this to save to the ImageJ Plugins folder. 

<a name="processing"/>

## 2. Image Processing Tutorial

The following guide will outline how to process a dataset using FASTMAP:

- **2.1 Images**. FASTMAP has been optimized for 8- and 16-bit .tif files, with the label of interest being in an image file which is separate from the channel to be used as a reference during atlas registration (DAPI, propidium iodide, autofluorescence, etc.). 

If your images are not already in this format, *ImageJ* can rapidly convert image formats by selecting "Process > Batch > Convert...".

- **2.2 File Organization**. Files should be organized under a common "parent folder". This parent folder should contain at least two subfolders: one containing the "label images" (the to-be-segmented labels) and a second containining the "registration images" (images to be used as references during atlas registration). Folders can contain all images for an entire project, as long as the images for each subject are in continuous strings and corresponding files appear in the same alphabetical order in both folders.

- **2.3 Atlas Organization**. FASTMAP is highlighted by its applicability to a nearly limitless range of biological samples, irrespective of sample type or orientation. This is due to the flexibility of the atlas plate registration and [generation](#atlas). To facilitate immediate use, sample atlases have been [provided](https://github.com/dterstege/FASTMAP/tree/main/Plates). 

To use these atlas plates, download the provided atlases and unzip **only** the main folders (ex. "Sagittal.zip") and **not** the nested zipped folders (ex. "RoiSet1.zip"). Keep these unzipped main folders in an easilly accessible "Plates" folder.

- **2.4 Initialization**. With image files and atlas plates in proper formats and organizations, the plugin may now be ran (open *ImageJ*, "Plugins > FASTMAP"). The user will be prompted to navigate to the parent folder containing both image channels. A second prompt will ask the user to navigate to a folder containing the desired atlas plates for the analysis.

- **2.5 Image Assignment**. A dialogue window titled FASTMAP will populate and prompt the user to identify which of the subfolders in the parent folder contains the *registration images* and which contains *label images*.

- **2.6 Range and Analysis Type**. The plugin will then display the number of files in the registration and label subfolders. Output data will be appended based upon the range inputted during this step, so if images from multiple samples are in the same folder the the range of the current sample should be defined.This window also asks which type(s) of analysis should be applied to the image set. Analysis types are as follows:

   - Volumetric Analysis: reports the total area of the region, the summed area of all labels within the region, and the percentage of the region that is comprised of labels.
   - Object Counts: reports the total area of the region and number of objects counted within each region.

Both the volumetric analysis and object counts analysis types have been written to use the default auto-thresholding parameters of *ImageJ*. If working with already binarized labels as inputs or raw images in which the default thresholding is insufficient, see the [settings](#settings) section for information on how to modify the plugin to better suit the input images.

At the bottom of this window, the user will be asked whether ROIs have already been gathered for this range of images. If images have previously been processed through FASTMAP and the ROIs have been saved, this option can be chosen to conserve the previously registered ROIs. For more information on saving ROIs, click [here](#save).

- **2.7 Choose Registration Plate**. A composite image displaying all plates from the selected atlas will populate on the screen. Drag this to the right side of the screen before selecting 'OK', otherwise it will be hidden by the next image to populate the screen. This image is the working registration image and a prompt will ask which atlas plate it most closely resembles.

- **2.8 Automated resizing**. FASTMAP can be applied to images collected using a wide variety of microscopy techniques. Furthermore, it can be applied to images of different sizes and resolutions. If the user is looking at the same group of regions using multiple microscopy types or imaging magnifications, the plugin can scale atlas plates to limit the extent to which regions need to be manually resized and manipulated. This linear transform is initiated by drawing a rectangle around the sample in the image.

- **2.9 Adjusting Registration**. Missized and often off-centered regions will then populate on the registration image and a window titled *ROIManager* will appear appear. Using this ROI Manager, select all regions (click on the region at the top of the list, hold the 'shift' key, then click on the region at the bottom of the list), next select "More... > OR(Combine)", then click "add(t)". Finally, click 'OK'.

One-by-One, regions will resize and come to the center of the image. Move, adjust, or delete the ROIs as needed - clicking 'OK' on the dialogue window once satisfied with each region. No need to adjust any dummy regions, but do not delete until after all regions have been adjusted.

With all regions adjusted, any ROIs which aren't essential to the analysis may now be deleted from the ROI Manager.

<a name="save"/>

After adjusting all ROIs, select all ROIs in the ROI Manager window and save the ROI set using a name specific to that image. This will allow for the adjusted ROIs to be called upon at a later date should the user wish to apply different thresholding parameters or a different analysis type to the image.

<a name="settings"/>

- **2.10 Settings**.

There are a few settings which may be customized to better suit particular images. These can be adusted by dragging and dropping the .ijm file into *ImageJ* and editting lines as needed. The default settings upon download are set to:

   - Thresholding: "Default"
   - Threshold Background Colour: "Dark"

These settings are found in both the volumetric analysis and the object counts sections of the code and should be adjusted according to the analysis type.

   *Tip*: If using an already binarized image, the following lines can simply be commented out using "//":
   ```
    setAutoThreshold("Default dark"); //may comment out this line if using an already binary image
    run("Convert to Mask"); //may comment out this line if using an already binary image
   ```

**2.11 Outputs**. After all images from the specified file range have been processed, output files will be appear in the parent folder. Depending on the analysis type, they will either be named *VolumetricAnalysis.csv* or *RegionalCounts.csv*. There is no sample identifier in this file name, so it is advised that the filename is edited before the user starts processing the next range of images to avoid overwritting the previous file.

<a name="atlas"/>

## 3. Atlas Plate Customization

A benefit to FASTMAP over other image registration tools is its atlas flexibility. With minimal up-front tracing, atlases can be generated for application to any image set. 

Sample plates can be found [here](https://github.com/dterstege/FASTMAP/tree/main/Plates).

The process of generating a custom atlas is outlined in the following steps:

- **3.1 Collecting Reference Images**. All atlases should be based off of something. This could be a subset of regions in an existing atlas or clearly delineated regions in an all-encompassing range of your own samples. These images do not need to be of any particular format or resolution, but should be clear enough for easy tracing of regions of interest.

- **3.2 Region Tracing**. Open the first of the reference images using *ImageJ*. With the Polygon Tool, trace a region of interest. By hitting "t" on the keyboard, add this ROI to the ROI Manager applet. Rename this newly logged ROI with the name of the region.

Tips for region tracing:

- Clicking "Show All" in the ROI Manager applet is recommended.
- Ensure that regions are not overlapping at all during initial tracing
- If ROIs do not cover the entire X and Y range of the sample, add a dummy ROI as a space filler. This will ensure that regions resize correctly when running the plugin. For an example of this, see the [example coronal plates]().




<a name="resources"/>

## 4. Additional Resources

<a name="ts"/>

## 5. Troubleshooting

<a name="cite"/>

## 6. Citation

<a name="contact"/>

## 7. Contact Us

**Contributors:**
- **Dylan Terstege*** (code/tool conceptualization/written documentation/atlas plates) - ![twitter-icon_16x16](https://user-images.githubusercontent.com/44174532/113163958-e3d3e400-91fd-11eb-8d79-17906d8d3f25.png)[@dterstege](https://twitter.com/dterstege) - ![Mail](https://user-images.githubusercontent.com/44174532/113164412-50e77980-91fe-11eb-9282-dd83852578ce.png)
<dylan.terstege@ucalgary.ca>
- Daniela Oboh (atlas plates)

Principal Investigator:
- Jonathan Epp (tool conceptualization) - https://epplab.com

<sub><sup>***corresponding author**</sup></sub>
