## Prerequisites
This assumes you have already downloaded and installed the OBS application.

### Unzip the OBS settings file
This has all the scenes, profiles, assets, fonts, and other files needed.

### Install font files
Several custom font files are used for the titles and subtitles in the
"lower-third" bar at the bottom for speaker names, hymns, and performances.

1. Go to each of the directories listed below under **\setup\Fonts**.
2. Double-click the **.otf** or **.ttf** file to open it in the Windows Font Previewer.
3. Select **Install** to install it.

| Font                          | Directory                                | Use                                          |
| ----------------------------  | ---------------------------------------- | -------------------------------------------- |
| **BaskervaldADFTitleStd.otf** | \setup\Fonts\\**baskervald-adf-std-font** | name, hymn, song title                       |
| **KhulaTitle-regular.otf**    | \setup\Fonts\\**khula**                   | subtitle, song number and detail, performers |
| **Trajan Pro 3 Regular.otf**  | \setup\Fonts\\**Trajan Pro 3**            | welcome splash screen                        |
| **TrajanPro3Light.ttf**       | \setup\Fonts\\**TrajanPro3Light**         | welcome splash screen                        |

NOTE: if you don't install the fonts, the title text in the lower-third bar
will not look right.

### Install Advanced Scene Switcher plugin
Download the latest version from the Internet and install it.

https://github.com/WarmUpTill/SceneSwitcher/releases

### Install Shaderfilter plugin
Make sure OBS is closed. Download the latest version from the Internet and
install it.

https://github.com/exeldro/obs-shaderfilter/releases

### Install VB Cable driver
Install it from the setup/Audio/VBCABLE_Driver_Pack43 directory. The saved
OBS profiles expect to route audio (monitor ouptupt) to the VBCable virtual
cable which you can input to other applications like Zoom.

Download the latest from here:

https://vb-audio.com/Cable/

### Install PTZ Controller app from PTZOptics
This is not necessary but is a convenient way to control a PTZ camera from
the desktop.

Install it from the setup/PTZControl/PTZOptics PTZ Controller Windows 1.4.1.zip file.

Download the latest desktop controller from here:

https://docs.ptzoptics.com/apps/legacy-apps/

Download the OBS plugin from here:

https://github.com/PTZOptics/OBSPlugin

There are other plugins and desktop controllers you can use instead.

## 1 Copy unzipped file directory
Copy OBS directory to the root, C:\, so the directory is C:\OBS

Overwrite all files. If you don't want to lose anything, move or  copy the
existing C:\OBS directory somewhere else.

## 2 Edit the scene .json file
Edit the scene(s) .json file(s) under the \scenes\ directories.

### Replace directory paths
Search for "/Users/{username}" and replace with "C:"

For example, search for:

**/Users/LukeS**

and replace with:

**C:**

Make sure all **/OBS/...** paths are prefixed with **C:/**

For example:

`C:/OBS/scenes/Sacrament-HD/images/BottomThirds-HD-BlueBar-880y-135h.png`

If they are not prefixed with C:/ then search and replace the prefix directory
path with C:/ so it looks like the example above and save the file.

**Note:** on Mac OS and Windows, OBS uses slashes (/) for file paths, which is the
convention on all Linux and Mac operating systems, instead of backslashes (\\),
which is the convention on Windows operating systems. OBS for Windows recognizes
slashes (/) even though the OS uses the backslash (\\) convention. DO NOT USE
BACKSLASHES (\\) IN FILE PATHS IN THE OBS JSON SETTINGS FILES.

### Replace directory path for shader_file_name
In the scene .json file, search for **shader_file_name** and change the directory
path to match where the shader filter is on Windows.

#### Windows 11
```
C:/Program Files/obs-studio/data/obs-plugins/obs-shaderfilter/examples/drop_shadow.shader
```

## 3 Edit basic.ini file
Edit the **basic.ini** under the **scenes/profile/{scene name}** directory

Make sure all file paths are prefixed with **C:\\\\** and point to valid
directories, for example:

```
FilePath=C:\\Users\\myUser\\Videos\\OBS
RecFilePath=C:\\Users\\myUser\\Videos\\OBS
FFFilePath=C:\\Users\\myUser\\Videos\\OBS
```

**Note:** Unlike the JSON file, the file paths in basic.ini use double
backslashes (\\\\).

## 4 Import Scene Collection
If you already have the Scene Collection in OBS, open OBS and delete the Scene
Collection that will be replaced.

1. Go to Scene Collection > Import.
2. Under Collection Path, click on the 3 dots.
3. Find the .json file for that scene under the OBS/scenes directory.
4. Click on Open to add it to the import list.
5. Click on Import.

Switch to the imported Scene Collection to verify that all the scenes work. Go
to Scene Collection and select the imported scene collection. If there are
missing files, a message will display showing what is missing.

_Many of the settings exported from Mac OS don't import properly into Windows 11.
They will have to be fixed manually._

For example, the **Slide Show of Pictures** scene usually doesn't retain the path
of the directory for the pictures in the slide show. A message will display that
says "_Some files are missing since you last used OBS_" and show the Source with
the problem and will automatically go to the scene.

### Fix Missing Files
Switch to the imported scene. If it shows a missing file or directory, go to the
Source in the Scene and reselect the file or directory.

Many of the captions may not display because the path and name of the files that
have the caption text aren't retained. These usually aren't reported as missing
files. You will have to go through the scenes with captions. If the text doesn't
display, reselect the file.

### Check for Broken Sources
The video, audio, image, and media source options are different between Mac OS
and Windows. Invalid sources will be red.

Click on every scene and note the ones that have invalid sources.

#### Fix Broken Video Source
1. Go to a scene, Add Source, select Video Capture Device.
2. Copy the name of the old source.
3. Rename the old source with "-old" on the end.
4. Rename the new source with the copied name.
5. Check the old source for filters. If there are any, recreate them on the new source.
6. Copy the new source (Ctrl+C) to all the scenes that use it and paste it (Ctrl+V) as a reference.
7. Move it to the same place in the scene as the old source.
8. Delete the old source from the scene.

## 5 Import Profile
If you already have the Profile in OBS, open OBS and delete the Profile
that will be replaced.

Import the Profile by going to Profile > Import and finding the Profile
directory under OBS/scenes/(scene name)/profile.

NOTE: if you put the OBS directory somewhere other than the root, C:/, follow
the same instructions in steps 4 and 5 and replace the root path.
