---
title: Processing Scans
nav: Processing
topics:
---

-----------
1. [Images](#images)  
2. [Documents](#documents) 

{:#images}
### Images

1. If it hasn’t been done already, go to the folder for this scanning project (in your personal ‘Scans’ folder) and make two new folders: one named ‘access jpg’, and the other ‘lowres jpg’. 
2. Open Photoshop. Go to File > Automate > Batch. 

{% include figure.html img="automate_batch.jpg" alt="intro image here" caption="" width="50%" %}

3. In the Batch window, select the action ‘tif>jpg’. If this action doesn’t exist on your workstation yet, ask a supervisor how to create it. 
    - For the Source, make sure folder is selected. Click Choose and select the tif folder where your new scans are stored. 
    - For the Destination, make sure folder is selected. Click Choose and select the access jpg folder. 
    - Click OK.

    {% include figure.html img="batch_tif_jpg_2.jpg" alt="intro image here" caption="" width="100%" %}

4. After Photoshop has completed the action, make sure all the images have scanned to the correct folder. 
5. In the access jpg folder, open images in Photoshop and crop out the color bar. Balance images if needed. Save and close images when done with them. 
6. Once finished with the whole access jpg folder, go back to Photoshop to File > Automate > Batch. 
7. In the Batch window, select the action ‘access>jpg’. This may also be called ‘300dpijpg’. If this action doesn’t exist, ask a supervisor how to create it.
    - For the Source, make sure folder is selected. Click Choose and select the access jpg folder that contains all the adjusted images you just created. 
    - For the Destination, make sure folder is selected. Click Choose and select the lowres jpg folder. Make sure the file path reads the correct destination. 
    - Click OK.

{% include figure.html img="batch_lowres.jpg" alt="intro image here" caption="" width="100%" %}

8. After Photoshop has completed the action, make sure all the images have been saved to the correct folder.

--------------
{:#documents}
### Documents

1. Select the file(s) to be converted from your lowres jpg folder. 
2. Right-click selected items and select either ‘Convert to Adobe PDF’ or ‘Combine supported files in Acrobat’. This will open a window in Adobe Acrobat. 
    - If converting one file into a PDF, choose 'Convert to Adobe PDF'
    - If combining multiple files into one PDF (like a multi-page letter or document), choose 'Combine supported files in Acrobat'. A new window will pop up—click 'Combine'. 

{% include figure.html img="convert_to_pdf.jpg" alt="intro image here" caption="" width="50%" %}

3. When Adobe Acrobat opens, find 'Tools' in the top right corner of the screen and select Recognize Text > In this file. 

{% include figure.html img="recognize_text.jpg" alt="intro image here" caption="" width="100%" %}

4. Wait until Adobe Acrobat completes the command (the document will end up back at the first page). 
5. Save the document as a PDF following the naming rules established under File Naming. 
