# Import OBS Settings to Windows 11 from Mac OS

## Prerequisites
This assumes you have already downloaded and installed the OBS application.

### Unzip the OBS settings file
This has all the scenes, profiles, assets, fonts, and other files needed.

### Install font files
- Go to \setup\Fonts\khula
- Double-click KhulaTitle-regular.otf to install it.
   
- Go to \setup\Fonts\baskervald-adf-std-font
- Double-click BaskervaldADFTitleStd.otf to install it.

( Old instructions. Install these fonts

- BaskervaldADFTitleStd.otf
- KhulaTitle-regular.otf
- Trajan Pro 3 Regular.otf
- TrajanPro3Light.ttf

NOTE: if you don't install the fonts, the title text in the lower 
two-thirds bar will not look right.

### Install Advanced Scene Switcher plugin
Download the latest version from the Internet and install it.

https://github.com/WarmUpTill/SceneSwitcher/releases

### Install Shaderfilter plugin
Make sure OBS is closed. Download the latest version from the 
Internet and install it.

https://github.com/exeldro/obs-shaderfilter/releases

### Install VB Cable driver
Install it from the setup/Audio/VBCABLE_Driver_Pack43 directory. 
The saved profiles expect to route audio (monitor ouptupt) to the 
VBCable virtual cable which you can input to other applications 
like Zoom.

Download the latest from here:

https://vb-audio.com/Cable/

### Install PTZ Controller app from PTZOptics
This is not necessary but is a convenient way to control a PTZ
camera from the desktop.

Install it from the setup/PTZControl/PTZOptics PTZ Controller Windows 1.4.1.zip file. 

Download the latest desktop controller from here:

https://docs.ptzoptics.com/apps/legacy-apps/

Download the OBS plugin from here:

https://github.com/PTZOptics/OBSPlugin

There are other plugins and desktop controllers you can get.

## 1 Copy unzipped file directory
Copy OBS directory to the root, C:\, so the directory is C:\OBS

Overwrite all files. If you don't want to lose anything, move or 
copy the existing C:\OBS directory somewhere else.

## 2 Edit the scene .json file
Edit the scene(s) .json file(s) under the \scenes\ directories.

### Replace directory paths
Search for "/Users/laurenanderson" and replace with "C:"
 
Make sure all /OBS paths are prefixed with C:/, for example:

```
C:/OBS/scenes/Sacrament-HD/images/BottomThirds-HD-BlueBar-880y-135h.png
```

If they are not prefixed with C:/ then search and replace the prefix 
directory path with C:/ so it looks like the example above and save
the file.
   
Note: on Mac OS and Windows, OBS uses slashes (/) for file paths, 
which is the convention on all Linux and Mac operating systems, instead 
of backslashes (\), which is the convention on Windows.
DO NOT USE BACKSLASHES IN FILE PATHS.

### Replace directory path for shader_file_name
In the scene .json file, search for shader_file_name and change the 
directory path to match where the shader filter is.
   
Search for "/Users/laurenanderson" and replace with "C:"
   
Mac OS
/Users/{username}/Library/Application Support/obs-studio/plugins/obs-shaderfilter.plugin/Contents/Resources/examples/drop_shadow.shader
   
Windows 11
C:/Program Files/obs-studio/data/obs-plugins/obs-shaderfilter/examples/drop_shadow.shader

## 3 Edit basic.ini file
Edit the basic.ini under the scenes/profile/(name) directory

Make sure all file paths are prefixed with C:\ and point to valid
directories, for example:

```
FilePath=C:\\Users\\myUser\\Videos\\OBS
RecFilePath=C:\\Users\\myUser\\Videos\\OBS
FFFilePath=C:\\Users\\myUser\\Videos\\OBS
```

## 4 Import Scene
If you already have the Scene in OBS, open OBS and delete the Scene 
that will be replaced. 

Import the Scene by going to Scene Collection > Import > Collection Path 
and finding the .json file for that scene under OBS/scenes.

## 5 Import Profile
If you already have the Profile in OBS, open OBS and delete the Profile 
that will be replaced.

Import the Profile by going to Profile > Import and finding the Profile
directory under OBS/scenes/(scene name)/profile.

NOTE: if you put the OBS directory somewhere other than the root, C:/, follow
the same instructions in steps 4 and 5 and replace the root path.



