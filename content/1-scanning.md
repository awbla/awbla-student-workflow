---
title: Scanning Procedures
nav: Scanning
---

-------------------

{% capture text %}**Before you scan**:
Make sure that hands are clean and dry when handling materials for scanning or any type of digitization work; all materials should be handled with care, and cotton gloves worn when instructed by a supervisor. These items cannot be replaced or easily repaired if destroyed or damaged.{% endcapture %}
{% include alert.html text=text color="danger" %}

1. [Why?](#why)
2. [File naming](#file)
3. [Scanning images](#images)
4. [Scanning documents](#documents)
5. [Lab equipment](#scanners)

-----------

{:#why}
## Why do we scan?

Digitizing materials by scanning them with a flatbed, large format, or feed scanner is sometimes the safest and most effective means of preserving the information in an item and allowing others to access it. Scanning items at a high resolution allows the item to be used in different ways without needing to make any manipulations to the actual item. This is why we aim for a minimum 600 dpi image; it provides a scalable image that can be used for large or small reprints while maintaining the original details of the item.

-----------

{:#file}
## File Naming

A standardized file naming system helps us know exactly where an item came from or where it belongs just by looking at the file name. Scanned files should be named using the following standardized naming rules:

**collectionabbreviation_box#_folder#-item#subitem**
{:.text-center}

Examples:
- Manuscript Group 190, Box 4, Folder 2, letter 1, multiple pages = **mg190_b4_f2-001p001, mg190_b4_f2-001p002, etc.**
- Photograph Group 3, box 1, photograph 3 = **pg3_b1-003**

If document is single page, use this format:

**CE_B1_F2_12345_Page_001**

If document is multiple page:

**CE_B1_F2_12345_Page_001**
**CE_B1_F2_12345_Page_002**
**CE_B1_F2_12345_Page_0033**

------------

{:#images}
## Scanning Images

Before beginning, go to your personal folder in the 'Scans' folder on the C: drive at your workstation. If a supervisor has not done so already, create a folder for the scanning project titled after the collection you'll be scanning (ex.: `MG 183`). Inside that folder, create another folder called 'tif'. This folder will be the destination for your initial scans.

- Turn on scanner at station. Open EpsonScan scanning software. 

- Place item to be scanned along the left side of the scanning bed (the glass plate), leaving a slight border between item and edge. 

- Position the Color Separation Guide so that the “saturated” bar is beside the item being scanned (along the bottom edge of the item is fine). Be sure to leave a ⅛-inch gap between the guide and the item.

- Close the scanner lid and press “Preview” in EpsonScan. Once the preview scan is finished, use the cursor to draw the selection window around the item and as much of the Color Separation Guide as is needed to color balance the item. There should not be a lot of space between the item and the edges of the selection window; see below:

    {% include figure.html img="screenshot-2.jpg" alt="intro image here" caption="" width="100%" %}
    
- Images should be scanned at **600 dpi** and should be at least **6,000 pixels** on the long edge. This measurement is located at the bottom left of the preview panel. The color filter should be set to ‘none’:

    {% include figure.html img="screenshot-3.jpg" alt="intro image here" caption="" width="50%" %}

- Once your settings are correct, press “Scan”. The “File Save Settings” window will pop up and you will need to:
    - Click “Other” and then “Browse to select the file you want your scanned images to be saved to. This should be the tif folder you already created.
    - Set up the File Name prefix. This should reflect the collection, box number, item number, and any other identifying characteristics like page numbers. See [File Naming](https://uidaholib.github.io/dds-student-workflow/content/1-scanning.html#file) for complete details. The Start Number should be at 001 if you’re starting a new project, or set to the next sequential number if you’re in the middle of a project. 
    - In the Image Format section, the file type should be set to TIFF (*.tif).

{% include figure.html img="screenshot-4.jpg" alt="intro image here" caption="" width="50%" %}

- Press “OK” and the scan will begin. 

-------------

{:#documents}
## Scanning Documents

- All documents should be scanned at **400 dpi** with the color filter set to “none”. 

- From here, follow the same directions for scanning images. Depending on the size of the document and the scanner used, the Color Separation Guide should be used following the same guidelines recommended when scanning images (Color Separation Guides will not be used on the feed scanner. Use the standard [File Naming](https://uidaholib.github.io/dds-student-workflow/content/1-intro.html#file) conventions for scanning items.

- Once a folder, box, or project is completely scanned, convert the files to JPEG using the [Processing guide](https://uidaholib.github.io/dds-student-workflow/content/2-lesson.html#documents). 

--------------

{%- assign scanners = site.data.equipment -%}

{:#equipment}
## Lab Equipment

An overview of the scanning equipment used in the CDIL. 

### Scanners:

<table class="table">
<tbody>
{% for s in scanners %}
<tr>
<td class="col-4"><img src="{{ s.image | prepend: '/images/' | relative_url }}" alt="image of {{ s.image }}" class="img-fluid"/></td>
<td class="col-8">{{ s.text }}</td>
</tr>
{% endfor %}
</tbody>
</table>
