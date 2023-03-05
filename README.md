# SSBM Skin Creation Tutorial (For Blender)

**Before we begin, I want to thank [xRunRiot](https://twitter.com/xRunRiot) for compiling a lot of the steps together and publishing them in the Animelee discord. This page is largely a reflection of that tutorial with a few modifications based on my experience and knowledge.** 

This tutorial focuses on the model-editing portion of creating a skin, ignoring things like character portraits or stock icons. It isn't fully comprehensive— there are gaps in our collective knowledge, so this tutorial may always be a work in progress. With that in mind, let us begin.

---

### Software and Resources
Below are programs and resources that are essential to creating a skin for Melee.
#### Necessary Software
* [**Blender**](https://www.blender.org/download/lts/3-3/)[^1] - An open source, free-to-use 3D modelling program, and the program used to manipulate and change the desired 3D models.
  * [**Blender Source Tools**](http://steamreview.org/BlenderSourceTools/) - A Blender addon necessary for importing and exporting `.smd` files.
  * Installing Blender addons is a simple process. [Click here](https://docs.blender.org/manual/en/latest/editors/preferences/addons.html#installing-add-ons) to read on how to do it, or look up [a Youtube video](https://youtu.be/vYh1qh9y1MI), there's plenty available.
* [**HSDRaw**](https://github.com/Ploaj/HSDLib/releases) - Created by Ploaj, HSDRaw is the second essential workspace for skin creation, allowing users to manipulate `.dat` files in many ways: importing and exporting models, changing textures, even change in-game characteristics.
  *  For this tutorial, it will primarily be used to export character armatures/skeletons, and import custom models to work in-game.
* [**DAT Texture Wizard**](https://github.com/DRGN-DRC/DAT-Texture-Wizard/releases/tag/v6.1.4) - Created by DRGN, DTW is used for manipulating Melee ISOs and the `.dat` files within. 
  *  For this tutorial it will primarily be used to import and export character `.dat` files, and change textures.
* An Image Editor - For editing and creating textures, it can be any that you're comfortable with. Below are a few good (free) options.
  *  [**GIMP**](https://www.gimp.org/downloads/) - An open-source Photoshop clone that's been around for a long time. Has all the necessary tools to create textures for use in the tutorial.
  *  [**Photopea**](https://www.photopea.com/) - A browser based image editor with a similar feature set and layout to Photoshop. Plus it's within your browser, so if you don't want to download more software, it's a decent pick
  * [**Paint.NET**](https://www.getpaint.net/download.html) - Less robust features than the previous two options, but it's relatively simple to use for simpler texture edits.

####  Additional Resources
* [**Costume Validator**](https://ssbmtextures.com/other-mod-types/costume-validator-by-ploaj/) - Makes skins Slippi compatible, this program solves the `DESYNC DETECTED` error created by inaccurate skeletons.
* [**SSBMTextures**](https://ssbmtextures.com/) - A hub for uploading and downloading a range of visual modifications for Melee, including texture swaps and model replacements.
* [**Drippi.gg**](https://drippi.gg) - A place to host melee skins and download others; robust social media support and in-browser 3D model viewer.

There will be no distribution of copyrighted material in this tutorial (i.e. `.dat` files or game ISOs), so you'll need to acquire those for yourself.


---

### Step 1 – Exporting Model (and Skeleton) from Melee to Blender
In this tutorial, I will be making an _Animelee_ style skin, but the steps are largely the same for both types of skins.
#### Acquiring the Character's `.dat` File and Textures
1. Open DTW (_DAT Texture Wizard_) and import your Melee ISO by going `File > Open Disc (ISO/GCM)` from the menu at the top of the window
2. Click on the _Characters_ shortcut at the top of the window
3. Open the folder of the character you want to make edits to
4. Single-click the file of the character costume color you want to make edits to
5. Click the export button on the right side of the window and save the `.dat` file somewhere easy to find.
6. Double-click the file of the character costume color you want to make edits to.
7. Right click any of the textures and select `Export All` and save the textures somewhere easy to find[^2].

#### Viewing the `.dat` with HSDRaw
1. Open HSD and import the .dat character file you exported by going `File > Open` from the menu at the top of the window
2. Double-click the `JOBJ` file in the Nodes window on the left side
3. The chacter will appear in a T-pose to the right side of your screen, in the Preview window
   *  Click and drag with the right mouse button to rotate 
   *  Click and drag with the left mouse button to pan
   *  Scroll wheel to zoom

#### Exporting the `.smd` and `.dae` Model Files
1. In HSD while viewing the model, go to File (Not the one in the top left, the one next to animation) and select "Export Model to File"
2. Save the model with both `.dae` and `.smd` extensions as two separate files
<details> <summary> Click Here for a Video Demonstration</summary
<div align="center"><video src="https://user-images.githubusercontent.com/127040488/222988721-ba468a01-eb54-4806-ae16-c1fc4ef20abd.mp4"/></div></details>

---
[^1]: I've linked Blender's LTS (Long Term Support) branch for its stability, but feel free to use the [latest available version](https://www.blender.org/download/).
[^2]: It's a good practice to save the .dat and texture files together in their own labelled folder, and it's recommended to keep an unedited copy of your .dat and texture folder as a backup


