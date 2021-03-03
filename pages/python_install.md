---
title: Install Guide: Python Geospatial Packages at ONS
description: A guide to installing geospatial Python packages on an ONS computer. 
---

# Install Guide: Python Geospatial Packages at ONS

The following instructions assume you are using an ONS Windows laptop, with Anaconda3 (64-bit) and Python 3.6.<br>
If not, please contact the ONS Service Desk to request installation.


There are five steps required to make sure that you can download and install the necessary packages: <br>
> 1.	Make sure Python is in your PATH.
> 2.	Make sure you have access to the ONS artifactory.
> 3.	Set up a .codarc and pip.ini file within your User profile.
> 4.	Download and install python wheels for the ‘shapely’, ‘rtree’, ‘pyproj’, ‘gdal’ and ‘fiona’ libraries.
> 5.	Install geopandas.

### 1. Make sure Python is in your PATH
The PATH variable tells your operating system the applications that are available from the command line. We need python to be available in the PATH to install the libraries required.
> * Search for the environment path by clicking on the start button and using the search box. <br>
> [image]
> * Select the “Edit environmental variables for your account” option in Control Panel.
> [image]
> * Check if you the PATH variable on your list of User variables as shown in the image below. If you do have PATH ommit the next step
> * If you dont have PATH select **'New'** to create this and name it PATH. 
> * If you have a PATH variable, but it doesn’t include Python, add the Python links using 'Edit'.
> * If you have to add Python to PATH, double check that your python installation is at 'C:\Python36\' . <br> If it is not, search for ‘python.exe’ on your windows explorer and add the path to the folder that contains ‘python.exe’ and to the ‘Scripts’ folder that should be in that directory. <br>As shown on the imaged above, the PATH in this example is `C:\Python36;C:\Python36\Scripts\`
> * To test whether this has worked, open Anaconda Prompt from the Windows start menu as shown below.<br> 
> [Anaconda prompt search image]
> * In the Anaconda Prompt, type 'python' and press return. You should open a python interpreter as below:
> [AP output image]
> * Close this and move onto the next part.
> 

### 2. Accessing the ONS Artifactory

Access artifactory at: http://art-p-01/  then login using your ONS username and password.<br> 
If you don’t have access, you’ll need to raise a service desk request.<br> 
Once you have access, you need to generate an encrypted password that you can use to access artifactory using PIP, python’s package installer.<br> 
> **To do this:** <br>
> *	Click on your username in the top right of the screen.
> *	Input your current password and click the unlock button.
> *	Generate an encrypted password.
> *	Copy the encrypted password to notepad for now, to use later. <br> 
> **Now, go back to the environment variables window we used to set PATH.**
> [Pip_index image]
> *	Add a new variable called PIP_INDEX_URL
> *	Set the variable value to: http://username: AP7JAPuaQ7cFZZ4gUNoDGjpLrEs@art-p-01/artifactory/api/pypi/yr-python/simple <br>
>       * username is your ONS username<br>
>       *	encrypted_password is the output from step 4 above.<br>
>   	

### 3. Set up the .condarc file
> * Under your user profile C:\Users\YourUsername, edit the. condarc file. (Create one if it doesn’t already exist by opening a Notepad and saving it as .condarc).<br> 
> * Copy and paste the following onto the .condarc file:<br>
>     `channel_alias: http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/conda-remote/`<br>
>     `channels: http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/conda-remote/`<br>
>     `default_channels: http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/conda-remote/`<br>
>     `ssl_verify: true`
  
> * Edit your credentials onto the above by replacing **USERNAME** with you windows ID and **ENCRYPTED PASSWORD** with the encrypted password from the Artifactory.<br>
> * Your `.condarc` file should look like the example below. Save and close it.
> [condac image]
> 

### 4. Set up a pip.ini file
> * Create a folder into C:\Users\YourUsername\AppData\Roaming called pip.
> * Create a file in the above directory called pip.ini (see Picture below)
> * Paste the below lines in it, replace ID with your user ID and PWD with the Hashtag password from Artifactory<br>
>     `[global]`<br>
>     `timeout = 60`<br>
>     `trusted-host = art-p-01`<br>
>     `index-url = http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/api/pypi/pypi.python.org/simple`<br>
>     `extra-index-url = http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/yr-python/`<br>
>     `http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/api/api/pypi/DAP-PyPist`<br>
>     `http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/PyPI-remote-cache`<br>
>     `http://USERNAME:ENCRYPTED PASSWORD@art-p-01/artifactory/list/PyPI-remote`<br>
> * If you have PIP_xxx variables set in your User Environment Variable, it would be best if you remove them

### 5. Download and install python wheels for the required libraries

We have to download these python libraries separately. This is because they rely on c libraries that are not downloaded if we use the normal python install approach, and cannot be built on ONS laptops.By downloading the wheels we are also downloading the c libraries that we don’t get otherwise.<br>
[Atefactory image]
In Artifactory, we’ll need to access the “Artifactory Repository Browser”. <br>
> * Click on the “Artifactory Repository Browser” icon (pages)
> * Click on the ‘Tree’ link.
> * Search for wheels.
> * Open the “Python_Wheels” drop down to reveal all the wheel files!<br>

**These Python wheels are Operating System and Python install specific. Most likely you will need to find the following wheels:**<br>
>     1. Rtree-0.8.3-cp36-cp36m-win_amd64.whl 
>     2. Fiona-1.7.13-cp36-cp36m-win_amd64.whl  
>     3. pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl 
>     4. Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl 
>     5. GDAL-2.2.4-cp36-cp36m-win_amd64.whl  
>       
These wheels have been built specifically for python 3.6 (cp36) and windows 64-bit (win_amd64), if your install or OS is different, download the appropriate wheels accordingly.
Once you have downloaded these wheels into your “Downloads” folder open the Anaconda Prompt again. <br>
> * Navigate to your downloads folder, for me this means giving the instruction: <br>

> `cd C:\Users\YourUsername\Downloads`, where cd is an instruction to Anaconda Prompt to ‘change directory’. <br>
> 
> * Now type and press return for: <br>
>   `pip install .\Rtree-0.8.3-cp36-cp36m-win_amd64.whl` <br>
>   `pip install .\Fiona-1.7.13-cp36-cp36m-win_amd64.whl` <br>
>   `pip install .\pyproj-1.9.5.1-cp36-cp36m-win_amd64.whl` <br>
>   `pip install .\Shapely-1.6.4.post1-cp36-cp36m-win_amd64.whl` <br>
>   `pip install .\GDAL-2.2.4-cp36-cp36m-win_amd64.whl` <br>

This will install these five libraries from the locally downloaded wheel files.

### 5. Install geopandas

Having installed Rtree, Fiona, shapely, gdal and pyproj, you should now be able to install geopandas. 
> * Type and press return for: <br>
>     `pip install geopandas` <br>
> This should download geopandas and the rest of its dependencies from artifactory. 
> You should now be ready to use geopandas. Check by opening python and trying:
>     `import geopandas as gpd`

##### Install mapclassify <br>

> * Download from this link: 
>      `https://pypi.org/project/mapclassify/#files` <br>
> * On Anaconda Prompt, map the path to your Downloads folder and run the following:
>      `pip install .\mapclassify-2.4.2-py3-none-any.whl` <br> 

You should hopefully have a fully functional Python for all the Geo_libraries.












