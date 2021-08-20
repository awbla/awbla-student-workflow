---
title: Creating 3D Models with Agisoft Metashape
nav: Agisoft
---

-----------
- [Create a new Agisoft Project](#newagisoftproject)
- [Add photos to Agisoft Project](#addphotos)
- [Create a mask](#mask)
- [Import and edit masks](#importeditmasks)  

{:#newagisoftproject}
### Create a new Agisoft Project
- Open Agisoft Metashape
- Click File > Save As > name project using the following convention: *itemnumber_3Dproject*

{:#addphotos}
### Add photos to Agisoft Project
- Navigate to the Workflow tab and click Add Photos
- Navigate to the Source Folder and click Select Folder
    - If prompted select *Single Camera*
-  Photos will be added to Workspace > Chunk # (# of cameras)
    - *# of cameras refers to the number of photos added to the project*
- Click Save

After adding photos to the Agisoft Project, we have to create *masks* to hide the background that appears in our photogrammetry images.

{:#mask}
### Create a mask
Documentation based on Samantha Porter's [Supplemental Instructions on Background Masking](https://conservancy.umn.edu/handle/11299/172480).

#### Create a background image in Microsoft PowerPoint
- Open Microsoft PowerPoint. Create a blank presentation.
- Navigate to the Insert tab, click Pictures > This Device. Navigate to the set of images you want to create a mask for, select one of the images, and click Insert.
- Navigate to the Picture Format tab and make note of the image size, for example 7.5" by 11.25".
- Navigate to the Insert tab, click Shapes > Rectangle. Drag to create a small rectangle.
- In the Shape Format tab, click Shape Outline > No Outline.
- In the Shape Format tab, click Shape Fill > Eyedropper.
- Click the eyedropper within your image's original background to select that color.
- Click the rectangular image, navigate to the Shape Format tab, and change the shape size so that it matches the original image.
- Right click the shape and select Save as Picture
- Navigate to (file location)
- Rename the file as *itemnumber_mask*, change the Save as type to JPEG File, and click Save

#### Determine image pixel size
- Navigate to the images you scanned, right click, and select Properties
- Navigate to the Details tab and the Image section
- Make note of the Dimensions, for example 6240 X 4160

#### Edit background image pixels in Microsoft Paint
- Open Microsoft Paint.
- Click File > Open.
- Navigate to the mask you created and click Open.
    -  Change the Zoom Level to 25%.
- Navigate to the Home tab and select Resize.
- In the Resize by section, select Pixels.
- Enter the pixel size that matches the original image.
- Make sure the Maintain Aspect Ratio box is checked.
- Click OK
- Click File > Save As > JPEG picture
- Navigate to the background image location, rename the file as *itemnumber_mask-pixels*, and click Save.

{:#importeditmasks}
### Import and edits masks

#### Import masks
- Click File > Import > Import Masks and select the following options
    - Method = From Background
    - Operation = Replacement
    - Filename template = Type filename for mask and include the file extension, such as *itemnumber_mask-pixels.jpg*
    - Tolerance = 25
    - Apply to = All cameras
- Click OK
- Navigate to the folder where the mask is located and click OK

The masking process should take approximately 5 minutes.