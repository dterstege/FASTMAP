FASTMAP
=======
**FASTMAP** (**F**lexible **A**tlas **S**egmentation **T**ool for **M**ulti-**A**rea **P**rocessing) is a tool for the registration of biological images to custom atlas plastes and the segmentation of labels of interest within atlas regions.  This tool operates as an *ImageJ Plugin* that draws upon versatile and powerful image analyses tools in *ImageJ* and presents them in a clean, concise, and easy to follow pipeline. 

FASTMAP was created by Dylan Terstege, a Neuroscience PhD candidate in the Epp Lab at the University of Calgary.


## Table of Contents

| section  | description | 
| ------------- | ------------- | 
| [1. Installation Instructions](#installation)   | How to install on macOS and Windows.  |
| [2. Image Processing Tutorial](#processing)   | How to process a sample image set  |
| [3. Atlas Plate Customization](#atlas)  | How to build your own atlas plates for custom projects  |
| [4. Additional Resources](#resources)  | Helpful links for atlas plate construction  |
| [5. Troubleshooting](#ts) | Potential complications and how to overcome them |
| [6. Contact Us](#contact)  | Where to reach us with questions  |

<a name="installation"/>

## 1. Installation Instructions

FASTMAP was designed with ease-of-use at the forefront of our minds.  The installation process reflects this with a simple 3-step approach:

 **1.1 Install *ImageJ***. Ensure that ImageJ is installed.  If it was not previously installed, it can be downloaded [here](https://imagej.nih.gov/ij/download.html).

**1.2 Download the Appropriate Version of FASTMAP.**  Download the appropriate version of FASTMAP for your operating system: [macOS](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_macOS) or [Windows](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_windows).  Linux has not yet been tested.

**1.3 Install Plugin in *ImageJ***.  Before installing, see [settings](#settings) section to determine whether the plugin should be modified in any way to better suit your project prior to installation. Once satisfied with the settings, open *ImageJ* and select "Plugins > Install...".  Navigate to the newly downloaded version of FASTMAP and allow this to save to the ImageJ Plugins folder. 

<a name="processing"/>

## 2. Image Processing Tutorial

The following guide will outline how to process a dataset using FASTMAP:

**2.1 Images**. FASTMAP has been optimized for 8- and 16-bit .tif files, with the label of interest being in an image file which is separate from the channel to be used as a reference during atlas registration (DAPI, propidium iodide, autofluorescence, etc.). 

If your images are not already in this format, *ImageJ* can rapidly convert image formats by selecting "Process > Batch > Convert...".

**2.2 File Organization**. Files should be organized under a common "parent folder". This parent folder should contain at least two subfolders: one containing the "label images" (the to-be-segmented labels) and a second containining the "registration images" (images to be used as references during atlas registration). Folders can contain all images for an entire project, as long as the images for each subject are in continuous strings and corresponding files appear in the same alphabetical order in both folders.

**2.3 Atlas Organization**. FASTMAP is highlighted by its applicability to a nearly limitless range of biological samples, irrespective of sample type or orientation. This is due to the flexibility of the atlas plate registration and [generation](#atlas). To facilitate immediate use, sample atlases have been [provided](https://github.com/dterstege/FASTMAP/tree/main/Plates). 

To use these atlas plates, download the provided atlases and unzip **only** the main folders (ex. "Sagittal.zip") and **not** the nested zipped folders (ex. "RoiSet1.zip"). Keep these unzipped main folders in an easilly accessible "Plates" folder.

**2.4 Initialization**. With image files and atlas plates in proper formats and organizations, the plugin may now be ran (open *ImageJ*, "Plugins > FASTMAP"). The user will be prompted to navigate to the parent folder containing both image channels. A second prompt will ask the user to navigate to a folder containing the desired atlas plates for the analysis.

**2.5 Image Assignment**. A dialogue window titled FASTMAP will populate and prompt the user to identify which of the subfolders in the parent folder contains the *registration images* and which contains *label images*.

**2.6 Range and Analysis Type**. The plugin will then display the number of files in the registration and label subfolders. Output data will be appended based upon the range inputted during this step, so if images from multiple samples are in the same folder the the range of the current sample should be defined.This window also asks which type(s) of analysis should be applied to the image set. Analysis types are as follows:

- Volumetric Analysis: reports the total area of the region, the summed area of all labels within the region, and the percentage of the region that is comprised of labels.
- Object Counts: reports the total area of the region and number of objects counted within each region.

Both the volumetric analysis and object counts analysis types have been written to use the default auto-thresholding parameters of *ImageJ*. If working with already binarized labels as inputs or raw images in which the default thresholding is insufficient, see the [settings](#settings) section for information on how to modify the plugin to better suit the input images.

At the bottom of this window, the user will be asked whether ROIs have already been gathered for this range of images. If images have previously been processed through FASTMAP and the ROIs have been saved, this option can be chosen to conserve the previously registered ROIs. For more information on saving ROIs, click [here](#save).

**2.7 Choose Registration Plate**.

<a name="settings"/>

**2.x Settings**.


<a name="atlas"/>

## 3. Atlas Plate Customization

<a name="resources"/>

## 4. Additional Resources

<a name="ts"/>

## 5. Troubleshooting

<a name="contact"/>

## 6. Contact Us

**Contributors:**
- **Dylan Terstege*** (code/tool conceptualization/written documentation/atlas plates) - ![twitter-icon_16x16](https://user-images.githubusercontent.com/44174532/113163958-e3d3e400-91fd-11eb-8d79-17906d8d3f25.png)[@dterstege](https://twitter.com/dterstege) - ![Mail](https://user-images.githubusercontent.com/44174532/113164412-50e77980-91fe-11eb-9282-dd83852578ce.png)
<dylan.terstege@ucalgary.ca>
- Daniela Oboh (plates)

Principal Investigator:
- Jonathan Epp (tool conceptualization) - https://epplab.com

<sub><sup>***corresponding author**</sup></sub>
