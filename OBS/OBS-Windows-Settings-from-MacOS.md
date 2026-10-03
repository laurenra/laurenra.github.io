# Import OBS Settings to Windows 11 from Mac OS

## Prerequisites
[x] Install font files

Go to \setup\Fonts\khula
Double-click KhulaTitle-regular.otf to install it.
   
Go to \setup\Fonts\baskervald-adf-std-font
Double-click BaskervaldADFTitleStd.otf to install it. 

[x] Install OBS
[x] Install Advanced Scene Switcher plugin

Download the latest version from the Internet and install it.

https://github.com/WarmUpTill/SceneSwitcher/releases.

## Set up OBS for Windows from Zip file
1. Make sure the OBS application is installed.

2. Unzip

3. Copy OBS directory to the root, C:\, so the directory is C:\OBS

   Overwrite all files. If you don't want to lose anything, move or 
   copy the existing C:\OBS directory somewhere else.

4. Install font files

   Go to \setup\Fonts\khula
   Double-click KhulaTitle-regular.otf to install it.
   
   Go to \setup\Fonts\baskervald-adf-std-font
   Double-click BaskervaldADFTitleStd.otf to install it. 

5. Install Advanced Scene Switcher plugin

   Go to \plugins\Windows and double-click 
   advanced-scene-switcher-1.31.0-windows-x64-Installer.exe to install it 
   or download the latest version from the Internet and install it.

6. Install Shaderfilter plugin

   Make sure OBS is closed.
   Go to \plugins\Windows and double-click 
   obs-shaderfilter-2.5.1-windows-installer.exe to install it 
   or download the latest version from the Internet and install it.


7. Edit the scene(s) .json file(s) under the \scenes\ directories.

   Search for "/Users/laurenanderson" and replace with "C:"
 
   Make sure all /OBS paths are prefixed with C:/, for example:

   C:/OBS/scenes/Sacrament-HD/images/BottomThirds-HD-BlueBar-880y-135h.png

   If they are not prefixed with C:/ then search and replace the prefix 
   directory path with C:/ so it looks like the example above and save
   the file.
   
   Note: on Mac OS and Windows, OBS uses slashes (/) for file paths, 
   which is the convention on all Linux and Mac operating systems, instead 
   of backslashes (\), which is the convention on Windows.
   DO NOT USE BACKSLASHES IN FILE PATHS.

   
8. In the scene .json file, search for shader_file_name and change the 
   directory path to match where the shader filter is.
   
   Search for "/Users/laurenanderson" and replace with "C:"
   
   Mac OS
   /Users/{username}/Library/Application Support/obs-studio/plugins/obs-shaderfilter.plugin/Contents/Resources/examples/drop_shadow.shader
   
   Windows 11
   C:/Program Files/obs-studio/data/obs-plugins/obs-shaderfilter/examples/drop_shadow.shader


9. Edit the basic.ini file under the scenes/profile/(name) directory

   Make sure all file paths are prefixed with C:\ and point to valid
   directories, for example:

   FilePath=C:\\Users\\myUser\\Videos\\OBS
   RecFilePath=C:\\Users\\myUser\\Videos\\OBS
   FFFilePath=C:\\Users\\myUser\\Videos\\OBS

   If you make changes, save the file.


10. If you already have the Profile(s) and Scene(s) in OBS, 
   open OBS and delete the Profile(s) and Scene(s) you will
   replace from the Zip file. 

11. Open OBS and import the Profile(s) and Scene(s).

   Import the Profile(s) by going to Profile > Import and finding the Profile
   directory under OBS/scenes/(scene name)/profile.

   Import the Scene(s) by going to Scene Collection > Import > Collection Path 
   and finding the .json file for that scene under OBS/scenes.

NOTE: if you put the OBS directory somewhere other than the root, C:/, follow
the same instructions in steps 3 and 4 and replace the root path.

12. If there is an assets/Fonts directory, install all these fonts:
   
   BaskervaldADFTitleStd.otf
   KhulaTitle-regular.otf
   Trajan Pro 3 Regular.otf
   TrajanPro3Light.ttf

   NOTE: if you don't install the fonts, the title text in the lower 
   two-thirds bar will not look right.

13. If you haven't already installed the VB Cable driver, install it from
   the setup/Audio/VBCABLE_Driver_Pack43 directory. The saved profiles expect 
   to route audio to the VBCable which you can input to other applications
   like Zoom.

14. If you haven't already installed the PTZ Controller app, install it from 
   the setup/PTZControl/PTZOptics PTZ Controller Windows 1.4.1.zip file. 



