---
title: Install Guide: Python Geospatial Packages at ONS
description: A guide to installing geospatial Python packages on an ONS computer. 
---

# Install Guide: Python Geospatial Packages at ONS

The following instructions assume you are using an ONS Windows laptop, with Anaconda3 (64-bit) and Python 3.6 or 3.8.
If not, please contact the ONS Service Desk to request installation.


## Check Your Python Version

If you're not sure what version of Python you have, launch **Anaconda Prompt** from the windows search bar and type in `Python`.

![Image showing the windows search bar for Anaconda Prompt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/anaconda%20prompt.PNG?raw=true)

### Python 3.6 
If you're using Python 3.6, you should get the following output:

![Image showing the output from Anaconda Prompt for 3.6](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/anaconda_prompt_output.PNG?raw=true)

Follow the [instructions for installation on Python 3.6](https://onsgeo.github.io/geospatial-training/docs/guides/python_install#installation-guide-for-python-36).


### Python 3.8

If you're using Python 3.8 you should get the following output:

![Image showing the output from Anaconda Prompt for 3.8](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/python_3_8.png?raw=true)

Follow the [instructions for installation on Python 3.8](https://onsgeo.github.io/geospatial-training/docs/guides/python_install#installation-guide-for-python-38).



## Installation Guide for Python 3.6

There are six steps required to make sure that you can download and install the necessary packages:
1.	Make sure you have access to the ONS artifactory.
2.	Set up a .codarc file.
3.  Set up a pip.ini file.
4.	Download and install Python wheels for the ‘shapely’, ‘rtree’, ‘pyproj’, ‘gdal’ and ‘fiona’ libraries.
5.	Install Geopandas.
6.  Install Mapclassify.


### 1. Accessing the ONS Artifactory

Access artifactory at: http://art-p-01/  then login using your ONS username and password.

If you don’t have access, you’ll need to raise a service desk request.

Once you have access, you need to generate an encrypted password that you can use to access artifactory using PIP, Python’s package installer.

**To do this:** 

*	Click on your username in the top right of the screen.
*	Input your current password and click the unlock button.
*	Generate an encrypted password.
*	Copy the encrypted password to notepad for now, to use later. 

Search for the **Edit environment Variables** option in the windows search bar to open the menu.

![Image showing the Edit Environment Variables menu before being opened](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/edit_environment%20menu.PNG?raw=true)

*	Under the **User Variables** section, add a new variable called **PIP_INDEX_URL**

![Image showing the environment variables menu when adding Pip Index URL](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_index.PNG?raw=true)

*	Set the variable value to: `http://UserName:EncryptedPassword@art-p-01/artifactory/api/pypi/yr-python/simple`
    * UserName is your ONS username
    *	EncryptedPassword is the output from step 1 above.
* Select OK and close.
   	

### 2. Set up the .condarc file
* [Open this link for the .condarc.txt file](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/.condarc.txt) then copy and paste its contents onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Make sure you do this for all channels
* When done, your. condarc file should look like the example below.
![Image showing the .condarc file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/condarc_file.png?raw=true)

* Save your .condarc file to `C:\Users\YourUsername` without the .txt extension and close it.

### 3. Set up a pip.ini file
* First, create a folder into `C:\Users\YourUsername\AppData\Roaming` and name it `pip`
* As in the previous step, [follow this link and copy the contents of the pip.ini.txt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/pip.ini.txt) file and paste them onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Again, make sure you have edited your credentials onto all five URLs on your .txt file
* When done, your .txt file should look like the example in the image below

![Image showing Pip Ini file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_ini.png?raw=true)

* Next, save your file as pip.ini into the pip folder you created without the .txt extension



### 4. Download and install Python wheels for the required libraries

We have to download these Python libraries separately. This is because they rely on C libraries that are not downloaded if we use the normal Python install approach, and cannot be built on ONS laptops.By downloading the wheels we are also downloading the C libraries that we don’t get otherwise.

![Image showing the Artefactory](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/artefactory.PNG?raw=true)


In Artifactory, we’ll need to access the “Artifactory Repository Browser”.

	1. Click on the “Artifactory Repository Browser” icon (pages)
	2. Click on the ‘Tree’ link.
	3. Search for wheels.
	4. Open the “Python_Wheels” drop down to reveal all the wheel files!

**These Python wheels are Operating System and Python install specific.** Download the following wheels:
  1. Fiona-1.7.13-cp36-cp36m-win_amd64.whl
  2. GDAL-2.2.4-cp36-cp36m-win_amd64.whl
  3. pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl
  4. Rtree-0.8.3-cp36-cp36m-win_amd64.whl
  5. Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl 
  
 
       
These wheels have been built specifically for Python 3.6 (cp36) and windows 64-bit (win_amd64), if your install or OS is different, download the appropriate wheels accordingly.
Once you have downloaded these wheels into your “Downloads” folder open the Anaconda Prompt again.

* Navigate to your downloads folder, for me this means giving the instruction:

 `cd C:\Users\YourUsername\Downloads`, where cd is an instruction to Anaconda Prompt to ‘change directory’.
 
* Now type and press return for each of the statements below in the order presented:

   `pip install .\Rtree-0.8.3-cp36-cp36m-win_amd64.whl`
   
    `pip install .\GDAL-2.2.4-cp36-cp36m-win_amd64.whl`
   
   `pip install .\Fiona-1.7.13-cp36-cp36m-win_amd64.whl`
   
   `pip install .\pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl`
   
   `pip install .\Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl`
   
   
This will install these five libraries from the locally downloaded wheel files.

### 5. Install Geopandas

Having installed Rtree, Fiona, shapely, gdal and pyproj, you should now be able to install Geopandas. 
* Type and press return for:
    `pip install geopandas`
     
 This should download Geopandas and the rest of its dependencies from artifactory. 
 You should now be ready to use Geopandas. Check by opening Python and trying:
     `import geopandas as gpd`

### 6. Install Mapclassify

* Open the [Mapclassify documentation page](https://pypi.org/project/mapclassify/#files) and download `mapclassify-2.4.2-py3-none-any.whl (38.6 kB)` 
      
* On Anaconda Prompt, map the path to your Downloads folder and run `pip install .\mapclassify-2.4.2-py3-none-any.whl`
     

You should hopefully have a fully functional Python for all the geo-libraries.


## Installation Guide for Python 3.8

There are six steps required to make sure that you can download and install the necessary packages:
1.	Make sure you have access to the ONS artifactory.
2.	Set up a .codarc file.
3.  Set up a pip.ini file.
4.	Download and install Python wheels for the ‘shapely’, ‘rtree’, ‘pyproj’, ‘gdal’ and ‘fiona’ libraries.
5.	Install Geopandas.
6.  Install Mapclassify


### 1. Accessing the ONS Artifactory

Access artifactory at: http://art-p-01/  then login using your ONS username and password.

If you don’t have access, you’ll need to raise a service desk request.

Once you have access, you need to generate an encrypted password that you can use to access artifactory using PIP, Python’s package installer.

**To do this:** 

*	Click on your username in the top right of the screen.
*	Input your current password and click the unlock button.
*	Generate an encrypted password.
*	Copy the encrypted password to notepad for now, to use later. 

Search for the **Edit environment Variables** option in the windows search bar to open the menu.

![Image showing the Edit Environment Variables menu before being opened](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/edit_environment%20menu.PNG?raw=true)

*	Under the **User Variables** section, add a new variable called **PIP_INDEX_URL**

![Image showing the environment variables menu when adding Pip Index URL](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_index.PNG?raw=true)
	 
*	Set the variable value to: `http://UserName:EncryptedPassword@art-p-01/artifactory/api/pypi/yr-python/simple`
    * UserName is your ONS username
    *	EncryptedPassword is the output from step 1 above.
* Select OK and close.
   	

### 2. Set up the .condarc file
* [Open this link for the .condarc.txt file](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/.condarc.txt) then copy and paste its contents onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Make sure you do this for all channels
* When done, your. condarc file should look like the example below.
![Image showing the .condarc file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/condarc_file.png?raw=true)

* Save your .condarc file to `C:\Users\YourUsername` without the .txt extension and close it.

### 3. Set up a pip.ini file
* First, create a folder into `C:\Users\YourUsername\AppData\Roaming` and name it `pip`
* As in the previous step, [follow this link and copy the contents of the pip.ini.txt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/pip.ini.txt) file and paste them onto a new .txt file.
* Edit your credentials onto your .txt file by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* Again, make sure you have edited your credentials onto all five URLs on your .txt file
* When done, your .txt file should look like the example in the image below

![Image showing Pip Ini file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_ini.png?raw=true)

* Next, save your file as pip.ini into the pip folder you created without the .txt extension



### 4. Download and install Python wheels for the required libraries

We have to download these Python libraries separately. This is because they rely on C libraries that are not downloaded if we use the normal Python install approach, and cannot be built on ONS laptops.By downloading the wheels we are also downloading the C libraries that we don’t get otherwise.

![Image showing the Artefactory](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/artefactory.PNG?raw=true)


In Artifactory, we’ll need to access the “Artifactory Repository Browser”.

	1. Click on the “Artifactory Repository Browser” icon (pages)
	2. Click on the ‘Tree’ link.
	3. Search for wheels.
	4. Open the “Python_Wheels” drop down to reveal all the wheel files!

**These Python wheels are Operating System and Python install specific.** Download the following wheels:
  1. Fiona-1.8.18-cp38-cp38-win_amd64.whl
  2. GDAL-3.2.2-cp38-cp38-win_amd64.whl
  3. pyproj-3.0.1-cp38-cp38-win_amd64.whl
  4. Rtree-0.9.7-cp38-cp38-win_amd64.whl
  5. Shapely-1.7.1-cp38-cp38-win_amd64.whl
  

These wheels have been built specifically for Python 3.8 (cp38) and windows 64-bit (win_amd64), if your install or OS is different, download the appropriate wheels accordingly.
If you cannot find one of these Python wheels on the drop down from the artifactory, copy it from the list above and paste it onto the tree search bar on the artifactory. Once you have downloaded these wheels into your “Downloads” folder open the Anaconda Prompt again.

* Navigate to your downloads folder, for me this means giving the instruction:

 `cd C:\Users\YourUsername\Downloads`, where cd is an instruction to Anaconda Prompt to ‘change directory’.
 
* Now type and press return for each of the statements below in the order presented:

   `pip install .\Rtree-0.9.7-cp38-cp38-win_amd64.whl`
   
    `pip install .\GDAL-3.2.2-cp38-cp38-win_amd64.whl`
   
   `pip install .\Fiona-1.8.18-cp38-cp38-win_amd64.whl`
   
   `pip install .\pyproj-3.0.1-cp38-cp38-win_amd64.whl`
   
   `pip install .\Shapely-1.7.1-cp38-cp38-win_amd64.whl`
   
   
This will install these five libraries from the locally downloaded wheel files.

### 5. Install Geopandas

Having installed Rtree, Fiona, shapely, gdal and pyproj, you should now be able to install Geopandas. 
* Type and press return for:
    `pip install geopandas`
     
 This should download Geopandas and the rest of its dependencies from artifactory. 
 You should now be ready to use Geopandas. Check by opening Python and trying:
     `import geopandas as gpd`

### 6. Install Mapclassify

* Open the [Mapclassify documentation page](https://pypi.org/project/mapclassify/#files) and download this package `mapclassify-2.4.2-py3-none-any.whl (38.6 kB)` 
      
* On Anaconda Prompt, map the path to your Downloads folder and run `pip install .\mapclassify-2.4.2-py3-none-any.whl`
     

You should hopefully have a fully functional Python for all the geo-libraries.
