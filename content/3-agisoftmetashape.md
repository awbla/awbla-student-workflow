---
title: Creating 3D Models with Agisoft Metashape
nav: Agisoft
---

-----------
- [Create a new Agisoft Project](#newagisoftproject)
- [Import masks](#importmasks) 
- [Align photos and refine bounding box position](#alignphotos)
- [Build and edit dense cloud](#dense)
- [Build and edit mesh](#mesh)
- [Align chunks](#alignchunks) 
- [Merge chunks](#mergechunks)
- [Build texture](#texture)
- [Place markers](#markers)
- [Align model orientation](#alignmodel)
- [Export 3D model](#export)
- [View 3D model](#view)

{:#newagisoftproject}
### Create a new Agisoft Project
- Open Agisoft Metashape
- Click File > Save As > name project using the following convention: *CE_Cabinet_Drawer_ItemNumber_3Dproject*
    - For example: CE_CabinetA_D4_2394_3Dproject 

{:#addphotos}
### Add photos to Agisoft Project
- Workflow > Add Folder > Top Down > Select Folder > Single cameras > Add all images to one chunk
- Workspace > Add Chunk > Click on chunk 2 > Workflow > Add Folder > Upright > Select Folder > Single cameras > Add all images to one chunk
- Click Save
- Delete images with sticky notes
- Click Save

<!--#### Estimate image quality
- Photos > Details > Highlight all photos > Right click selected photos > Estimate Image Quality > All cameras > OK
- Click Save

Image quality will appears in the "Quality" column. Agisoft recommends disabling images with quality less than 0.5 units.

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
- Close Microsoft Paint-->

{:#importmasks}
### Import masks
- Navigate to the Agisoft Metashape Project
- Workflow > Batch Process > Add > Import Masks > Apply to All Chunks
    - Method = From Background
    - Operation = Replacement
    - Tolerance = 20
    - Type file name = Type the filename for the mask and include the file extension, such as *itemnumber_mask-pixels.jpg*
    - Select folder where file is located
- OK > OK
- Click Save after masks have been imported

The masking process should take approximately 5 minutes.

Once the masks are applied, double click on an image in the Photos section to review the mask application.

- If not enough of the background is masked, follow the [Import masks](#importmasks) instructions but raise the tolerance to 30
- If too much of the artifact is masked, follow the [Import masks](#importmasks) instructions but lower the tolerance to 10

{:#alignphotos}
### Align photos and refine the bounding box position
#### Align photos
- Workflow > Batch Process > Uncheck box for Previous Job > Add > Align Photos > Apply to All Chunks
    - Accuracy = High
    - Generic preselection = Yes / Checked box
    - Reference preselection = Disabled / Unchecked box <!-- this may change to Reference preselection > Source once we use scale bars -->
    - Reset current alignment = No
    - Key point limit = 80,000
    - Key point limit per Mpx = 1,000
    - Tie point limit = 8,000
    - Apply masks to = Key points
    - Exclude stationary tie points = Yes
    - Guided image matching = No
    - Adaptive camera model fitting = Yes
- OK > OK
- Click Save after images have aligned 

Photo alignment should take between 5 to 15 minutes, depending on the artifact.

#### Refine the bounding box position
- Use *Resize Region*, *Move Region*, and *Rotate Region* to ensure that the entire object appears in the bounding box for each separate chunk.
- Double click on the artifact to ensure it appears within the navigation circle
- Click Save after refining the bounding box

{:#dense}
### Build dense cloud
- Workflow > Batch Process > Uncheck box for Previous Job > Add > Build Dense Cloud > Apply to All Chunks
    - Quality = Medium / High
    - Depth filtering = Mild
    - Reuse depth maps = Yes
    - Calculate point colors = Yes
    - Calculate point confidence = Yes
- OK > OK
- Click Save after the dense cloud is generated

Dense cloud generation should take approximately 15 minutes for Medium quality and 1.5 hours for High quality.

{:#mesh}
### Build and edit mesh

#### Build mesh
- Workflow > Batch Process > Uncheck box for Previous Job > Add > Build Mesh > Apply to All Chunks
    - Texture type = Dense cloud
    - Surface type = Arbitrary (3D)
    - Quality = High
    - Face count = High
    - Custom face count = automatically entered
    - Depth filtering = Mild
    - Interpolation = Enabled
    - Point classes = All
    - Calculate vertex colors = Yes
    - Reuse depth map = Yes
    - Use strict volumetric masks = No
- OK > OK
- Click Save after building mesh

Mesh generation should take approximately 5 minutes.

#### Edit mesh
For each model:
- Click the Model icon to view results
- Use the selection tools and and the *Delete* button on your keyboard to remove the eraser base and the stray points from the mesh
- Click Save after deleting any points

### Apply masks from model
For each model:
- Click File > Import > Import Masks
    - Method = From model
    - Operation = Replacement
    - Apply to = All cameras
- Click Save after mask is imported

This process should take approximately 1 minute

{:#alignchunks}
### Align chunks
- Workflow > Align Chunks > Check boxes for correct chunks
    - Method = Point based
    - Accuracy = High
    - Key point limit = 80,000
    - Apply masks to = Key points
    - Generic preselection = Yes / checked box
- Click Save after aligning chunks

Chunk alignment should take approximately 2 minutes.

{:#mergechunks}
### Merge chunks
- Workflow > Merge Chunks > Check boxes for correct chunks
    - Merge dense clouds = Checked box
    - Merge models = Checked box
    - Merge depth maps = Checked box
- Click Save after merging chunks

Merging chunks should take approximately 2 minutes.

{:#texture}
### Build texture
- Double click the merged chunk > click Workflow > Build Texture 
    - Texture type = Diffuse map
    - Source data = Images
    - Mapping mode = Generic
    - Blending mode = Mosaic
    - Texture size/count = Value is automatically entered
        - Advanced:
            - Enable hole filling = Checked box
            - Enable ghosting filter = Checked box
- Click Save after building texture

Texture generation should take approximately 2 minutes.

{:#markers}
### Place markers
- Photos > Select 5 photos from a "high" view that are next to each other
- Tools > Markers > Detect Markers > 
    - Marker type = Cross (non coded)
    - Tolerance = 15
    - Maximum residual (pix) = 10
    - Process selected cameras only = Checked box
- Click OK
- Click Save
- Reference > CTRL click on markers 1 and 3 > Right Click > Create Scale Bar
- Double click in the Distance box > type "0.12" > Hit Enter on keyboard
- Reference > CTRL click on markers 2 and 4 > Right Click > Create Scale Bar
- Double click in the Distance box > type "0.12" > Hit Enter on keyboard
- Click in the Distance block and enter "0.12"
- Click "Update Transform" icon
- Click Save

Marker placement should take approximately 2 minutes.

{:#alignmodel}
### Align model orientation
Sometimes, the orientation of the model can appear correct in Agisoft Metashape but incorrect when exported.

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
- Rename the file as *CE_Cabinet_Drawer_ItemNumber_3Dproject-model*
    - For example: CE_CabinetA_D4_2394_3Dproject-model
- Select *.stl* as the file format
- Click Save

X3D model (.x3d)
- Click File > Export > Export Model
- Navigate to the  destination folder
- Rename the file as *CE_Cabinet_Drawer_ItemNumber_3Dproject-model*
- Select *.x3d* as the file format
- Click Save

Wavefront OBJ model (.obj)
- Click File > Export > Export Model
- Navigate to the  destination folder
- Rename the file as *CE_Cabinet_Drawer_ItemNumber_3Dproject-model*
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
