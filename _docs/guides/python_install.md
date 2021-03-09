---
title: Install Guide: Python Geospatial Packages at ONS
description: A guide to installing geospatial Python packages on an ONS computer. 
---

# Install Guide: Python Geospatial Packages at ONS

The following instructions assume you are using an ONS Windows laptop, with Anaconda3 (64-bit) and Python 3.6.
If not, please contact the ONS Service Desk to request installation.


There are five steps required to make sure that you can download and install the necessary packages:
1.	Make sure Python is in your PATH.
2.	Make sure you have access to the ONS artifactory.
3.	Set up a .codarc and pip.ini file within your User profile.
4.	Download and install python wheels for the ‘shapely’, ‘rtree’, ‘pyproj’, ‘gdal’ and ‘fiona’ libraries.
5.	Install geopandas.

### 1. Make sure Python is in your PATH
The PATH variable tells your operating system the applications that are available from the command line. We need python to be available in the PATH to install the libraries required.
* Search for the environment path by clicking on the start button and using the search box.
![Windows search bar image showing Edit Environment menu](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/edit_environment.PNG?raw=true)
* Select the “Edit environmental variables for your account” option in Control Panel.
[image]
* Check if you the PATH variable on your list of User variables as shown in the image below. If you do have PATH ommit the next step
* If you dont have PATH select **'New'** to create this and name it PATH. 
* If you have a PATH variable, but it doesn’t include Python, add the Python links using 'Edit'.
* If you have to add Python to PATH, double check that your python installation is at 'C:\Python36\' . 
* If it is not, search for ‘python.exe’ on your windows explorer and add the path to the folder that contains ‘python.exe’ and to the ‘Scripts’ folder that should be in that directory. 
* As shown on the imaged above, the PATH in this example is `C:\Python36;C:\Python36\Scripts\`
* To test whether this has worked, open Anaconda Prompt from the Windows start menu as shown below.
 
![Image showing the windows search bar for Anaconda Prompt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/anaconda%20prompt.PNG?raw=true)
* In the Anaconda Prompt, type 'python' and press return. You should open a python interpreter as below:
![Image showing the output from Anaconda Prompt](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/anaconda_prompt_output.PNG?raw=true)
* Close this and move onto the next part.
 

### 2. Accessing the ONS Artifactory

Access artifactory at: http://art-p-01/  then login using your ONS username and password.

If you don’t have access, you’ll need to raise a service desk request.

Once you have access, you need to generate an encrypted password that you can use to access artifactory using PIP, python’s package installer.

**To do this:** 

*	Click on your username in the top right of the screen.
*	Input your current password and click the unlock button.
*	Generate an encrypted password.
*	Copy the encrypted password to notepad for now, to use later. 

**Now, go back to the environment variables window we used to set PATH.**
 ![Image showing the environment variables menu when adding Pip Index URL](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_index.PNG?raw=true)
*	Add a new variable called PIP_INDEX_URL
*	Set the variable value to: http://username: AP7JAPuaQ7cFZZ4gUNoDGjpLrEs@art-p-01/artifactory/api/pypi/yr-python/simple
    * username is your ONS username
    *	encrypted_password is the output from step 4 above.
   	

### 3. Set up the .condarc file
* Open the .condarc.txt file from the repository and edit your credentials onto this by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* When done, your. condarc file should look like the example below.
![Image showing the .condarc file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/condarc_file.png?raw=true)

* Save it to C:\Users\YourUsername without the .txt extension and close it.

### 4. Set up a pip.ini file
* First, create a folder into C:\Users\YourUsername\AppData\Roaming and name it pip
* As in the previous step, open the pip.ini.txt file from the repository and edit your credentials onto this by replacing Username with your windows ID and EncryptedPassword with the encrypted password from the artifactory.
* When done, your pip.ini.txt file should look like the example in the image below
* Make sure to save you pip.ini file without the .txt extension
![Image showing Pip Ini file contents](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/pip_ini.png?raw=true)


### 5. Download and install python wheels for the required libraries

We have to download these python libraries separately. This is because they rely on c libraries that are not downloaded if we use the normal python install approach, and cannot be built on ONS laptops.By downloading the wheels we are also downloading the c libraries that we don’t get otherwise.

![Image showing the Artefactory](https://github.com/ONSgeo/geospatial-training/blob/master/_docs/guides/img/artefactory.PNG?raw=true)


In Artifactory, we’ll need to access the “Artifactory Repository Browser”.

 * Click on the “Artifactory Repository Browser” icon (pages)
 * Click on the ‘Tree’ link.
 * Search for wheels.
 * Open the “Python_Wheels” drop down to reveal all the wheel files!

**These Python wheels are Operating System and Python install specific. Most likely you will need to find the following wheels:**
  1. Rtree-0.8.3-cp36-cp36m-win_amd64.whl 
  2. Fiona-1.7.13-cp36-cp36m-win_amd64.whl  
  3. pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl 
  4. Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl 
  5. GDAL-2.2.4-cp36-cp36m-win_amd64.whl  
       
These wheels have been built specifically for python 3.6 (cp36) and windows 64-bit (win_amd64), if your install or OS is different, download the appropriate wheels accordingly.
Once you have downloaded these wheels into your “Downloads” folder open the Anaconda Prompt again.

* Navigate to your downloads folder, for me this means giving the instruction:

 `cd C:\Users\YourUsername\Downloads`, where cd is an instruction to Anaconda Prompt to ‘change directory’.
 
* Now type and press return for:

   `pip install .\Rtree-0.8.3-cp36-cp36m-win_amd64.whl`
   
   `pip install .\Fiona-1.7.13-cp36-cp36m-win_amd64.whl`
   
   `pip install .\pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl`
   
   `pip install .\Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl`
   
   `pip install .\GDAL-2.2.4-cp36-cp36m-win_amd64.whl`
   

This will install these five libraries from the locally downloaded wheel files.

### 5. Install geopandas

Having installed Rtree, Fiona, shapely, gdal and pyproj, you should now be able to install geopandas. 
* Type and press return for:
    `pip install geopandas`
     
 This should download geopandas and the rest of its dependencies from artifactory. 
 You should now be ready to use geopandas. Check by opening python and trying:
     `import geopandas as gpd`

##### Install mapclassify

* Download from this link: 
      `https://pypi.org/project/mapclassify/#files` 
      
* On Anaconda Prompt, map the path to your Downloads folder and run the following:
      `pip install .\mapclassify-2.4.2-py3-none-any.whl`
     

You should hopefully have a fully functional Python for all the Geo_libraries.












