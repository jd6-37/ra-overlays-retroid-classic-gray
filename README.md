# RetroArch Overlays for Gray Bezel Retroid Classic Devices

**NOTE: The Retroid Classic has an OLED screen. Static overlays are said to sometimes cause burn-in on OLED screens. I don't know if these overlays will do that or how many hours it would take for it to happen. Do your own research and use at your own risk.**

This is a set of 1240 x 1080 overlays designed to match the gray bezels on the Retroid Classic devices with gray bezels (the "Classic 6" and "Retro" colorways).

This pack contains branded overlays for 23 different systems plus three unbranded "nologo" overlays for the three different aspect ratios (4:3, 3:2, and 16:9). They have rounded corners for the bottom of the screen area to match the rounded corners at the top of the device's screen.

![](https://raw.githubusercontent.com/jd6-37/ra-overlays-retroid-classic-gray/main/assets/photo.jpeg)

## How These Work 

Because the darkness of the gray color of the physical bezel will vary depending on the environment in which one is playing, each of these bezel configs reference 16 different PNG files. The PNG files are of the same design but the gray color of the bezel ranges from black (00 brightness - for use at night in dark rooms) to a very light gray (75 brightness - for use outdoors in bright daylight). By cycling through these shades, while rarely a perfect match, one can usually find a "good enough" match between the gray of the overlay bezel and the gray of the device's physical bezel.

To cycle through the shades of gray, one must utilize the `input_overlay_next` setting in retroarch.cfg. This setting will be null by default and can't be changed in the RetroArch GUI, to my knowledge. You must edit the master RetroArch file located at `/storage/emulated/0/Android/data/com.retroarch.aarch64/files/retoarch.cfg`. I recommend the app CX File Explorer, which will allow you to navigate to and directly edit this file. Find and change this config setting:

    input_overlay_next_btn = `103`

Note that this is the "_btn" setting. A value of "103" equates to the R1 button on the Classic, but you can set it to whatever you like.

## Video Scaling

These overlays are designed to be used with the screen pushed all the way to the top and non-integer scaled so they are full width.

Steps (repeat for every console/system):

1. Launch any game in RetroArch (or through ES-DE) from the console/system you want to edit. 
2. Enter the RetroArch Quick Menu, go back a screen, and into Settings > Video > Scaling.
3. Change the following settings:

.

    Integer Scaling: OFF
    Aspect Ratio: Custom
    Custom Aspect Ratio (X Position): 0
    Custom Aspect Ratio (Y Position): 0
    Custom Aspect Ratio (Width): 1240
    Custom Aspect Ratio (Height): 930
.

**The height value of `930` is for 4:3 aspect ratio. For 3:2 ratio (Eg. GBA), set it to `827`. For 16:9 (Eg. PSP), set it to `698`.*

4. With all settings changed, go back to Main Menu > Quick Menu > Overrides. Choose "Save Content Directory Overrides" (or Core or Game, if you prefer).

## Installing and Using the Overlays

**Downloading and installing:**

1. Download this repository either with `git clone` or via the Github website UI by clicking "Code > Download Zip".
2. Transfer the "Retroid-Classic-1240x1080" folder to your device. You can put this somewhere in the default Overlays directory or anywhere else you like. I prefer to put my custom overlays in my ROMs directory in a folder called "_OVERLAYS" for easy syncing with my other devices via SyncThing.

**Enabling the overlays** (repeat for every console/system):

1. Launch any game in RetroArch (or through ES-DE) from the console/system you want to edit. 
2. Enter the RetroArch Quick Menu, into On-Screen Overlay.
3. Set "Display Overlay" to `ON` and then choose "Overlay Preset". Navigate to the location where you put the "Retroid-Classic-1240x1080" folder. Go into that folder and select the config for your system (or the unbranded "nologo" option of the proper aspect ratio).
4. Change or confirm the following additional settings:

.

    Overlay Opacity: 1.0
    Hide Overlay When Controller is Connected: OFF
    Show Inputs on Overlay: OFF
    Auto-Scale Overlay: OFF
    (Landscape) Overlay Scale: 1.000
.

5. With all settings changed, go back to Quick Menu > Overrides. Choose "Save Content Directory Overrides" (or Core or Game, if you prefer).


**Using the overlays** 

When a game launches, the "00" brightness (aka black) version of the overlay will load. Choose a lighter shade of gray with the hotkey combo you chose (Eg. Select + R1). There are sixteen shades of gray, after which the cycle will start over again at "00"/black. In my usage, the first or second option works for playing in bed at night in a pitch dark room. During the daytime in a well-lit room, the fifth to seventh option usually matches the gray of the bezel the best. Outdoors in direct sunlight, the last couple lightest options are best. 

**Customizing the Overlays Order**

If you, for example, only play outdoors and would like to change the order and/or starting position of the shades of gray, simply edit the PNG filenames in these lines of the cfg file:

`overlay0_overlay = img/gray-3_2-plain-gba/00.png`

## Customizing the Overlays Design

I designed these to my preference with a very minimalistic monochrome gray system logo watermark. If that's not your preferred style, feel free to design your own with the included PSD template. 

Open the template in Photoshop or Photopea.com (a free, web-based Photoshop alternative). Double-click the icon of the "LOGO (Edit)" smart object layer to open it. Add whatever logos or effects you like and save the smart object. It will update the logo in all 16 frames in the main PSD.

When finished, click File > Export As > PNG. Change "Slices" setting to "All Slices". It will export a Zip file containing all sixteen frames, named 00.png through 75.png. Use these to replace the PNGs in the corresponding system folder in the "img" folder (or create a new folder and corresponding cfg file).


![](https://raw.githubusercontent.com/jd6-37/ra-overlays-retroid-classic-gray/main/assets/screenshot-psd.jpg)

## License

This project is released under the MIT License. You’re free to use, modify, and distribute it — just give credit and don’t hold me liable for anything!