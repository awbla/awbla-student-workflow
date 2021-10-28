---
title: Creating a Mask
nav: Agisoft
---

### Create a mask
The following documentation on creating a mask is adapted from Samantha Porter's "Supplemental Instructions on Background Masking" (file name: [Supplemental_Instructions_1_Background_Masking.pdf)](https://conservancy.umn.edu/handle/11299/172480).

#### Create a background image in Microsoft PowerPoint
1. Open Microsoft PowerPoint and create a blank presentation
    - Delete the empty text boxes
1. Navigate to the Insert tab, click Pictures > This Device
1. Navigate to the set of images you want to create a mask for, select one of the images, and click Insert
1. Navigate to the Picture Format tab and make note of the image size, for example 7.5" by 11.25"
1. Navigate to the Insert tab, click Shapes > Rectangle
1. Drag to create a small rectangle and click on it
1. In the Shape Format tab, click Shape Outline > No Outline
1. In the Shape Format tab, click Shape Fill > Eyedropper
1. Click the eyedropper within your image's original background to select that color
1. Click the rectangular image, navigate to the Shape Format tab, and change the shape size so that it matches the original image
1. Right click the shape and select Save as Picture
1. Navigate to (file location)
1. Change the Save as type to JPEG File
1. Rename the file as *itemnumber_mask* and click Save
1. Close Microsoft PowerPoint - there is not need to save the presentation

#### Determine image pixel size
1. Navigate to the images you scanned, right click on of them, and select Properties
1. Navigate to the Details tab and the Image section
1. Make note of the Dimensions, for example 6240 X 4160

#### Edit background image pixels in Microsoft Paint
1. Open Microsoft Paint
1. Click File > Open
1. Navigate to the mask you created and click Open
    -  Change the Zoom Level to 25%
1. Navigate to the Home tab and select Resize
1. In the *Resize by* section, select Pixels
1. Refer back to the dimensions you noted and enter the pixel size
1. Make sure the Maintain Aspect Ratio box is checked
1. Click OK
1. Click File > Save As > JPEG picture
1. Navigate to the background image location, rename the file as *itemnumber_mask-pixels*, and click Save
1. Close Microsoft Paint-->
