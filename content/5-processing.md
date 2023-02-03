---
title: Processing Scans and Adding Items to OneDrive
nav: Processing
topics:
---

-----------
### Background
After scanning and photography is complete, it is necessary to process the scans, add the items to OneDrive for storage, and transfer them to external hard drives for final access and preservation.

#### Processing Scans:
- [Processing Images](#images)  
- [Processing Documents](#documents) 

#### Adding Items to OneDrive:
- [Adding Documents to OneDrive](#adddocuments)
- [Adding Scanned Images to OneDrive](#addimages)
- [Adding Slides to OneDrive](#addslides)
- [Adding 2D Photos to OneDrive](#add2Dphotos)
- [Adding Photogrammetry Photos to OneDrive](#add3Dphotos)
- [Adding 3D Agisoft Projects to OneDrive](#add3Dprojects)

### Processing Scans
{:#images}
#### Processing Images

- Open Photoshop
- Then, go to File > Automate > Batch. 

{% include figure.html img="automate_batch.jpg" alt="Screenshot showing how to navigate to Adobe's batch process feature" caption="" width="50%" %}

- In the Batch window, select the Set 'photographs' and for the action select ‘photo tif>jpg’. 
    - For the Source, make sure folder is selected. Click Choose and select the tif folder where your new scans are stored. 
    - For the Destination, make sure folder is selected. Click Choose and select the access-JPG folder. 
    - Make sure the 'Override' box is checked under the save side
    - Click OK.

    {% include figure.html img="batch_tif_jpg_2.jpg" alt="Screenshot showing selections within Adobe's batch process feature" caption="" width="100%" %}

- After Photoshop has completed the action, make sure all the images have scanned/saved to the correct folder. 

In the access jpg folder, open images in Photoshop crop colorbar and straighten images. 
    To straighten, use ruler tool>image>image rotation>arbitrary. This will keep the image flat, rather than create layers. Save.

To adjust levels in photoshop go to image>adjustments>levels. A box will pop up, click auto and okay. Save.

Once levels are adjusted, go to image>auto color then try both image>auto contrast and image>auto tone. Whichever of these last two look better, use that and save.

- Once finished with the whole access jpg folder, go back to Photoshop to File > Automate > Batch. 
- In the Batch window, select Set 'photographs' and select the action ‘accessjpg>lowresjpg’. 
    - For the Source, make sure folder is selected. Click Choose and select the access jpg folder that contains all the adjusted images you just created. 
    - For the Destination, make sure folder is selected. Click Choose and select the lowres jpg folder. Make sure the file path reads the correct destination. 
    - Click OK.
    - Save

{% include figure.html img="batch_lowres.jpg" alt="intro image here" caption="" width="100%" %}

- After Photoshop has completed the action, make sure all the images have been saved to the correct folder. -->

--------------
{:#documents}
#### Processing Documents

- Select the document file(s) to be converted from your JPG folder. 
- Right-click on the .jpg file and select 'Covert to Adobe PDF'
    - If combining multiple page items, select all items, then right-click and select 'Combine with Adobe Acrobat'
    - Then click 'Combine' in the new window

{% include figure.html img="convert_to_pdf.jpg" alt="Screenshot showing how to navigate to options for converting or combining files to create a PDF" caption="" width="50%" %}

- After Adobe opens with the new PDF file, navigate to the toolbar on the right-side of the window
- Expand the toolbar so each tool's name is viewable (or hover over them to determine which tool is which)
- Select 'Scan and OCR'
- In the new toolbar that opens above the document, select 'Text Recognition'

{% include figure.html img="AdobePDFsteps.png" alt="Screenshot showing selections for Adobe's text recognition feature" caption="" width="100%" %}

- Wait until Adobe Acrobat completes the command
    -  Hint: The document will end up back at the first page when it is complete
- Save the document as a PDF following the naming rules established under 'File Naming'
    - Omit the '-001'
    - In cases of combined documents, Adobe will automatically change the file name to 'Binder 1' or somthing similar; rename the file following our guidelines
- When Adobe Acrobat opens, find 'Tools' in the top right corner of the screen and select Recognize Text > In this file. 

--------------
### Adding Items to OneDrive:


{:#adddocuments}
#### Adding Documents to OneDrive
Scanned documents saved in your OneDrive will need to be uploaded to the *Documents* folder in the AWBLA OneDrive.

##### Download the Documents folder structure prior to scanning
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Documents* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name {Folder} (to be edited by you)
            - PDF {Folder}
            - Processed-JPEG {Folder}
            - TIFF {Folder}
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Documents* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B1_F2_Item430)

##### Scan documents directly into the renamed item folder in your personal OneDrive
- Scan documents and save coverted documents into their appropriate folders within the renamed item folder
   - Save the PDF files (.pdf format) into the *PDF* parent folder
   - Save the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder
   - Save the TIFF files (.tif format) into the *TIFF* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Documents* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Documents* folder in the AWBLA OneDrive

--------------
{:#addimages}
#### Adding Scanned Images to OneDrive
Scanned images saved in your OneDrive will need to be uploaded to the *Photos-Negatives* folder in the AWBLA OneDrive.

##### Download the Photos-Negatives folder structure prior to scanning
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Photos-Negatives* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name {Folder} (to be edited by you)
            - Processed-JPEG {Folder}
            - TIFF {Folder}
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Photos-Negatives* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B76_F4-7)

##### Scan images directly into the renamed item folder in your personal OneDrive
- Scan images and save coverted images into their appropriate folders within the renamed item folder
   - Save the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder
   - Save the TIFF files (.tif format) into the *TIFF* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Photos-Negatives* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Photos-Negatives* folder in the AWBLA OneDrive

--------------
{:#addslides}
#### Adding Slides to OneDrive
Scanned slides saved in your OneDrive will need to be uploaded to the *Slides* folder in the AWBLA OneDrive.

##### Download the Slides folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Slides* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name {Folder} (to be edited by you)
            - Processed-JPEG {Folder}
            - TIFF {Folder}
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Slides* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B1_F2_Item430)

##### Scan slides directly into the renamed item folder in your personal OneDrive
- Scan slides and save coverted slides into their appropriate folders within the renamed item folder
   - Save the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder
   - Save the TIFF files (.tif format) into the *TIFF* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Slides* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Slides* folder in the AWBLA OneDrive

--------------
{:#add2Dphotos}
#### Adding 2D Photos to OneDrive
Images taken during 2D photography will need to be transferred from the memory card to the Desktop, from the desktop into your personal OneDrive with correct folder structure, then uploaded to the *2D Artifact Photos* folder in the AWBLA OneDrive.

##### Transfer the photos from the memory card to the Desktop
- Create a blank folder on the Desktop
- Transfer the complete file set(s) over into it.

##### Download the 2D Artifact Photos folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *2D Artifact Photos* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name {Folder} (to be edited by you)
            - Processed-JPEG {Folder}
            - Raw {Folder}
            - TIFF {Folder}
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *2D Artifact Photos* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_CabinetA_D4_2394)

##### Transfer the photos from the Desktop into the renamed item folder in your personal OneDrive
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the 2D artifact photos
- Copy the scanned images into their appropriate folders within the renamed item folder
   - Copy the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder
   - Copy the Raw files (.cr2 format) into the *Raw* parent folder
   - Copy the TIFF files (.tif format) itno the *TIFF* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *2D Artifact Photos* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *2D Artifact Photos* folder in the AWBLA OneDrive

--------------
{:#add3Dphotos}
#### Adding Photogrammetry Photos to OneDrive
Images taken during photogrammetry will need to be transferred from the memory card to the Desktop, from the desktop into your personal OneDrive with correct folder structure, then uploaded to the *3D Artifact Photos* folder in the AWBLA OneDrive.

##### Transfer the photos from the memory card to the Desktop
- Create a blank folder on the Desktop
- Transfer the complete file set(s) over into it.

##### Download the 3D Artifact Photos folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *3D Artifact Photos* folder
    - This folder set is organized as follows:
      - BeginHere-Item Name {Folder} (to be edited by you)
         - Processed-JPEG {Folder}
            - View 1 {Folder}
               - V1-Level1 {Folder}
               - V1-Level2 {Folder}
               - V1-Level3 {Folder}
            - View 2 {Folder}
               - V2-Level1 {Folder}
               - V2-Level2 {Folder}
               - V2-Level3 {Folder}
         - Raw {Folder}
            - View 1 {Folder}
               - V1-Level1 {Folder}
               - V1-Level2 {Folder}
               - V1-Level3 {Folder}
            - View 2 {Folder}
               - V2-Level1 {Folder}
               - V2-Level2 {Folder}
               - V2-Level3 {Folder}
         - TIFF {Folder}
            - View 1 {Folder}
               - V1-Level1 {Folder}
               - V1-Level2 {Folder}
               - V1-Level3 {Folder}
            - View 2 {Folder}
               - V2-Level1 {Folder}
               - V2-Level2 {Folder}
               - V2-Level3 {Folder}
         - Test Shots-Errors
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *3D Artifact Photos* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_CabinetA_D4_2394)

##### Transfer the photos from the Desktop into the renamed item folder in your personal OneDrive
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the photos
- Review the photos, using the start and stop Levels cards to identify the different views and levels
- Copy test shots photos into the *Test Shots-Errors* folder
    - Copy any test shots, including errors/whoops/mistakes shots into the this folder
- Copy the remaining photos, including the Start and Stop shots, into their appropriate folders within the renamed item folder
   - Copy the JPEG files (.jpeg format) into the appropriate View and Level subfolders within the *Processed-JPEG* parent folder
   - Copy the Raw files (.cr2 format) into the appropriate View and Level subfolders within the *Raw* parent folder
   - Copy the TIFF files (.tif format) into the appropriate View and Level subfolders within the *TIFF* parent folder
- Each of the sub-folders, like *Processed-JPEG > View 1 > V1-Level1*, will have at least 26 files total
   - This includes the 24 rotation shots, plus the Start and Stop shots

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *3D Artifact Photos* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *3D Artifact Photos* folder in the AWBLA OneDrive

--------------
{:#add3Dprojects}
#### Adding 3D Agisoft Projects to OneDrive
Files and models created when using Agisoft Metashape will need to be uploaded to the *3D Projects* folder in the AWBLA OneDrive.

#### Download the 3D Projects folder structure prior to starting a 3D project
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *3D Projects* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name {Folder} (to be edited by you)
            - Models {Folder}
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on your own personal OneDrive, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *3D Projects* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_CabinetA_D4_2394)

#### Save the 3D project in the renamed item folder in your personal OneDrive
- Open Agisoft Metashape
- Click File > Save As
- Navigate to and double-click on the correct item's folder in your personal OneDrive (for example: CE_CabinetA_D4_2394)
- Type the file name, which should include the cabinet letter, drawer number, and item number
    - For example: CE_CabinetA_D4_2349_3Dproject 
- Click Save

##### Upload the item folder to the AWBLA OneDrive
One the 3D project is complete:
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *3D Projects* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the appropriate item folder
    - This folder should includ the following:
        - An Agisoft project file (for example: CE_CabinetA_D4_2349_3Dproject.psx)
        - A sub-folder with all of the files associated with the Agisoft project (for example: CE_CabinetA_D4_2349_3Dproject.files)
        - A sub-folder named *Models* with the OBJ, STL, and X3D files
- Click Upload to add the folder and subfolders to the *3D Projects* folder in the AWBLA OneDrive
