FASTMAP
=======
**FASTMAP** (**F**lexible **A**tlas **S**egmentation **T**ool for **M**ulti-**A**rea **P**rocessing) is a tool for the registration of biological images to custom atlas plastes and the segmentation of labels of interest within atlas regions.  This tool operates as an *ImageJ Plugin* that draws upon versatile and powerful image analyses tools in *ImageJ* and presents them in a clean, concise, and easy to follow pipeline. 

FASTMAP was created by Dylan Terstege, a Neuroscience PhD candidate in the Epp Lab at the University of Calgary.


### Table of Contents

| section  | description | 
| ------------- | ------------- | 
| [Installation instructions](#installation)   | How to install on macOS and Windows.  |
| [Image Processing Tutorial](#processing)   | How to process a sample image set  |
| [Atlas Plate Customization](#atlas)  | How to build your own atlas plates for custom projects  |
| [Additional Resources](#resources)  | Helpful links for atlas plate construction  |
| [Contact Us](#contact)  | Where to reach us with questions  |

<a name="installation"/>

### Installation Instructions

FASTMAP was designed with ease-of-use at the forefront of our minds.  The installation process reflects this with a simple 3-step approach:

 **1. Install *ImageJ***. Ensure that ImageJ is installed.  If it was not previously installed, it can be downloaded [here](https://imagej.nih.gov/ij/download.html).

**2. Download the Appropriate Version of FASTMAP.**  Download the appropriate version of FASTMAP for your operating system: [macOS](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_macOS) or [Windows](https://github.com/dterstege/FASTMAP/tree/main/FASTMAP_windows).  Linux has not yet been tested.

**3. Install Plugin in *ImageJ***.  Open *ImageJ* and select "Plugins > Install...".  Navigate to the newly downloaded version of FASTMAP and allow this to save to the ImageJ Plugins folder. 

<a name="processing"/>

### Image Processing Tutorial

The following guide will outline how to process a dataset using FASTMAP:

**1. Images**. FASTMAP has been optimized for 8- and 16-bit .tif files, with the label of interest being in an image file which is separate from the channel to be used as a reference during atlas registration (DAPI, propidium iodide, autofluorescence, etc.). 
If your images are not already in this format, *ImageJ* can rapidly convert image formats by selecting "Process > Batch > Convert...".

**2. File Organization**. Files should be organized under a common "parent folder". This parent folder should contain at least two subfolders: one containing the "label images" (the to-be-segmented labels) and a second containining the "registration images" (images to be used as references during atlas registration). Folders can contain all images for an entire project, as long as the images for each subject are in continuous strings and corresponding files appear in the same alphabetical order in both folders.

<a name="atlas"/>

### Atlas Plate Customization

<a name="resources"/>

### Additional Resources

<a name="contact"/>

### Contact Us

**Author:**
**Dylan Terstege** - [@dterstege](https://twitter.com/dterstege) - <dylan.terstege@ucalgary.ca>

Principal Investigator:
Jonathan Epp - https://epplab.com
