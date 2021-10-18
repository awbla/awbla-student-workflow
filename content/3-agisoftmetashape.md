---
title: Creating 3D Models with Agisoft Metashape
nav: Agisoft
---

-----------
<!--Check out our [Agisoft Metashape Tutorial series](https://youtube.com/playlist?list=PL2VCfpBUgJGi2GJFro_hCa6Kxohlxlxt8) on YouTube, demonstrating each of the steps below.-->

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
- [Step 12: Build texture](#texture)
- [Step 13: Place markers](#markers)
- [Step 14: Align model orientation](#alignmodel)
- [Step 15: Export the 3D model](#export)
- [Step 16: View the 3D model](#view)

{:#newagisoftproject}
### Step 1: Create a new Agisoft Project
- Open Agisoft Metashape
- Click File > Save As
- Navigate to the correct folder
- Type the file name, which should include the cabinet letter, drawer number, and item number
    - For example: CE_CabinetA_D4_2349_3Dproject 

{:#addphotos}
### Step 2: Add photos to the Agisoft Project
We will need to add photos in two separate chunks to make sure that they are aligned correctly. 

- Double click Chunk 1 > click Workflow > click Add Folder
- Navigate to the correct 3D artifact photos folder
- Double click on Processed and double click on the correct item's folder
- Single click on the first folder in the photos folder > click Select Folder
- Make sure that single cameras and add all images to one chunk are selected > Click OK
- Navigate to the Workspace section > click the Add chunk icon
- Double click Chunk 2 > click Workflow > click Add Folder
- Navigate to the correct 3D artifact photos folder
- Double click on Processed and double click on the correct item's folder
- Single click on the second folder in the photos folder > click Select Folder
- Make sure that single cameras and add all images to one chunk are selected > Click OK
- Click Save

Next, we need to delete the photos that include the sticky notes or index cards since we don’t want to use these in our model creation. 
- Double click Chunk 1 > navigate to the Photos section
- Single click on a photo with a sticky note or index card
- Click the X icon and click Yes to remove one camera
- Repeat these steps to delete all of the photos with sticky notes or index cards in Chunk 1
- Repeat *all steps* for Chunk 2
- Click Save once you've deleted all of the photos with sticky notes/index cards in Chunk 1 and Chunk 2

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
### Step 3: Import a background image/mask
- Click Workflow > Batch Process
- Click Add
- Click in the first dropdown box and scroll to and select Import Masks
- Confirm that All chunks is selected in the second dropdown box
- In the Parameters box, set:
    - Method = From background
    - Operation = Replacemnt
    - Tolerance = 20
- Double click in the filename template box and type the file name for the mask
    - For example: Obsidian-Powder_mask-pixels.jpg
        - Don't forget to add the *.jpg*
- Double click in the Folder box > navigate to the folder where the mask image has been saved
- Click the folder > click Select Folder
- Click OK then click OK again
- Once the masking process is complete, click Close
- Then click Save

The masking process should take approximately 5 minutes. 

Double click on a few images in the Photos section to review the mask application. Don’t worry if the base is still visible or if small portions of the artifacts have been masked, this will be fixed later in the 3D model creation process.

However, if too much of the artifact is masked, complete the [Import masks](#importmasks) tasks again but *lower the tolerance to 10.*

{:#alignphotos}
### Step 4: Align photos
- Click Workflow > Batch Process
- Uncheck the box for previous job, if necessary
- Click Add
- Click in the first dropdown box and scroll to and select Align Photos
- Confirm that All chunks is selected in the second dropdown box
- In the Parameters box, set:
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
- Click OK then click OK again
- Once the photos have aligned, click Close
- Then click Save

Photo alignment should take between 2 to 15 minutes, depending on the number of images.

At the top of the screen, click Model to navigate to the initial model that Agisoft created during image alignment. 

{:#refinebounding}
### Step 5: Refine the bounding box
- Double click Chunk 1 > double click on the model to center it within the screen
- Use the navigation ball to spin and flip the model to make sure it is contained within the bounding box
- If a portion of the model is cut off, click the Region icon > select Resize region
- Drag to resize the region so that the entire model is inside the bounding box
- After you've refined the bounding box for Chunk 1, click Save
- Repeat *all steps* for Chunk 2 > click Save

{:#builddense}
### Step 6: Build dense cloud
- Click Workflow > Batch Process
- Uncheck the box for previous job, if necessary
- Click Add
- Click in the first dropdown box and scroll to and select Build Dense Cloud
- Confirm that All chunks is selected in the second dropdown box
- In the Parameters box, set:
    - Quality = Medium or High (this will be specified by the grant leadership team and the Digitization Manager)
    - Depth filtering = Mild
    - Reuse depth maps = Yes
    - Calculate point colors = Yes
    - Calculate point confidence = Yes
- Click OK then click OK again
- Once dense cloud generation is complete, click Close
- Then click Save

Dense cloud generation should take between 5 to 15 minutes for Medium quality and up to 1.5 hours for High quality.

Click the Dense Cloud icon to see the results.

{:#buildmesh}
### Step 7: Build the mesh
- Click Workflow > Batch Process
- Uncheck the box for previous job, if necessary
- Click Add
- Click in the first dropdown box and scroll to and select Build Mesh
- Confirm that All chunks is selected in the second dropdown box
- In the Parameters box, set:
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
- Click OK then click OK again
- Once mesh generation is complete, click Close
- Then click Save

Mesh generation should take approximately 5 minutes.

Click the Model Shaded icon to see the results.

{:#editmesh}
### Step 8: Edit the mesh
- Double click Chunk 1 > double click on the model to center it within the screen
- Click the navigation icon and use the navigation ball to spin and flip the model so that the base is relatively flat to start
- Click the Zoom in and Zoom out icons to make the model bigger or smaller within the screen
- Click the Selection icon > choose Rectangle selection
- Draw a rectangle around the base area you want to delete
    - Try to be as careful as possible when deleting the eraser base from the model as you don’t want to remove too much of the object itself
        - But don’t worry about perfection as Agisoft Metashape will use the images in the other chunk to reconstruct the base areas that have been removed
    - If you do end up highlighting an area you don’t want to delete, simply click in a blank area of the bounding box, then redraw your rectangle
- Once you are happy with the shape and area you’ve highlighted, press Delete on your keyboard
- Click the navigation icon and use the navigation ball to spin and flip the model to the other side
- If you still need to delete some of the base, click the Selection icon > choose either Rectangle selection or Freeform selection
- Draw a shape around the base area you want to delete > press Delete on your keyboard
    - You might need to use the navigation icon and navigation ball to tilt the model so you can delete any remaining portion of the base
- Once we’ve deleted the base on both sides of the model, we need to delete the stray points
- Click the Zoom out icon to and zoom out until you see the entire bounding box
- Click the Selection icon > choose Freeform selection
- Draw a shape around the stray points you want to delete
- Once you are happy with the shape and area you’ve highlighted, press Delete on your keyboard
- Continue to delete any stray points that appear in the bounding box
    - You may need to use the Zoom in and Zoom out icons as well as click the navigation icon and use the navigation ball to spin and flip the model to find and remove all stray points
- Once you've edited the mesh for Chunk 1 > click Save
- Repeat *all steps* for Chunk 2 > click Save

{:#masksfrommodel}
### Step 9: Apply masks from model
- Double click Chunk 1
- Click File > Import > Import Masks
- In the Parameters section, set:
    - Method = From model
    - Operation = Replacement
    - All cameras = Box checked/selected
- Click OK
- Click View > Photos
- Double click on a photo to the see the result of the mask 
    - We can now see that the entire background, including the base, has been masked
- After the new mask is imported for Chunk 1, click Save > click the X icon next to the image to close it
- Repeat *all steps* for Chunk 2 > click Save

Applying masks from the model should take approximately 1 minute per chunk.

{:#alignchunks}
### Step 10: Align chunks
- Click Workflow > Align Chunks
- Confirm that both chunks are checked
- In the Parameters section, set:
    - Method = Point based
    - Accuracy = High
    - Key point limit = 80,000
    - Apply masks to = Key points
    - Generic preselection = Box checked/selected
- Click OK
    - The status box will disappear once complete
- After chunk alignment is complete, click Save

Chunk alignment should take approximately 2 minutes.

{:#mergechunks}
### Step 11: Merge chunks
- Click Workflow > Merge Chunks
- Check the boxes for Chunk 1 and Chunk 2
- Check the boxes for:
    - Merge dense clouds
    - Merge models
    - Merge depth maps
- Click OK
    - The status box will disappear once complete
- Once this process is complete, we will see a new chunk named Merged Chunk
- Double click on the Merged Chunk to see the results
    - If our model creation process was successful Agisoft will have taken the models from both Chunk 1 and Chunk 2 and combined them to create a new and model
    - Sometimes when merging chunks, the new chunk will disappear from the screen. If this happens, use the Zoom out icon to zoom out until you see it, double click on the model to center it within your screen, then use the Zoom In icon to zoom back in
- Once merging chunks is complete, click Save

Merging chunks should take approximately 2 minutes.

{:#texture}
### Step 12: Build texture
- Double click on the Merged Chunk
- Click Workflow > Build Texture
- In the Parameters section, set:
    - Texture type = Diffuse map
    - Source data = Images
    - Mapping mode = Generic
    - Blending mode = Mosaic
    - Texture size/count = Generated automatically, so you don’t need to change that
    - Advanced section:
        - Enable hole filling = Box checked/selected
        - Enable ghosting filter = Box checked/selected
- - Click OK
    - The status box will disappear once complete
- Once texture generation is complete, click Save
- Click Save after building texture

Click the Model Shaded icon and select Model Textured to see the results.

{:#markers}
### Step 13: Place markers
Placing markers allow us to embed the size of the object into the file so that it can be viewed and printed at a correct scale. 

- Double click on the Merged Chunk
- If the Photos section is not visible, click View > Photos
- Hold down the CTRL key on your keyboard
- Click on five photos from a high view that are right next to each other
- Click Tools > Markers > Detect Markers
- In the Parameters section, set:
    - Marker type = Corss (non coded)
    - Tolerance = 15
    - Maximum residual (pix) = 10
    - Process selected cameras only = Box checked/selected
- Click OK
- Once the process is complete, click Save
- Navigate to the Reference section
- Hold down the CTRL key on your keyboard
- Click on points 1 and 3 to highlight them
- Rigth click > click Create Scale Bar
- Double click in the newly created Distance box
- Type 0.12
- Press Enter on your keyboard
- Hold down the CTRL key on your keyboard
- Click on points 2 and 4 to highlight them
- Rigth click > click Create Scale Bar
- Double click in the newly created Distance box
- Type 0.12
- Press Enter on your keyboard
- Click the Update Transform icon to apply the scale across all images in the model
- Click Save

If the model disappeared, use the Zoom out icon to zoom out until you see it, double click on the model to center it within your screen, then use the Zoom in icon to zoom back in. You can now see the scale bar we have created.

{:#alignmodel}
### Step 14: Align model orientation
Sometimes, the orientation of the model can appear correct in Agisoft Metashape but incorrect when exported.

To align the model orientation:
- Click Model > View Mode > Perspective/Orthographic
- Click Model > Predefined Views > Bottom
- Click the Object icon > choose Rotate Object
- Rotate the model so that the bottom of the artifact is facing you
- To check the model orientation, click Model > Predefined Views > Front or Top and Back, etc.
- Once you are happy with the model's orientation, click Save

{:#export}
### Step 15: Export 3D model
We will export the 3D model in three different file formats.

Wavefront OBJ model (.obj)
- Click File > Export > Export Model
- Navigate to the correct folder where the model will be saved
- Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
- Set the Save as type to *Wavefront OBJ*
- Click Save
- In the Export Model dialog box, set:
    - Export texture = JPEG
- Click OK

Wavefront OBJ models save the *texture image* as a separate file. Be sure to keep the texture file in the same folder as the OBJ file.

STL model (.stl)
- Click File > Export > Export Model
- Navigate to the correct folder where the model will be saved
- Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
- Set the Save as type to *STL models*
- Click Save
- Click OK, if prompted

X3D model (.x3d)
- Click File > Export > Export Model
- Navigate to the correct folder where the model will be saved
- Type the file name and add *-model* to the end of the file name
    - For example: CE_CabinetA_D4_2349_3Dproject-model
- Set the Save as type to *X3D models*
- Click Save
- Click OK, if prompted

{:#view}
### Step 16: View 3D model
- Open the 3D viewer app
- Click File > Open
- Navigate to the folder where the model was saved
- Select the model you want to view
- Click Open

The STL file will not include the artifact’s original colors, but is often used for printing a 3D model. In comparison, the OBJ file will include the artifact’s original colors, and is often used for display purposes on the web.

