# SSBM Skin Creation Tutorial (For Blender)

**Before we begin, I want to thank [xRunRiot](https://twitter.com/xRunRiot) for compiling a lot of the steps together and publishing them in the Animelee discord. Prior to his effort, a lot of skin modding knowledge was decentralized and incomplete.**

This tutorial focuses on the model-editing portion of creating a skin, ignoring things like character portraits or stock icons. It isn't fully comprehensive— there are gaps in our collective knowledge, so this tutorial will be a work in progress. With that in mind, let us begin.

**I've included video demonstrations on each step, so do not be put off by the huge wall of text. Eventually I will add more visual aids.**

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
Put plainly, we'll be using the `.dae` for the meshes/textures (if your mod is using the character model), and the `.smd` for the skeleton/vertex weights.[^3].
##### Importing and preparing the `.dae` file for use
1. `File > Import > Collada (.dae)` then navigate to the `.dae` file you just created with HSDRaw
    * In the Blender viewport, you can hold the `Z` key and mouse over _Material Preview_ to see the assigned material.
      *  Some of the textures may look wrong or mirrored in strange ways. **Don't fret, they're _fine_.** A lot of Melee's textures are mirrored and scaled in-game to look correct. Thhose can be configured in HSDRaw's texture settings.
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

### Step 3 — Custom Meshes
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

For this tutorial, I'll be creating the mesh and texture. If you're interested in using ripped models, check out the website, [**The Models Resource**](https://www.models-resource.com/). It's a great compendium of ripped game models uploaded that are easily accessible and well organized.

<details> <summary> Click Here: Creating the Mesh for Dragon Quest's Slime </summary> <div align="center"> <video src="https://user-images.githubusercontent.com/127040488/227730625-e6b21c57-0f14-4807-b7ef-5a8e3d4048ff.mp4"></div></details>
 
### Step 4 — Creating Materials and Assigning Textures

Whether you've created your own model, or simply need to apply a texture to an imported model, being able to navigate the materials panel and _Shading_ view are important. In Blender, the textures (i.e. the image file itself) are contained within a _material_ that's assigned to an object.
 
1. Select the mesh object you want to create a texture for.
2. Navigate to the _Material Properties_ menu in the navigation panel (the little, checkered red ball), and click `+New` to create a new material.
    * If you have the _Material Utilities_ add-on enabled, `Shift+Q` opens up a menu for quickly creating and assigning textures. It's helpful for quickly assigning materials to multiple objects, if need be.
3. With the new material created, go to the _Shading_ view, located at the top of the screen. This screen shows the nodes[^5] that comprise the material for the _active object_[^6].
    * `Shift+A` is a shortcut to open up the _Add_ menu. Once the menu is open, search the word "Image" and add an `Image Texture` node into the material. Drag the yellow _Color_ output on the `Image Texture` node to the receiving _Base Color_ circle on the `Principled BSDF` node.
4. Click the folder icon on the `Image Texture` node to open the browser, then navigate to and open the texture you require.
    * It's worth noting that any change made to a material applies across every object that has that material assigned. That means if I change the texture in my _slime_ material, every single object with the _slime_ material will also change texture.
  
<details> <summary> Click Here for a Video Demonstration</summary> <div align="center"> <video src="https://user-images.githubusercontent.com/127040488/227736752-282cbebe-df74-4be7-898f-ec5a0fc71a23.mp4"></div></details>
 
Since I'm creating an Animelee style mod, I'm going to use a "palette blocks" method when it comes to texturing, essentially just placing color blocks and assigning each face of the model to a corresponding color instead of a traditional texturing method. See below for what the texture looks like.

![palette](https://user-images.githubusercontent.com/127040488/227795931-e4169fd6-2817-4eb3-9cbd-3e69083d5960.png)
 
Luckily, creating these textures is simple, just create a texture with a resolution that's a base two resolution (e.g. 64x64 px, 128x64 px, 256x256 px, etc.) with a base color and a color for any shading or highlights. Personally, I also typically include a solid black palette for the Animelee outline.
 
#### UV Mapping (for Animelee)

![santa-uv](https://user-images.githubusercontent.com/127040488/227798630-dd55a79d-84fa-4a93-af08-4b95eec046a5.png)

UVs are essentially a set of digital instructions on how to wrap a texture around a 3D model, much like a candy wrapper around a chocolate. UV Mapping is the process of laying out the "instructions"/coordinates that a model follows. It can be really complicated in general— beyond the scope of this tutorial, and since Animelee models are textured entirely within solid colors, we only need to point each polygon to the correct color.

1. With your material created and assigned to the relevant objects, navigate to the _UV Editing_ view at the top of the window. 
2. Select the object with the UVs you'd like to modify and go into _Edit Mode_ (`Tab` is the shortcut for switching to _Edit Mode_).
3. In _Edit Mode_, you can switch between vertex selection, line selection, and face selection (`1`, `2`, or `3` on the keyboard respectively, or the icons on the top bar). For this tutorial I'll primarily use face selection (`3`).
    *   The `A` key is a shortcut to select every _visible_ face in _Edit Mode_. `H` is the shortcut for hiding selected faces, `Alt+H` unhides all faces, and `Shift+H` hides every face _except_ for those you have selected.
        *   There are many ways to speed up face selection, so feel free to look around the _Select_ dropdown menu in _Edit Mode_ and experiment a little.
4. With a face selected, you should see a "UV" appear in the left panel of the screen, over the selected texture. It should resemble the shape of the selected faces, but since we're assigning it a color on our palette, it doesn't need a shape. 
    *   You may have to select the UVs that appear in a similar fashion to how you would select something in _Edit Mode_. 
    *   Once selected, `M` → _At Center_, snaps all corners of the selected UV into a single spot, guarenteeing  a solid color when moved over a palette square. `G` is the shortcut for the move tool, to move selected vertices (it's the same in UV Editing and 3D editing).
5. Repeat for all the faces of the model to their desired color square, until your model is fully "textured".
 
<details> <summary> Click Here for a Video Demonstration</summary> <div align="center"> <video src="https://user-images.githubusercontent.com/127040488/227807941-d851d6af-4e20-49ae-953c-6d114fa63882.mp4"></div></details>
 
### Step 5 — Weights and Rigging the Model
 
**This is the most important step of the process.** At this point, let's assume you've got your model ready and the skeleton prepared. It's time to bind, or _parent_, the mesh objects to the skeleton.

Important terms for Rigging/Weight Painting:
*   _Vertex_ - An individual point, or corner, of the model. Every model is essentially a collection of vertices that are connected into _faces_ a.k.a. polygons.
*   _Edge_ - Two connected vertices.
*   _Face_ - Three or more connected edges that make up a flat plane. Three connected edges are typically referred to as a _tri_, four edges are a _quad_, and four or more are called _ngons_. Ngons should be avoided in character modeling, opt for tris and quads.
*   _Vertex Group_ - A collection that refers to specific vertices. 
      *   In rigging, this is how you tell games and 3D software which bones affect specific parts of the model. 
          *   This is achieved by naming the vertex group after the bone. 
          *   SSBM character skeletons have bones typically named something like `JOBJ_0` or `JOBJ_32`. 
      *   For example, the left shoulder bone is `JOBJ_30`, we would select all the vertices of the shoulder and assign them to a vertex group also named _JOBJ_30_
*   _Vertex Weights_ - A single vertex can, and will, be a part of any number of vertex groups. Weights are a decimal value from `0.0 – 1.0` that determine how much a bone _influences_ a vertices' movement.
      *   For example, say Vertex A is assigned to _Bone A_ with a weight of `.65`, and _Bone B_ with a weight of `.35`. When the skeleton is animated, _Bone A_ will influence the movement of the vertex more than _Bone B_. This is obvious in places like knees or elbows, where deformation is plain to see.
      *   The total weight of a vertex _can_ surpass a value of `1.0` (i.e. Bone A → `.75` & Bone B → `.40` total to `1.15`), however, in Melee weights **cannot surpass a total value of `1.0`**. They need to be _normalized_.
*   _Normalize_ - The process of taking the weights of a vertex and proportionally making them total to `1.0`. Lucky for us, Blender has a built-in function for normalizing selected vertices.
      *   For example, if _Bone A_ has a weight of `1.0` and _Bone B_ has a weight of `3.0`, normalizing will result in _Bone A_ having a weight of `.25` and _Bone B_ `.75`, totalling `1.0`. **This is very important to prevent crashes and visual glitches in your character mod**.
*   Zero Weights - A zero weight vertex is one that isn't assigned to any vertex group. **If any vertex on your model has a zero weight, the game will crash when loading it**.
      *  **This means that every vertex needs to be assigned to a vertex group**. Not only that, but **every vertex, on every mesh, must be normalized**.
  
Now, onto rigging your model! There are three workflows I will briefly go over, each with their own pros and cons.
1. Automatic Weights - When you parent an object to the skeleton, you're given the option to `Parent with Automatic Weights`— I _highly_ recommend avoiding this method. It oftentimes results in fast, inaccurate weights, and the clean-up of the weights will take longer than the time saved by doing it automatically.
    *   This option is based on the skeleton's bones. Melee skeletons have a lot of redundant/useless bones that are never used, meaning this will weigh some vertices to useless bones, resulting in a glitchy mess.

---

[^1]: I've linked Blender's LTS (Long Term Support) branch for its stability, but feel free to use the [latest available version](https://www.blender.org/download/).
[^2]: It's a good practice to save the .dat and texture files together in their own labelled folder, and it's recommended to keep an unedited copy of your .dat and texture folder as a backup
[^3]: By default, the imported `.dae` already comes broken down by material and is thus easier to manipulate and change without creating objects with too many assigned materials. The skeleton found in the `.dae` format is also incomplete and inaccurate and will result in crashes in-game, hence the inclusion of the `.smd` file.
[^4]: A budget refers to the general ceiling of total polys/tris rendered on screen. Since SSBM is a gamecube game, it's generally best to try and remain relatively low poly, and make up detail in texturing.
[^5]: Nodes are how shaders and compositing are constructed in Blender. They're pretty intuitive and color coded, for the purpose of this tutorial, there's not any advanced knowledge needed— especially because compatibility when it comes to importing into HSDRaw.
[^6]: It's important to realize there's a difference between the _active_ object and _selected_ objects. The active object is the most recently (shift) clicked object, indicated by the bright orange outline around the mesh. When selecting multiple objects, actions are typically applied to the active object first and foremost. For example, if you `Shift+LMB` Object B → Object A, Object A will be the active object.

