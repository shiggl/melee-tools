# SSBM Skin Creation Tutorial (For Blender)

**Before we begin, I want to thank [xRunRiot](https://twitter.com/xRunRiot) for compiling a lot of the steps together and publishing them in the Animelee discord. This page is largely a reflection of that tutorial with a few modifications based on my experience and knowledge.** 

This tutorial focuses on the model-editing portion of creating a skin, ignoring things like character portraits or stock icons. It isn't fully comprehensive— there are gaps in our collective knowledge, so this tutorial may always be a work in progress. With that in mind, let us begin.

---

### Software and Resources
Below are programs and resources that are essential to creating a skin for Melee.
#### Necessary Software
* [**Blender**](https://www.blender.org/download/lts/3-3/)[^1] - An open source, free-to-use 3D modelling program, and the program used to manipulate and change the desired 3D models.
  * [**Blender Source Tools**](http://steamreview.org/BlenderSourceTools/) - A Blender add-on necessary for importing and exporting `.smd` files.
  * **Material Utilities** - A built-in Blender add-on available in the _Preferences_ menu that is helpful in dealing with materials in Blender. Search for it in the _Add-ons_ tab and enable it to use it.
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

### Step 1 – Exporting Model (and Skeleton) from Melee w/ HSDRaw
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

### Step 2 – Importing and Preparing the Model in Blender
**Be sure to have installed the _Blender Source Tools_ addon [mentioned above](https://github.com/shiggl/melee-tools#necessary-software).** It's necessary to get a working skeleton.
#### Importing the `.dae` and `.smd` files
Put plainly, we'll be using the `.dae` for the meshes/textures, and the `.smd` for the skeleton/vertex weights[^3].
##### Importing and preparing the `.dae` file for use
1. `File > Import > Collada (.dae)` then navigate to the `.dae` file you just created with HSDRaw
    * In the Blender viewport, you can hold the `Z` key and mouse over _Material Preview_ to see the assigned material
      *  Some of the textures may look wrong or mirrored in strange ways. **Don't fret, they're _fine_.** A lot of Melee's textures are mirrored and scaled in-game to look correct. This can be configured in HSDRaw's texture settings.
2.  Select the _Armature_ created by the `.dae` file and delete it. We won't be needing it for this tutorial.
3.  Create a collection in the scene browser and name it what ever you'd like. I named mine _dae_ for this project. Drag all the newly created objects into that collection
<details> <summary> Click Here for a Video Demonstration</summary>
<div align="center"><video src="https://user-images.githubusercontent.com/127040488/222990531-9a1665a9-f895-4040-9c4c-9b9d405a1d30.mp4"/></div></details>

##### Importing and preparing the `.smd` file for use
1. `File > Import > Source Engine (.smd, .vta, .dmx, .qc)` then navigate to the `.smd` file you just created with HSDRaw
2. Blender will create a collection automatically. It contains a single object that consists of all the character's models and textures together. This will be used to transfer vertex weights later in the tutorial.
    * If you have the _Material Utilities_ add-on installed, in the viewport, select the object and hit `Shift+Q` to bring up the add-on menu and clear out all active materials. This step isn't strictly necessary, but it helps lessen confusion between the separated `.dae` meshes and the `.smd` base.
3. In the scene browser, click the dropdown on _char_skeleton_, then again next to the green man. 
4. Go into _Edit Mode_ 
    * (`Tab` key in the viewport to easily switch between _Edit Mode_ and _Object Mode_)
6. Select all the non-"JOBJ_#" bones (their names should be something like _Joint_0_Object_0_) in the browser to the side and delete them.
    * These are the junk bones and will create errors if they're left in the skeleton. This step is essential to having the mod work in game.

<details> <summary> Click Here for a Video Demonstration</summary>
<div align="center"><video src="https://user-images.githubusercontent.com/127040488/227718677-115623d0-41dd-432b-bbb3-483cf3352c74.mp4"/></div></details>

### Step 3 – Rigging Custom Meshes
Jigglypuff is a great character for dipping your toes into model edits, as she's a simple character with not a lot of moving parts. Humanoid characters are more tricky, and are higher risk for janky deformations; I'll briefly go over some tips in the clean-up portion of this tutorial on common issues. For the majority of this tutorial though, I'll be making a Slime skin from Dragon Quest over Jigglypuff. 

There are a few roads you can go down, modelling it yourself, importing a ripped game model, or a combination of both.  I'll briefly go over some of the pros and cons for each method.

#### Importing a Ripped Game Model
* _Saves Time_ - If you're inexperienced, with textures and meshes already created, you don't have to stress over spending time learning how to model.
* _Unoptimized_ - Lots of models, especially from newer titles, often have polycounts (i.e. how many sides/triangles make up the model) that are outside SSBM's "budget".[^4]
   *  In addition to this, some models are in a default _A-Pose_ as opposed to _T-Pose_, which might require adjustments to be made on the model itself.
   *  Oftentimes, game models are constructed _tris_, sides made of 3 vertices, which are typically more difficult to manipulate compared to _quads_.
* _Good Learning Resource_ - One of the most constructive things to do with ripped game models is to study how they're made. Since you can look at them in Blender, you can try and understand what tools and shapes were used to make the model— improving your own in the process.
* _Less Control_ - If you don't make the model, you're locked into the original model's topology which doesn't always deform well with Melee's skeletons.
#### Creating a Model from Scratch
* _More Intensive_ - If you don't have experience modelling, or have a good workflow, creating your own model can be a lot more time consuming.
   *  The knowledgebase for creating a full character from scratch can be intimidating, especially when you involve UV unwrapping and texture creation. So I'd recommend starting out with modifying the existing Melee characters or ripped game models, and get comfortable with a workflow. 
* _More Control_ - Since you're creating the meshes, you get to make every decision, and iterate on a model without much of a headache. This also means you can be more conscious of the Melee skeleton you're skinning over.
* _Distribution_ - Wholly created by yourself, there's less of a grey area in redistributing your mod, especially if you decide to create a Patreon/monetize in any shape.
* _Fulfillment_ - More subjective, but 3D modelling is an art and skill, so it's fulfilling to model and texture a character from start to finish.

<details> <summary> Click Here for a Video of Creating the Mesh for Dragon Quest's Slime </summary> <div align="center"> <video src="https://user-images.githubusercontent.com/127040488/227730625-e6b21c57-0f14-4807-b7ef-5a8e3d4048ff.mp4"></div></details>







---
[^1]: I've linked Blender's LTS (Long Term Support) branch for its stability, but feel free to use the [latest available version](https://www.blender.org/download/).
[^2]: It's a good practice to save the .dat and texture files together in their own labelled folder, and it's recommended to keep an unedited copy of your .dat and texture folder as a backup
[^3]: By default, the imported `.dae` already comes broken down by material and is thus easier to manipulate and change without creating objects with too many assigned materials. The skeleton found in the `.dae` format is also incomplete and inaccurate and will result in crashes in-game, hence the inclusion of the `.smd` file.
[^4]: A budget refers to the general ceiling of total polys/tris rendered on screen. Since SSBM is a gamecube game, it's generally best to try and remain relatively low poly, and make up detail in texturing.

