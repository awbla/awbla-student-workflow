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

- If it hasn’t been done already, go to the folder for this scanning project (in your personal ‘Scans’ folder) and make two new folders: one named ‘access jpg’, and the other ‘lowres jpg’. 
- Open Photoshop. Go to File > Automate > Batch. 

{% include figure.html img="automate_batch.jpg" alt="intro image here" caption="" width="50%" %}

- In the Batch window, select the action ‘tif>jpg’. If this action doesn’t exist on your workstation yet, ask a supervisor how to create it. 
    - For the Source, make sure folder is selected. Click Choose and select the tif folder where your new scans are stored. 
    - For the Destination, make sure folder is selected. Click Choose and select the access jpg folder. 
    - Click OK.

    {% include figure.html img="batch_tif_jpg_2.jpg" alt="intro image here" caption="" width="100%" %}

- After Photoshop has completed the action, make sure all the images have scanned to the correct folder. 
- In the access jpg folder, open images in Photoshop and crop out the color bar. Balance images using the Levels tool in Photoshop if needed. Save and close images when done with them. 
- Once finished with the whole access jpg folder, go back to Photoshop to File > Automate > Batch. 
- In the Batch window, select the action ‘access>jpg’. This may also be called ‘300dpijpg’. If this action doesn’t exist, ask a supervisor how to create it.
    - For the Source, make sure folder is selected. Click Choose and select the access jpg folder that contains all the adjusted images you just created. 
    - For the Destination, make sure folder is selected. Click Choose and select the lowres jpg folder. Make sure the file path reads the correct destination. 
    - Click OK.

{% include figure.html img="batch_lowres.jpg" alt="intro image here" caption="" width="100%" %}

- After Photoshop has completed the action, make sure all the images have been saved to the correct folder.

