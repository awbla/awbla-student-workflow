---
title: Creating 3D Models with Agisoft Metashape
nav:
---

-----------
- [Create a new Agisoft Project](#newagisoftproject)
- [Add photos to Agisoft Project](#addphotos)
- [Create a mask](#mask)
- [Import and edit masks](#importeditmasks) 
- [Align photos and refine bounding box position](#alignphotos)
- [Build and edit dense cloud](#dense)
- [Build mesh](#mesh)
- [Build texture](#texture)
- [Align model orientation](#alignmodel)
- [Export 3D model](#export)
- [View 3D model](#view)

{:#newagisoftproject}
### Create a new Agisoft Project
- Open Agisoft Metashape
- Click File > Save As > name project using the following convention: *itemnumber_3Dproject*

{:#addphotos}
### Add photos to Agisoft Project
- Navigate to the Workflow tab and click Add Photos or Add Folder
- Navigate to the Source Folder
- Select the photos you want to add or click Slect Folder
    - When prompted select *Single Cameras* <!--and *Create chunk from each subfolder*-->
- Photos will be added to Workspace > Chunk # (# of cameras)
    - *# of cameras refers to the number of photos added to the project*
- Click Save
- If the photos aren't visible, navigate to the View tab and click Photos
- Delete the photos with the sticky notes
    - Click on a photo in the *Photos* area
    - Click the *X* icon (Remove Cameras)
    - Repeat steps until all sticky note photos are deleted
- Click Save

Keep the Agisoft Metshape Project open.

After adding photos to the Agisoft Project, we have to create *masks* to hide the background that appears in our photogrammetry images.

{:#mask}
### Create a mask
The following documentation on creating a mask is adapted from Samantha Porter's "Supplemental Instructions on Background Masking" (file name: [Supplemental_Instructions_1_Background_Masking.pdf)](https://conservancy.umn.edu/handle/11299/172480).

#### Create a background image in Microsoft PowerPoint
- Open Microsoft PowerPoint and create a blank presentation
    - Delete the empty text boxes
- Navigate to the Insert tab, click Pictures > This Device
- Navigate to the set of images you want to create a mask for, select one of the images, and click Insert
- Navigate to the Picture Format tab and make note of the image size, for example 7.5" by 11.25"
- Navigate to the Insert tab, click Shapes > Rectangle
- Drag to create a small rectangle and click on it
- In the Shape Format tab, click Shape Outline > No Outline
- In the Shape Format tab, click Shape Fill > Eyedropper
- Click the eyedropper within your image's original background to select that color
- Click the rectangular image, navigate to the Shape Format tab, and change the shape size so that it matches the original image
- Right click the shape and select Save as Picture
- Navigate to (file location)
- Change the Save as type to JPEG File
- Rename the file as *itemnumber_mask* and click Save
- Close Microsoft PowerPoint - there is not need to save the presentation

#### Determine image pixel size
- Navigate to the images you scanned, right click on of them, and select Properties
- Navigate to the Details tab and the Image section
- Make note of the Dimensions, for example 6240 X 4160

#### Edit background image pixels in Microsoft Paint
- Open Microsoft Paint
- Click File > Open
- Navigate to the mask you created and click Open
    -  Change the Zoom Level to 25%
- Navigate to the Home tab and select Resize
- In the *Resize by* section, select Pixels
- Refer back to the dimensions you noted and enter the pixel size
- Make sure the Maintain Aspect Ratio box is checked
- Click OK
- Click File > Save As > JPEG picture
- Navigate to the background image location, rename the file as *itemnumber_mask-pixels*, and click Save
- Close Microsoft Paint

{:#importeditmasks}
### Import and edits masks

{:#importmasks}
#### Import masks
- Navigate to the Agisoft Metashape Project
- Click File > Import > Import Masks 
- Select the following options
    - Method = From Background
    - Operation = Replacement
    - Filename template = Type the filename for the mask and include the file extension, such as *itemnumber_mask-pixels.jpg*
    - Tolerance = 25
    - Apply to = All cameras
- Click OK
- Navigate to the folder where the mask is located and click Select Folder

The masking process should take approximately 5 minutes.

#### Edit masks
Once the masks are applied, double click on an image in the Photos section to review the mask application.

- If not enough of the background is masked, follow the [Import masks](#importmasks) instructions but raise the tolerance to 40
- If too much of the artifact is masked, follow the [Import masks](#importmasks) instructions but lower the tolerance to 10

To edit the mask application on individual images:
- Double click on the image whose mask you want to edit
- Click the Selection Tool and select Intelligent Scissors
- Click to create a free-form shape where you want to add or remove part of the mask
- Click back on the first dot to finish the shape
- Select one option:
    - Add selection = Add selected area to the mask
    - Subtract selection = Remove selected area from mask
- Click Save after editing each image's mask
- Follow these instructions to edit any other images.
- Click Save once you've finished all edits

{:#alignphotos}
### Align photos and refine the bounding box position
#### Align photos
- Select correct Chunk (if more than one is present)
- Click Workflow > Align Photos 
- Select the following options
    - Accuracy = High; Source
    - Generic preselection = Checked box
    - Reference preselection = Unchecked box <!-- this may change to Reference preselection > Source once we use scale bars -->
    - Advanced
        - Key point limit = 40,000
        - Tie point limit = 4,000
        - Apply masks to = Key Points
        - Exclude stationary tie points = Checked box
- Click OK
- Click Save after images have aligned 

Photo alignment should take approximately 15 minutes.

#### Refine the bounding box position
- Use *Resize Region*, *Move Region*, and *Rotate Region* to ensure that the entire object appears in the bounding box.
- Navigate to Object Tools and click Rotate Object to move the object so that it appears correctly in the grid.
- Click Save after refining the bounding box

{:#dense}
### Build and edit dense cloud

#### Build dense cloud
- Click Workflow > Build Dense Cloud and select the following options
    - Quality = Medium
    - Depth filtering = Mild
    - Calculate point colors = Checked box
    - Calculate point confidence = Checked box
- Click OK
- Click Save after the dense cloud is generated

Dense cloud generation should take approximately 15 minutes.

#### Edit dense cloud
- Click the Dense Cloud icon to view results
- Use the selection tools and delete/crop instruments to remove stray points from the dense cloud
- Click Save after deleting any points

{:#mesh}
### Build mesh
- Click Workflow > Build Texture and select the following options
    - Texture type = Dense cloud
    - Surface type = Arbitrary (3D)
    - Quality = Medium
    - Face count = Medium
    - Depth filtering = Mild
    - Interpolation = Enabled
    - Point classes = All
    - Calculate vertex colors = Yes
    - Reuse depth map = Yes
- Click Save after building mesh

Mesh generation should take approximately 5 minutes.

{:#texture}
### Build texture
- Click Workflow > Build Texture and select the following options
    - Texture type = Diffuse map
    - Source data = Images
    - Mapping mode = Generic
    - Blending mode = Mosaic
    - Texture size/count = Value is automatically entered
    - Enable hole filling = Checked box
    - Enable ghosting filter = Checked box
- Click Save after building texture

Texture generation should take approximately 2 minutes.

{:#alignmodel}
### Align model orientation
Sometimes, the orientation of model can appear correct in Agisoft Metashape but incorrect when exported.

To fix this:
- Click Model > View Mode > Perspective/Orthographic
- Click Model > Predefined Views > Bottom
- Click the Rotate Object icon and select Rotate Object
- Rotate object so that the bottom of the object is facing you
- Click Model > Predefined Views > Bottom / Top / Front / Back to check the model orientation
- Click Save once the orientation is correct

{:#export}
### Export 3D model
We will export the 3D model in three different file formats.

STL model (.stl)
- Click File > Export > Export Model
- Navigate to the destination folder
- Rename the file as *itemnumber_3Dproject-model*
- Select *.stl* as the file format
- Click Save

X3D model (.x3d)
- Click File > Export > Export Model
- Navigate to the  destination folder
- Rename the file as *itemnumber_3Dproject-model*
- Select *.x3d* as the file format
- Click Save

Wavefront OBJ model (.obj)
- Click File > Export > Export Model
- Navigate to the  destination folder
- Rename the file as *itemnumber_3Dproject-model*
- Select *.obj* as the file format
- Click Save
    - In the Export Model dialog box, select:
        - Export texture = JPEG

Wavefront OBJ models save the *texture image* as a separate file. Be sure to keep the texture file in the same folder as the .obj file.

{:#view}
### View 3D model
- Open Microsft 3D viewer
- Click File > Open
- Navigate to the folder where the model is located and click OK
