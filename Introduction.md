# Introduction #


An ASE file is a small, human readable file format used for static meshes (a 3d model without any skeletal data) in various game engines.  This script fully supports features such as smoothing groups, vertex painting, collision objects, and more.  For video tutorials visit my [Youtube Channel](http://www.youtube.com/user/MCampagnini?feature=mhee).

# Details #
ASE Export Script
MCampagnini / Richisbored
Version 1.41

**Installation**

  * Download and extract the ASE Export Script
  * In Blender, File / User Preferences
  * Go to the Add-On Tab
  * Install Add-On, select the extracted python script
  * Click Save as Default to enable the script every time Blender loads (optional)

You will find a new export option in File / Export called Ascii Scene Export (.ase).  If you do not see the script in the export menu after following the installation instructions, open the Add-On tab and find the script under Import-Export: ASCII Scene Exporter.  Be sure that it is enabled by checking the box next to the add-on name.  Contact me on my website if you still have problems exporting.

**Mesh Requirements**

  * All non-collision meshes must be UV unwrapped.
  * All non-collision meshes must have a material and texture image applied.
  * Mesh should have two UV textures, one for lighting and one for textures.
  * Mesh should be modelled correctly.

**Optional**

  * Mesh may have more than one material, but will require a texture image for each material.
  * Mesh may have more than one UV texture.
  * Mesh may be assigned as a collision object.
  * Mesh may have more than one collision object to determine collision borders.
  * Mesh may be assigned smoothing groups.

**Collision Objects**

Assign a mesh as a collision object by prefixing each object name with UCX`_*`, where `*` can be anything you would like.

**Smoothing Groups**

Assign smoothing groups by edge selecting the border of the faces you want assigned to a smoothing group, press ctrl+e and mark sharp.  Any face group separated with sharp edges will be assigned a smoothing group.

**Vertex Painting**

Apply vertex painting in Blender as normal, be sure that you have at least two uv texture slots.  This is not a technical limitation, but due to time constraints I left the vertex painting code inside of a conditional that requires two uv textures.  In order to view your vertex painting in UDK you will have to import and set up your materials correctly within UDK.

**Change Log**

_Version 1.4 to 1.41_
  * Added an export option to recalculate normals

_Version 1.35 to 1.4_
  * Added vertex painting support.  Requires two uv textures.

_Version 1.3 to 1.35_
  * Fixed a bug causing ugly output when over 32 smoothing groups were assigned
  * Recoded a small portion of the script to remove complications when assigning more than 150 smoothing groups.
  * Fixed a crash by adding in a bpy.ops.mesh.reveal before calculating mesh data.  Any hidden parts of your mesh will be made visible before calculating mesh data.