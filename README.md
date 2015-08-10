Projection mapping 101 {#tutorial_projection_simple}
=============================================================

Overview
--------

Requirements:

* an OpenNI2 compatible depth sensor
* a projector (*the resolution must be 1024 x 768*)
* a projection target (e.g., a mannequin or a face mask )
* we assume that the scene consists only of projection targets and flat surfaces (e.g., tabletop, wall).


Steps:

1. Run sensor_projector_calibration for structured lighting.

2. Run cluster_projection for object segmentation and 3D mesh export.

3. Open Unity3D project and import 3D mesh files for projection mapping.



Step-by-step instructions
--------

### Structured light

1. Run *rgbd-example-sensor_projector_calibration*.

2. Move *pattern* window to the projector screen, and press **f** key to make it fullscreen. If needed, press **w** to return to a window.

3. Place the depth camera in front of the projection target. See *camera* window to make sure that the projected lines are distinguishable on the screen. Also make sure that the target appears to be gray (not black) on the *depth* window.

4. Once the depth camera is placed, do not move it throughout the rest of the instructions.

5. Press space key to start structured lighting. Once started, wait until other windows shows up.

6. See *correspondenceX* and *correspondenceY* windows. If the target object appeared as red/black, proceed to the Segmentation and UV mapping. If not, there are problems with lighting (room lighting and structured light intensity) or the target surface is too glossy.

### Segmentation and UV mapping

1. Run *rgbd-example-cluster_projection*. Wait until windows show up.

2. *clusterN* windows represent planes. *mesh_N_M* windows represent other objects (including the target object). 3D meshes are saved as *mesh_N_M.obj*.

### Unity3D projection mapping

1. Open the Unity3D project and load *mapping.scene*.

2. Copy the 3D mesh file to the *Assets* folder.

3. Drag the 3D mesh file to the Hierarchy tab. Then, expand the *mesh_N_M* tree to reveal *default* GameObject.

4. Build and run an executable file (shortcut: ctrl + B). Uncheck *Windowed* for the fullscreen mode, and select the projector screen on *Select monitor*.
