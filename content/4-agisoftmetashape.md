---
title: Creating 3D Models with Agisoft Metashape
nav: Agisoft
---

-----------
**Is this your first model creation?** 
**Need a reminder** 
Check out our [Agisoft Metashape Tutorial series](https://youtube.com/playlist?list=PL2VCfpBUgJGi2GJFro_hCa6Kxohlxlxt8) on YouTube, demonstrating each of the steps below. The videos seem to play best when viewed in Firefox or Edge.

- [Preparation](#preparation)
- [Step 1: Create a new Agisoft Project](#newagisoftproject)
- [Step 2: Add photos to the Agisoft Project](#addphotos)
- [Step 3: Import a background image/mask](#importmasks) 
- [Step 4: Align photos](#alignphotos)
- [Step 5: Refine the bounding box](#refinebounding)
- [Step 6: Build the dense cloud](#builddense)
- [Step 7: Build the mesh](#buildmesh)
- [Step 8: Edit the mesh](#editmesh)
- [Step 9: Apply masks from the model](#masksfrommodel)
- [Step 10: Align chunks](#alignchunks) 
- [Step 11: Merge chunks](#mergechunks)
- [Step 12: Build texture](#texture) <!--[Step 13: Place markers](#markers) - [Step 14: Align model orientation](#alignmodel)-->
- [Step 13: Export the 3D model](#export)
- [Step 14: View the 3D model](#view)

{:#preparation}
### Preparation
Follow along with the [Agisoft Metashape Tutorial series] to familiarize yourself with the program and process. 
#### Open 3D folder associated with the object you are modeling 
  -  You should see the *Processed-JPEG*, *TIFF*, *RAW*, and *Testshots-Errors* folders 
     If not already present: add *Models* and *Project* folders

{:#newagisoftproject}
### Step 1: Create a new Agisoft Project
1. Open Agisoft Metashape
1. Click File > Save As
1. Navigate to and double-click on the correct item's folder (for example: CE_CA_D4_2394)
2. Double-click on *Project* folder
3. Type the file name, which should include the cabinet letter, drawer number, and item number
    - For example: CE_CA_D4_2349_3Dproject 
4. Click Save

{:#addphotos}
### Step 2: Add photos to the Agisoft Project
We will need to add photos in two separate chunks to make sure that they are aligned correctly. 

1. Double click Chunk 1 to select, right click > click Add Folder
1. Navigate to the correct 3D artifact photos folder
1. Double click on Processed-JPEG
1. Single click on the *View 1* folder in the photos folder > click Select Folder
1. Make sure that single cameras and add all images to one chunk are selected > Click OK
1. Under Chunk 1, right click and select Add Chunk
1.Repeat above steps to upload *View 2* photos to Chunk 2
1. Click Save

Next, we need to delete the photos that include the sticky notes or index cards since we don’t want to use these in our model creation. 
1. Double click Chunk 1 > navigate to the Photos section
1. Single click on a photo with a sticky note or index card
1. Click the X icon and click Yes to remove one camera
1. Repeat these steps to delete all of the photos with sticky notes or index cards in Chunk 1
1. Repeat *all steps* for Chunk 2
1. Click Save once you've deleted all of the photos with sticky notes/index cards in Chunk 1 and Chunk 2

<!--#### Estimate image quality
1. Photos > Details > Highlight all photos > Right click selected photos > Estimate Image Quality > All cameras > OK
1. Click Save

Image quality will appears in the "Quality" column. Agisoft recommends disabling images with quality less than 0.5 units.

Keep the Agisoft Metashape Project open.

After adding photos to the Agisoft Project, we have to create *masks* to hide the background that appears in our photogrammetry images. [Creating a Mask](#createamask) instructions -->

{:#importmasks}
### Step 3: Import a background image/mask
In most cases the background color will depend on the object being digitized. You will likely need to make a new background image/mask for each object, **follow the** [Creating a Mask](#createamask) **instructions.**

1. At the top of the screen, click Workflow > Batch Process
1. Click Add
1. Click in the first dropdown box and scroll to and select Import Masks
1. Confirm that All chunks is selected in the second dropdown box
1. In the Parameters box, double click each box to set:
    - Method = From background
    - Operation = Replacement
    - Tolerance = 20
1. Double click in the filename template box and type the file name for the _mask-pixels.jpg file you created
    - For example: CE_1245_mask-pixels.jpg
        - Don't forget to add the *.jpg*
1. Double click in the Folder box > navigate to the folder where the mask image has been saved
1. Click the folder > click Select Folder
1. Click OK then click OK again
1. Once the masking process is complete, click Close
1. Then click Save

The masking process should take approximately 5 minutes. 

Double click on a few images in the Photos section to review the mask application. Don’t worry if the base is still visible or if small portions of the artifacts have been masked, this will be fixed later in the 3D model creation process.

However, if too much of the artifact is masked, complete the [Import masks](#importmasks) tasks again but *lower the tolerance to 10.*

{:#alignphotos}
### Step 4: Align photos
1. Click Workflow > Batch Process
1. Uncheck the box for previous job, if necessary
1. Click Add
1. Click in the first dropdown box and scroll to and select Align Photos
1. Confirm that All chunks is selected in the second dropdown box
1. In the Parameters box, double click each box to set:
    - Accuracy = High
    - Generic preselection = Yes
    - Reference preselection = Disabled
    - Reset current alignment = No
    - Key point limit = 80,000
    - Key point limit per Mpx = 1,000
    - Tie point limit = 8,000
    - Apply masks to = Key points
    - Exclude stationary tie points = Yes
    - Guided image matching = No
    - Adaptive camera model fitting = Yes
1. Click OK then click OK again
1. Once the photos have aligned, click Close
1. Then click Save

Photo alignment should take between 2 to 15 minutes, depending on the number of images.

At the top of the screen, click Model to navigate to the initial model that Agisoft created during image alignment. 

{:#refinebounding}
### Step 5: Refine the bounding box
The bounding box is the light grey 3D cube that encapsulates the object. The object needs to completely contained in this cube. To check this:
1. Double click Chunk 1 > double click on the model to center it within the screen
1. Use the navigation ball to spin and flip the model to make sure it is contained within the bounding box
1. If a portion of the model is cut off, click the Region icon > select Resize region
1. Drag to resize the region so that the entire model is inside the bounding box
1. After you've refined the bounding box for Chunk 1, click Save
1. Repeat *all steps* for Chunk 2 > click Save

{:#builddense}
### Step 6: Build dense cloud
1. Click Workflow > Batch Process
1. Uncheck the box for previous job, if necessary
1. Click Add
1. Click in the first dropdown box and scroll to and select Build Dense Cloud
1. Confirm that All chunks is selected in the second dropdown box
1. In the Parameters box, set:
    - Quality = Medium
    - Depth filtering = Mild
    - Reuse depth maps = Yes
    - Calculate point colors = Yes
    - Calculate point confidence = Yes
1. Click OK then click OK again
1. Once dense cloud generation is complete, click Close
1. Then click Save

Dense cloud generation should take between 5 to 15 minutes for Medium quality and up to 1.5 hours for High quality.

Click the Dense Cloud icon to see the results.

{:#buildmesh}
### Step 7: Build the mesh
1. Click Workflow > Batch Process
1. Uncheck the box for previous job, if necessary
1. Click Add
1. Click in the first dropdown box and scroll to and select Build Mesh
1. Confirm that All chunks is selected in the second dropdown box
1. In the Parameters box, set:
    - Texture type = Dense cloud
    - Surface type = Arbitrary (3D)
    - Depth maps quality = High
    - Face count = High
    - Custom face count value = Generated automatically, so you don’t need to change that
    - Depth filtering = Mild
    - Interpolation = Enabled
    - Point classes = All
    - Calculate vertex colors = Yes
    - Reuse depth maps = Yes
    - Use strict volumetric masks = No
1. Click OK then click OK again
1. Once mesh generation is complete, click Close
1. Then click Save

Mesh generation should take approximately 5 minutes.

Click the Model Shaded icon to see the results.

{:#editmesh}
### Step 8: Edit the mesh
1. Double click Chunk 1 > double click on the model to center it within the screen
1. Remove clay base and : click the navigation icon and use the navigation ball to spin and flip the model so that the base is relatively flat to start
1. Click the Zoom in and Zoom out icons to make the model bigger or smaller within the screen
1. Click the Selection icon > choose Rectangle selection
1. Draw a rectangle around the base area you want to delete
    - Try to be as careful as possible when deleting the clay/eraser base from the model as you don’t want to remove too much of the object itself
        - But don’t worry about perfection as Agisoft Metashape will use the images in the other chunk to reconstruct the base areas that have been removed
    - If you do end up highlighting an area you don’t want to delete, simply click in a blank area of the bounding box, then redraw your rectangle
    - Ctrl+Z can also be used to undo a previous mistake
1. Once you are happy with the shape and area you’ve highlighted, press Delete on your keyboard
1. Click the navigation icon and use the navigation ball to spin and flip the model to the other side
1. If you still need to delete some of the base, click the Selection icon > choose either Rectangle selection or Freeform selection
1. Draw a shape around the base area you want to delete > press Delete on your keyboard
    - You might need to use the navigation icon and navigation ball to tilt the model so you can delete any remaining portion of the base
1. Once we’ve deleted the base on both sides of the model, we need to delete the stray points
1. Click the Zoom out icon to and zoom out until you see the entire bounding box
1. Click the Selection icon > choose Freeform selection
1. Draw a shape around the stray points you want to delete
1. Once you are happy with the shape and area you’ve highlighted, press Delete on your keyboard
1. Continue to delete any stray points that appear in the bounding box
    - You may need to use the Zoom in and Zoom out icons as well as click the navigation icon and use the navigation ball to spin and flip the model to find and remove all stray points
1. Once you've edited the mesh for Chunk 1 > click Save
1. Repeat *all steps* for Chunk 2 > click Save

{:#masksfrommodel}
### Step 9: Apply masks from model
1. Double click Chunk 1
1. Click File > Import > Import Masks
1. In the Parameters section, set:
    - Method = From model
    - Operation = Replacement
    - All cameras = Box checked/selected
1. Click OK
1. Click View > Photos
1. Double click on a photo to the see the result of the mask 
    - We can now see that the entire background, including the base, has been masked
1. After the new mask is imported for Chunk 1, click Save > click the X icon next to the image to close it
1. Repeat *all steps* for Chunk 2 > click Save

Applying masks from the model should take approximately 1 minute per chunk.

{:#alignchunks}
### Step 10: Align chunks
1. Click Workflow > Align Chunks
1. Confirm that both chunks are checked
1. In the Parameters section, set:
    - Method = Point based
    - Accuracy = High
    - Key point limit = 80,000
    - Apply masks to = Key points
    - Generic preselection = Box checked/selected
1. Click OK
    - The status box will disappear once complete
1. After chunk alignment is complete, click Save
A **T** sympbol will appear next to each Chunk in the *Workspace* if successful. 
Chunk alignment should take approximately 2 minutes.

{:#mergechunks}
### Step 11: Merge chunks
1. Click Workflow > Merge Chunks
1. Check the boxes for Chunk 1 and Chunk 2
1. Check the boxes for:
    - Merge dense clouds
    - Merge models
    - Merge depth maps
1. Click OK
    - The status box will disappear once complete
1. Once this process is complete, we will see a new chunk named Merged Chunk
1. Double click on the Merged Chunk to see the results
    - If our model creation process was successful Agisoft will have taken the models from both Chunk 1 and Chunk 2 and combined them to create a new and model
    - Sometimes when merging chunks, the new chunk will disappear from the screen. If this happens, use the Zoom out icon to zoom out until you see it, double click on the model to center it within your screen, then use the Zoom In icon to zoom back in
1. Once merging chunks is complete, click Save

Merging chunks should take approximately 2 minutes.

### Step 11.5: Decimate Mesh
Prior to building the texture, the Mesh needs to be downsized. 
- Navigate to *Tools* > *Mesh* > *Decimate Mesh* 
- Double click in the second box and change to 20,000
- Click *OK* 

{:#texture}
### Step 12: Build texture
1. Double click on the Merged Chunk
1. Click Workflow > Build Texture
1. In the Parameters section, set:
    - Texture type = Diffuse map
    - Source data = Images
    - Mapping mode = Generic
    - Blending mode = Mosaic
    - Texture size/count = Generated automatically, so you don’t need to change that
    - Advanced section:
        - Enable hole filling = Box checked/selected
        - Enable ghosting filter = Box checked/selected
1. Click OK
    - The status box will disappear once complete
1. Once texture generation is complete, click Save
1. Click Save after building texture

Click the Model Shaded icon and select Model Textured to see the results.

<!-- {:#markers}
### Step 13: Place markers
Placing markers allow us to embed the size of the object into the file so that it can be viewed and printed at a correct scale. 

1. Double click on the Merged Chunk
1. If the Photos section is not visible, click View > Photos
1. Hold down the CTRL key on your keyboard
1. Click on five photos from a high view that are right next to each other
1. Click Tools > Markers > Detect Markers
1. In the Parameters section, set:
    - Marker type = Cross (non coded)
    - Tolerance = 15
    - Maximum residual (pix) = 10
    - Process selected cameras only = Box checked/selected
1. Click OK
1. Once the process is complete, click Save

Then we have determine which of the markers/points are directly opposite from each other.
1. Navigate to the Photos section > Double click on one of the photos that you applied the markers to
1. Review the photo and make a note about which points are directly oppposite from each other
    - In this model, points 1 and 3 are directly opposite from each other and points 2 and 4 are directly opposite from each other

Once you make note of the points that are directly oppposite from each other
1. Navigate to the Reference section
1. Hold down the CTRL key on your keyboard
1. Click on the first two points that are directly opposite from each other to highlight them
    - In this example, that is point 1 and point 3
1. Right click > click Create Scale Bar
1. Double click in the newly created Distance box
1. Type 0.12
1. Press Enter on your keyboard
1. Hold down the CTRL key on your keyboard
1. Click on the next two points that are directly opposite from each other to highlight them
    - In this example, that is point 2 and point 4
1. Right click > click Create Scale Bar
1. Double click in the newly created Distance box
1. Type 0.12
1. Press Enter on your keyboard
1. Click the Update Transform icon to apply the scale across all images in the model
1. Click Save

If the model disappeared, use the Zoom out icon to zoom out until you see it, double click on the model to center it within your screen, then use the Zoom in icon to zoom back in. You can now see the scale bar we have created.

{:#alignmodel}
### Step 14: Align model orientation
Sometimes, the orientation of the model can appear correct in Agisoft Metashape but incorrect when exported.

To align the model orientation:
1. Click Model > View Mode > Perspective/Orthographic
1. Click Model > Predefined Views > Bottom
1. Click the Object icon > choose Rotate Object
1. Rotate the model so that the bottom of the artifact is facing you
1. To check the model orientation, click Model > Predefined Views > Front or Top and Back, etc.
1. Once you are happy with the model's orientation, click Save -->

{:#export}
### Step 13: Export 3D model
We will export the 3D model in three different file formats.

Wavefront OBJ model (.obj)
1. Click File > Export > Export Model
1. Navigate to and double-click on the correct item's folder in your personal OneDrive (for example: CE_CabinetA_D4_2394)
1. Double-click on the *Models* folder
1. Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
1. Set the Save as type to *Wavefront OBJ*
1. Click Save
1. In the Export Model dialog box, set:
    - Export texture = JPEG
1. Click OK

Wavefront OBJ models generate two additional files that are associated with the model: an .mtl file and a .jpg file. All three files (.obj, .mtl, and .jpg) must be placed in the same folder.

STL model (.stl)
1. Click File > Export > Export Model
1. Navigate to and double-click on the correct item's folder in your personal OneDrive (for example: CE_CabinetA_D4_2394)
1. Double-click on the *Models* folder
1. Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
1. Set the Save as type to *STL models*
1. Click Save
1. Click OK, if prompted

X3D model (.x3d)
1. Click File > Export > Export Model
1. Navigate to and double-click on the correct item's folder in your personal OneDrive (for example: CE_CabinetA_D4_2394)
1. Double-click on the *Models* folder
1. Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
1. Set the Save as type to *X3D models*
1. Click Save
1. Click OK, if prompted

{:#view}
### Step 15: View 3D model
1. Open the 3D viewer app
1. Click File > Open
1. Navigate to the folder where the model was saved
1. Select the model you want to view
1. Click Open

The STL file will not include the artifact’s original colors, but is often used for printing a 3D model. In comparison, the OBJ file will include the artifact’s original colors, and is often used for display purposes on the web.

### Step 16: Edit model in MeshMixer 
1. Open MeshMixer program 
2. Drag and drop .stl file into MeshMixer
3. On left side, click *Analysis* > *Inspector* > CLick Auto Repair All > choose Done
4. Navigate to *Edit* > choose *Transform* 
5. Move the red, blue and green rounded bars until the object orrientation is correct. We want the green arrow to be vertical. To ensure this, on the faint circle around the object a "L" and "W" are present and the "L" is usually green, choose the "W". 
6. To resize the object to reflect acutal size. Double click in the *Size Y* and enter the length of the object in mm. 
7. Click Accept 
8. Export the .stl 
9. File > Export > choose .stl
10. You will simply replace the previously created .stl with the new MeshMixer version.
-------------
{:#createamask}
### Create a mask
You should be able to use the same background image/mask across objects, so long as the Foldio background color doesn't change. If you need to make a new background image/mask, follow the instructions below.

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
1. Close Microsoft Paint