--------------
{:#documents}
#### Processing Documents

- Select the file(s) to be converted from your lowres jpg folder. 
- Right-click selected items and select either ‘Convert to Adobe PDF’ or ‘Combine supported files in Acrobat’. This will open a window in Adobe Acrobat. 
    - If converting one file into a PDF, choose 'Convert to Adobe PDF'
    - If combining multiple files into one PDF (like a multi-page letter or document), choose 'Combine supported files in Acrobat'. A new window will pop up—click 'Combine'. 

{% include figure.html img="convert_to_pdf.jpg" alt="intro image here" caption="" width="50%" %}

- When Adobe Acrobat opens, find 'Tools' in the top right corner of the screen and select Recognize Text > In this file. 

{% include figure.html img="recognize_text.jpg" alt="intro image here" caption="" width="100%" %}

- Wait until Adobe Acrobat completes the command (the document will end up back at the first page). 
- Save the document as a PDF following the naming rules established under File Naming. 

--------------
### Adding Items to OneDrive:

{:#adddocuments}
#### Adding Documents to OneDrive
Scanned documents will need to be transferred from the desktop into correct folder structure, then uploaded to the *Documents* folder in the AWBLA OneDrive.

##### Download the Documents folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Documents* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name (to be edited by you)
            - PDF 
            - Processed-JPEG
            - Raw
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on the Desktop, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Documents* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B1_F2_Item430)

##### Transfer scanned documents from the Desktop into the renamed item folder
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the scanned documents
- Copy the scanned documents into their appropriate folders within the renamed item folder
   - Copy the Raw files (.tif format) into the *Raw* parent folder
   - Copy the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder
   - Copy the PDF files (.pdf format) into the *PDF* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Documents* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Documents* folder in the AWBLA OneDrive

--------------
{:#addimages}
#### Adding Scanned Images to OneDrive
Scanned images will need to be transferred from the desktop into correct folder structure, then uploaded to the *Photos-Negatives* folder in the AWBLA OneDrive.

##### Download the Photos-Negatives folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Photos-Negatives* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name (to be edited by you)
            - Processed-JPEG
            - Raw
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on the Desktop, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Photos-Negatives* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B76_F4-7)

##### Transfer scanned images from the Desktop into the renamed item folder
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the scanned images
- Copy the scanned images into their appropriate folders within the renamed item folder
   - Copy the Raw files (.tif format) into the *Raw* parent folder
   - Copy the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Photos-Negatives* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Photos-Negatives* folder in the AWBLA OneDrive

--------------
{:#addslides}
#### Adding Slides to OneDrive
Scanned slides will need to be transferred from the desktop into correct folder structure, then uploaded to the *Documents* folder in the AWBLA OneDrive.

##### Download the Slides folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *Slides* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name (to be edited by you)
            - Processed-JPEG
            - Raw
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on the Desktop, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *Slides* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_B1_F2_Item430)

##### Transfer scanned slides from the Desktop into the renamed item folder
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the scanned slides
- Copy the scanned slides into their appropriate folders within the renamed item folder
   - Copy the Raw files (.tif format) into the *Raw* parent folder
   - Copy the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *Slides* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *Slides* folder in the AWBLA OneDrive

--------------
{:#add2Dphotos}
#### Adding 2D Photos to OneDrive
Images taken during 2D photography will need to be transferred from the memory card to the Desktop, transferred from the desktop into correct folder structure, then uploaded to the *2D Artifact Photos* folder in the AWBLA OneDrive.

##### Transfer the photos from the memory card to the Desktop
- Create a blank folder on the Desktop
- Transfer the complete file set(s) over into it.

##### Download the 2D Artifact Photos folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *2D Artifact Photos* folder
    - This folder set is organized as follows:
        - BeginHere-Item Name (to be edited by you)
            - Processed-JPEG
            - Raw
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on the Desktop, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *2D Artifact Photos* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_CabinetA_D4_2394)

##### Transfer scanned images from the Desktop into the renamed item folder
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the 2D artifact photos
- Copy the scanned images into their appropriate folders within the renamed item folder
   - Copy the Raw files (.cr2 format) into the *Raw* parent folder
   - Copy the JPEG files (.jpeg format) into the *Processed-JPEG* parent folder

##### Upload the renamed item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *2D Artifact Photos* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the renamed item folder
- Click Upload to add the folder and subfolders to the *2D Artifact Photos* folder in the AWBLA OneDrive

--------------
{:#add3Dphotos}
#### Adding Photogrammetry Photos to OneDrive
Images taken during photogrammetry will need to be transferred from the memory card to the Desktop, transferred from the desktop into correct folder structure, then uploaded to the *3D Artifact Photos* folder in the AWBLA OneDrive.

##### Transfer the photos from the memory card to the Desktop
- Create a blank folder on the Desktop
- Transfer the complete file set(s) over into it.

##### Download the 3D Artifact Photos folder structure
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Click the box for the *3D Artifact Photos* folder
    - This folder set is organized as follows:
      - BeginHere-Item Name (to be edited by you)
         - Processed-JPEG
            - View 1
               - V1-Level1
               - V1-Level2
               - V1-Level3
            - View 2
               - V2-Level1
               - V2-Level2
               - V2-Level3
         - Raw
            - View 1
               - V1-Level1
               - V1-Level2
               - V1-Level3
            - View 2
               - V2-Level1
               - V2-Level2
               - V2-Level3
         - Test Shots-Errors
- Click Download and choose where to save the zip folder, if prompted
- Navigate to the downloaded zip folder (it should be named somthing like OneDrive_2021-10-28.zip)
- Right click the folder and select Extract All
- Click Browse, navigate to and click on the Desktop, then click Extract
    - Make sure the *Show extracted files when complete* box is checked
- Double-click on the *3D Artifact Photos* folder to open it
- Right-click the *BeginHere-Item Name* folder, select Rename, and type the Item Name (such as CE_CabinetA_D4_2394)

##### Transfer images from the Desktop into the renamed item folder
- Double-click on the renamed item folder to open it
- Open the Desktop folder that includes the photos
- Review the photos, using the start and stop Levels cards to identify the different views and levels
- Copy any test shots or errors/whoops/mistakes shots into the *Test Shots-Errors* folder
- Copy the remaining photos, including the Start and Stop shots, into their appropriate folders within the renamed item folder
   - Copy the Raw files (.cr2 format) into the appropriate View and Level subfolders within the *Raw* parent folder
   - Copy the JPEG files (.jpeg format) into the appropriate View and Level subfolders within the *Processed-JPEG* parent folder
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

##### Upload the item folder to the AWBLA OneDrive
- Navigate to the *CLIR-DHC Crabtree* folder in the AWBLA OneDrive
- Double-click on the *3D Projects* folder to open it
- Click Upload folder and select Folder
- Navigate to and single click the appropriate item folder
    - This folder should includ the following:
        - An Agisoft project file (for example: CE_CabinetA_D4_2349_3Dproject.psx)
        - A folder with all of the files associated with the Agisoft project (for example: CE_CabinetA_D4_2349_3Dproject.files)
        - A folder named Models with OBJ, STL, and X3D files
- Click Upload to add the folder and subfolders to the *3D Projects* folder in the AWBLA OneDrive
