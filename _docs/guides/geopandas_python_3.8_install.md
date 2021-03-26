---
title: Install Guide: Python 3.8 Geospatial Packages at ONS
description: A guide to installing geospatial Python packages on an ONS computer. 
---

# Install Guide: Python Geospatial Packages at ONS

The following instructions assume you are using an ONS Windows laptop, with Anaconda3 (64-bit) and Python 3.8.
If not, please contact the ONS Service Desk to request installation.

If you're not sure what version of python you have, Launch **Anaconda Prompt** from the windows search bar and type in `python`.

![Image showing the windows search bar for Anaconda Prompt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/anaconda%20prompt.PNG?raw=true)


IF you're using Python 3.6, you should follow the **'geopandas python 3.6 install'**


There are five steps required to make sure that you can download and install the necessary packages:
1.	Make sure you have access to the ONS artifactory.
2.	Set up a .codarc file.
3.  Set up a pip.ini file.
4.	Download and install python wheels for the ‘shapely’, ‘rtree’, ‘pyproj’, ‘gdal’ and ‘fiona’ libraries.
5.	Install geopandas.


### 1. Accessing the ONS Artifactory

Access artifactory at: http://art-p-01/  then login using your ONS username and password.

If you don’t have access, you’ll need to raise a service desk request.

Once you have access, you need to generate an encrypted password that you can use to access artifactory using PIP, python’s package installer.

**To do this:** 

*	Click on your username in the top right of the screen.
*	Input your current password and click the unlock button.
*	Generate an encrypted password.
*	Copy the encrypted password to notepad for now, to use later. 

**Search for the **Edit environment Variables** option in the windows search bar to open the menu.

![Image showing the Edit Environment Variables menu before being opened](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/edit_environment%20menu.PNG?raw=true)

*	Under the **User Variables** section, add a new variable called **PIP_INDEX_URL**

![Image showing the environment variables menu when adding Pip Index URL](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_index.PNG?raw=true)
	 
*	Set the variable value to:`http://UserName:EncryptedPassword@art-p-01/artifactory/api/pypi/yr-python/simple`
    * UserName is your ONS username
    *	EncryptedPassword is the output from step 1 above.
* Select OK and close.
   	

### 2. Set up the .condarc file
* [Open this link for the .condarc.txt file](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/.condarc.txt) then copy and paste its contents onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Make sure you do this for all channels
* When done, your. condarc file should look like the example below.
![Image showing the .condarc file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/condarc_file.png?raw=true)

* Save your .condarc file to **`C:\Users\YourUsername`** without the .txt extension and close it.

### 3. Set up a pip.ini file
* First, create a folder into **`C:\Users\YourUsername\AppData\Roaming`** and name it **`pip`**
* As in the previous step, [follow this link and copy the contents of the pip.ini.txt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/pip.ini.txt) file and paste them onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Again, make sure you have edited your credentials onto all five URLs on your .txt file
* When done, your .txt file should look like the example in the image below

![Image showing Pip Ini file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_ini.png?raw=true)

* Next, save your file as pip.ini into the pip folder you created without the .txt extension



### 4. Download and install python wheels for the required libraries

We have to download these python libraries separately. This is because they rely on c libraries that are not downloaded if we use the normal python install approach, and cannot be built on ONS laptops.By downloading the wheels we are also downloading the c libraries that we don’t get otherwise.

Follow this link **`https://www.lfd.uci.edu/~gohlke/pythonlibs/`** to download the wheels for installing the libraries we need.

**These Python wheels are Operating System and Python install specific. Scroll down and download each of the following:**
  1. Fiona-1.8.18-cp38-cp38-win_amd64.whl
  2. GDAL-3.2.2-cp38-cp38-win_amd64.whl
  3. pyproj-3.0.1-cp38-cp38-win_amd64.whl
  4. Rtree-0.9.7-cp38-cp38-win_amd64.whl
  5. Shapely-1.7.1-cp38-cp38-win_amd64.whl
  
 
       
These wheels have been built specifically for python 3.8 (cp38) and windows 64-bit (win_amd64), if your install or OS is different, download the appropriate wheels accordingly.
Once you have downloaded these wheels into your “Downloads” folder open the Anaconda Prompt again.

* Navigate to your downloads folder, for me this means giving the instruction:

 `cd C:\Users\YourUsername\Downloads`, where cd is an instruction to Anaconda Prompt to ‘change directory’.
 
* Now type and press return for each of the statements below in the order presented:

   `pip install .\Rtree-0.9.7-cp38-cp38-win_amd64.whl`
   
    `pip install .\GDAL-3.2.2-cp38-cp38-win_amd64.whl`
   
   `pip install .\Fiona-1.8.18-cp38-cp38-win_amd64.whl`
   
   `pip install .\pyproj-3.0.1-cp38-cp38-win_amd64.whl`
   
   `pip install .\Shapely-1.7.1-cp38-cp38-win_amd64.whl`
   
   
This will install these five libraries from the locally downloaded wheel files.

### 5. Install geopandas

Having installed Rtree, Fiona, shapely, gdal and pyproj, you should now be able to install geopandas. 
* Type and press return for:
    `pip install geopandas`
     
 This should download geopandas and the rest of its dependencies from artifactory. 
 You should now be ready to use geopandas. Check by opening python and trying:
     `import geopandas as gpd`

##### Install mapclassify

* Open the [Mapclassify documentation page from this link:](https://pypi.org/project/mapclassify/#files) and download this package by selecting:

`mapclassify-2.4.2-py3-none-any.whl (38.6 kB)` 
      
* On Anaconda Prompt, map the path to your Downloads folder and run the following:

`pip install .\mapclassify-2.4.2-py3-none-any.whl`
     

You should hopefully have a fully functional Python for all the geo-libraries.

