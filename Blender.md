# Blender Installation Guide

The following steps are to download and install the latest stable version of Blender on your computer.

The aims are:
1. To have Blender installed on the local PC
2. To familairize with Blender basics and operations.

## Step 1: Download the Installer

1. **Navigate to the Official Website:** Open your web browser and go to the official Blender website: `https://www.blender.org/`
<img width="3456" height="2040" alt="image" src="https://github.com/user-attachments/assets/e9ef6b94-d2fe-4849-85a6-fc55f685629f" />

2. **Locate the Download Button:** Click on the **"Download Blender"** button.
3. **Select Your Version:** The website typically auto-detects the operating system (Windows, macOS, or Linux).
4. **Start Download:** Click the final download button to save the installer file to your computer.

## Step 2: Run the Installer (Windows/Linux)

### For Windows:

1. **Run the EXE:** Locate the downloaded `.exe` file and double-click it to start the installation wizard.

### For Linux (Using Snap or Tarball):

Check out this link for useful information on this: https://docs.blender.org/manual/en/latest/getting_started/installing/linux.html
* The easiest method is usually through the software manager, like Snap. Look for "Blender" in your software center. You can also install by writing in the terminal `snap install blender --classic`

* Alternatively, using the `.tar.xz` file:

  1. Extract the downloaded file.

  2. Navigate to the extracted directory and run the Blender executable directly. No formal installation is required.

## Step 2: Getting Started with Blender

The following are helpful tutorials to leanr about Blender before starting to work in the following tasks.
  1. https://youtu.be/Ci3Has4L5W4?si=WVs0_OB_OExaQv9A
  2. https://www.youtube.com/playlist?list=PLsGl9GczcgBumq6fLmmR1ZYYn4EDkIg5B

The Blender documentation also provides lots of helpful resources: https://docs.blender.org/

# Creating a Realistic Leaf 

The aims are:
1. To create a realistic leaf using a leaf image in Blender
2. To create an anchor point (origin) where the leaf will be attach to the stem

Relevant resources:
Video Guide: https://drive.google.com/file/d/1661lM53iJ8kLIGcY4T0kFD5NtbuBvMAI/view?usp=drive_link
Final Models can be found in https://github.com/kmerckae/internship_samuel/tree/master/Plant%20Generation/Blender/Assets. The images used also in creating the leaf can be found in the same folder and they need to be downloaded to a folder before they can be used.

## Step 1: Preparation and Importing the Image Plane

1.  **Initial Setup:** Open Blender and delete the default cube.

2.  **Import the Leaf Image:** Go to **Add** > **Image** > **Image as Planes**. Select the photo of your leaf and import it.

<img width="3456" height="2040" alt="image" src="https://github.com/user-attachments/assets/78020b44-0b99-4858-b8b9-1c0df7d1ad54" />


3.  **Adjust View and Scale:** Change your rendered view to **Material Preview** in the top right corner so you will see the material (leaf) imported. Scale the imported leaf up slightly and adjust its rotation if necessary.

## Step 2: Cutting Out the Leaf Shape

1.  **Enter Edit Mode:** With the image plane selected, go into **Edit Mode**.

2.  **Use the Knife Tool:** Select the **Knife Tool**.
   
<img width="3456" height="2040" alt="image" src="https://github.com/user-attachments/assets/f87c2c92-bcca-44b7-847d-803521a22900" />

3.  **Cut the Outline:** Zoom in and begin cutting along the edge of the leaf, starting at the bottom.
    * Ensure you follow the edge of the leaf.

5.  **Finalize the Cut:** Once you have moved all the way around the leaf, connect your last dot back to your first one and press **Enter**.

6.  **Delete Excess Faces:** Switch to the selection tool. Select the faces/planes surrounding the leaf outline. **Delete** these faces. You should now have an initial leaf shape. To delete excess faces in Blender, enter Edit Mode (Tab key), select the faces you want to remove, and then press X to open the delete menu. You can select multiple faces by holding Shift and clicking, or use tools like Select All by Trait > Interior Faces for hidden geometry.

## Step 3: Finalizing the Leaf Object

<img width="3456" height="2040" alt="image" src="https://github.com/user-attachments/assets/bad60ee6-a2e1-47f1-801e-e4d4f6a7b413" />


1.  **Set the Origin Point:** This step is crucial for placement on a tree (This is where the leaf will be attached to the stem later on).
    * Go to the **Top View**.
    * Select the **3D Cursor** tool.
    * Click on the **stem/end point** of your leaf.
    * Go back to the selection tool.
    *  Go to **Edit Mode** by pressing the **Enter Key**, Left-click on the object (the leaf) whereby you should see the orange outline. Then, Right-click and select **"Set Origin to 3D Cursor"**. The **origin point** will now be located at the end of the leaf stem.

# Flower Creation.

The aims are:
1. To create a 3D flower in Blender
2. To create an anchor point (origin) where the flower will be attach to the stem
3. To be able to adjust the parameters of the flower such as size, number of petals, colour.

Relevant resources:
It is important to have some understanding of Blender Geometric node before following these steps. A relevant tutorial to understand how geometric node works generally is: https://www.youtube.com/watch?v=aTeLyeVO0Dc, while this tutorial details how flower can be created: https://www.youtube.com/watch?v=VVK7n9rMsHI&t=2944s

## Step 1: Create the Blossom Base Leaf Shape

1.  **Add a Curve:** Add a **Quadratic Bezier Curve** node and set its resolution to 10. You can find any node by pressing **Shift+A** in the geometric node window and searching for the node by typing the name. Also to find the Quadratic Bezier curve, you can select "Curve", the "Primitives", and then "Quadratic Bézier" in the add button.
2.  **Define Points:** Define the start, middle, and end points of the curve.
    * *Important:* Ensure the **end point** is set to the zero point (`0, 0, 0`) for stable bending and transformations later.
    * *Example Points:* Start (`2, -0.3, 0`), Middle (`1, -0.2, -0.4`), End (`0, 0, 0`).
3.  **Increase Resolution:** Add a **Resample Curve** node to define the shape of the blossom leaf later. You can alos find the Resample curve by going to "Curve", "Operations", and then "Resample Curve".

<img width="1635" height="882" alt="image" src="https://github.com/user-attachments/assets/bf53b5ae-e9f4-4f0a-853a-7b5e83956e9d" />


## Step 2: Define the Leaf Profile and Thickness

1.  **Prepare for Mesh:** Add a **Set Curve Radius** node followed by a **Curve to Mesh** node.
2.  **Define Profile:** Copy the initial **Quadratic Bezier Curve** and connect it to the **Profile Curve** input of the `Curve to Mesh` node. Zero out its parameters, then set the start X value to `-0.5` and the endpoint to `0.5` to define the leaf's cross-section.
3.  **Control Radius:** Use a **Float Curve** node and a **Spline Parameter** node to control the thickness/width of the leaf from beginning to end.
    * Connect `Factor` from **Spline Parameter** to `Value` of **Float Curve**.
    * Connect `Value` from **Float Curve** to the `Scale` of the `Curve to Mesh` node. Adjust the Float Curve points to define the desired leaf shape.
4.  **Thickness Control:** For easy thickness adjustment, use a **Value** node connected to a **Combine XYZ** node. The X parameter is affected twice; one connection uses a **Math** node set to **Multiply (-1)** for the negative value.
5.  **Align and Transform:** Use a **Transform** node to rotate the leaf for perfect initial alignment.

## Step 3: Refine the Leaf Shape

1.  **Subdivision:** Add a **Subdivision Surface** node right after the `Curve to Mesh` node, setting the level to `1` for a smoother appearance.
2.  **Geometry Deletion (Custom Shape Control):** Add a **Delete Geometry** node and use an **Endpoint Selection** node. By setting the `Endpoint Selection` start and end sizes, you can delete geometry from the beginning or end of the leaf to shape it.
3.  **Material Assignment:** Add a **Set Material** node to prepare for material assignment.

<img width="2111" height="721" alt="image" src="https://github.com/user-attachments/assets/ef7aee75-cb6e-45c8-8f7a-e50b0d9fba77" />

## Step 4: Create the Blossom Leaf Stem

1.  **Stem Geometry:** Use another **Set Curve Radius** node connected to the `Resample Curve` output from the "blossom base shape" group.
2.  **Stem Profile:** Use a **Curve to Mesh** node, defined by a **Curve Circle** node, as the profile.
3.  **Thickness:** Set the `Curve Circle` radius very small (e.g., `0.003`) and check **"fill caps"**.
4.  **Shape Control:** Use a **Float Curve** and **Spline Parameter** to control the shape/thickness of the stem.
5.  **Combine:** Use a **Join Geometry** node at the end to connect the leaf and the stem geometries.
6.  **Switch/Material:** Add a **Set Material** node and a **Switch** node so the stem can be turned on or off easily.

<img width="3456" height="2160" alt="image" src="https://github.com/user-attachments/assets/c1257d47-a976-424b-8847-c19db93a585a" />

## Step 5: Create the Flower Middle (Stamen)

1.  **Base Shape:** Add an **Icosphere** node. Set subdivisions to `3` and the size (radius) to approximately `0.13` meters.
2.  **Initial Transformation:** Use a **Transform** node to scale the Z-axis (e.g., `0.35`) to shape the inner part of the blossom.
3.  **Extrusion:** Add a **Subdivision Surface** node (level 2) followed by an **Extrude Mesh** node. Initially set the offset scale to zero.
4.  **Targeted Extrusion (Upper Faces):** To only extrude the upper part of the icosphere, use a complex selection setup:
    * Use a **Separate XYZ** node to get the position of each face.
    * Connect the `Z` value to a **Math** node set to **Greater Than**.
    * Control the sensitivity of the selection using another **Math** node set to **Divide** (e.g., dividing by 100) and connect the output into the lower input of the `Greater Than` node.
    * Connect the output of the `Greater Than` node to the **Selection** input of the `Extrude Mesh` node.
5.  **Refinement:** Add a **Set Shade Smooth** node.
6.  **Variety:** Add a second **Extrude Mesh** node, connecting the selection from the first extrusion to the selection of the second. Use a divided value (Math Divide by 10) for the offset of the second extrusion for better control and variety.
7.  **Material:** Add a **Set Material** node for the middle part.

<img width="3456" height="2160" alt="image" src="https://github.com/user-attachments/assets/985ac677-bc83-47cd-afe6-0e9a1093b14b" />

## Step 6: Distribute Blossoms around the Stamen

1.  **Distribution Curve:** Create a **Curve Circle**. For the radius, use the exact same radius value used for the Icosphere in Step 5 (use the group input).
2.  **Prepare Instance Input:** Create a separate **Join Geometry** node that only accepts the output from the **"blossom custom shape"** group (Step 3). This prevents the "flower stamen" from being included in the instances.
3.  **Instance on Points:** Use an **Instance on Points** node. The `Curve Circle` goes into the **Points**, and the separate `Join Geometry` output (the leaf) goes into the **Instance**.
4.  **Rotation Alignment:** To align the leaves around the circle, use a **Curve to Points** node connected to the `Curve Circle`.
    * Connect the `Rotation` output of the `Curve to Points` node to a **Rotate Euler** node, and then connect the `Rotate Euler` output to the **Rotation** input of the `Instance on Points` node.
5.  **Instance Adjustment:** Insert a **Rotate Instance** node after the `Instance on Points` node to adjust the X rotation so the leaves face the correct direction.
6.  **Randomness:** Add randomness to the rotation using a **Vector Math** node (set to **Add**) and a **Random Value** node (between -0.2 and 0.2).

<img width="3456" height="2160" alt="image" src="https://github.com/user-attachments/assets/7f3d8f0e-c47d-41e4-a6dd-23f29f006ca2" />

## Step 7: Create and Bend the Main Flower Stem

1.  **Curve Line:** Add a **Curve Line** node, setting the end point Z value for the desired height (`0.1`).
2.  **Resolution:** Add a **Resample Curve** node (resolution 10).
3.  **Bending Setup:** To bend the stem, use a **Set Position** node.
    * Use the **Index** of the vertices, multiply it, and then feed that value into the **Angle** input of a **Vector Rotate** node.
    * Divide the multiplied value by a large number (100) using a **Math** node to keep the control sensitive.
    * Connect the **Position** to the **Vector** input of the `Vector Rotate` node, and set the `Vector Rotate` node to X-axis (or the desired bending axis).
    * Connect the **Vector** output of the `Vector Rotate` to the **Position** input of the `Set Position` node.
4.  **Stem Thickness:** After the `Set Position` node, add a **Set Curve Radius** node.
5.  **Stem Profile:** Use a **Curve to Mesh** node with a small **Curve Circle** as the profile. Use a **Math Divide** node by 100 (0.51 divided by 100) to control the radius sensitively.
6.  **Thickness Variation:** Use a **Spline Parameter** node and a **Color Ramp** node connected to the `Curve to Mesh`. **Invert** the `Color Ramp` so the stem is thick at the beginning and thinner at the end.
7.  **Material:** Add a **Set Material** node.
8.  **Scale Control:** Use a **Random Value** node (0.05 to 0.2) connected to the **Scale** input to vary the size of the individual blossoms.
9.  **Blossom Control (Opening/Closing):** Use a **Group Input** (set to vector) combined with **Combine XYZ** nodes and a **Math** node to influence the Y channel.

## Step 8: Assemble the Flower onto the Stem

1.  **Final Instance:** Use an **Instance on Points** node.
2.  **Points Input:** Connect the **Curve** output from the main stem (after the `Set Position` node but before the `Curve to Mesh` node in Step 7) into the **Points** input of the `Instance on Points` node.
3.  **Instance Input:** Connect the combined output of the **"distribute blossoms"** group (Step 6) and the **"flower stamen"** group (Step 5) as the **Instance**.
4.  **Initial Scaling:** Scale the instance down dramatically (`0.05`) as the components were modeled large.
5.  **Select Top Point:** Use an **Endpoint Selection** node connected to the **Selection** input of the `Instance on Points` node to ensure the flower only appears at the top of the stem.
6.  **Alignment:** Use an **Align Euler to Vector** node connected to a **Curve Tangent** node. Connect the `Tangent` output to the **Vector** input and the `Align Euler` rotation output to the `Instance on Points` **Rotation** input. Set the alignment axis to Z.
7.  **Finalize:** Connect the output to the final **Join Geometry** node.
   
<img width="2439" height="837" alt="image" src="https://github.com/user-attachments/assets/9315514f-dcc4-414b-8265-29e40a80587e" />

## Step 9: Material Setup

1.  **Material Assignment:** Assign materials to all **Set Material** nodes.

<img width="3451" height="2150" alt="image" src="https://github.com/user-attachments/assets/54b89424-8a0e-4a40-bc9f-9445b24a043b" />

Final Asset id named **StrawberryFlower2.blend**

# Fruit Creation

The aims are:
1. To create a realistic fruit in Blender
2. To create an anchor point (origin) where the fruit will be attach to the stem
3. To be able to adjust the parameters of the fruit such as size, ripeness.

Relevant resources:
Relevant resources can be found at https://www.youtube.com/watch?v=6EE5W6f3tc4 (This tutorial create fruit using geometric node, makking it easy to adjust its parameters), https://www.youtube.com/watch?v=gL_uOBhNwqM (This tutorial model strawberry using triditional CAD approach, the writeup below is more related to this tutorial.)

## Step 1. Modeling the Strawberry Base Shape

The base shape can be created using a cube.
1.  **Start the Base:** Keep the default cube.
2.  **Rough Shape:** Enter **Edit Mode**. Select the bottom vertices and **scale them down** to create a taper.
3.  **Refine Shape:** Add a loop cut, scale it a little, and scale the upper part also.
4.  **Compress:** Go to the right view and minimize the size on the Y-axis.
5.  **Subdivision and Apply:** Go to the **Modifier** section, add a **Subdivision Modifier** (3 levels), then **Apply** the modifier.
6.  **Displacement:** Add a **Displacement Modifier**, use the **'ends of the right'** option, set the value to `1`, and **Apply** it.
7.  **Create Seed Impressions (Geometry):** Enter **Edit Mode** (face selection active). Press **Ctrl+B** to bevel. Use **Ctrl+I** to invert the selection. **Extrude** the selected faces inward.
8.  **Forming the Divots:** Go up and use **'individual origin'** as the transform pivot. **Extrude** the faces down and **scale** them again. **Scale** these faces on the Z-axis.
9.  **Protrusions:** Go back and choose the **'medium pivot'**. **Extrude** these faces out. Choose **'individual origin'** again and scale down these faces.
10. **Smoothing:** Add a **Subdivision Modifier** to smooth the shape. Right-click on the shape and choose **Smooth Shading**.

<img width="2726" height="1363" alt="image" src="https://github.com/user-attachments/assets/35f00c69-fb39-44b0-9e24-1ac0ac18a358" />

## Step 2. Creating and Applying Materials (Shading)

1.  **Preparation:** Go to the **Shading** window. Change the look dev HDRI for more contrast.
2.  **Gradient Color:** In the node editor, add a **Gradient Texture** and a **Color Ramp** (from Converter). Attach these nodes. Add a **Mapping** node and a **Texture Coordinate**. Set the **Y angle rotation** to `90` degrees. Set the color stops.
3.  **Roughness and Subsurface:** Adjust the **Roughness** slightly. Add a **Subsurface Scattering** component using an orangish color.
4.  **Main Bump:** Add a **Noise Texture** (from Texture), a **Color Ramp** (from Converter), and a **Bump** node (from Vector).
5.  **Connect Bump Nodes:** Attach the `Noise Factor` to the `Color Ramp Factor`, the `Color Ramp Color` to the `Bump Height`, and the `Bump Normal` to the `Material Normal`. **Reduce the height** of the bump and scale the `Noise Texture`.
6.  **Seed Material (Using Selection from Step I.A):** Enter **Edit Mode** and ensure the faces selected earlier for the divots are still selected.
7.  **New Material Slot:** Go to the material icon, click `+`, and add a new material.
8.  **Copy and Modify Seed Material:** **Copy** the nodes from the first (red) material and paste them into the new material. Change the color to yellow. Set the **Gradient Texture** to **Spherical**.
9.  **Seed Bump:** **Copy** the bump nodes from the first material and paste them into the yellow material. Reduce the size of the noise and increase the strength to `1`. Attach the `Normal` to the `Normal`.
10. **Assign Seed Material:** Use **Ctrl++** to select neighbor faces and click **Assign**.

<img width="2901" height="1716" alt="image" src="https://github.com/user-attachments/assets/51582ce7-29f8-46ea-bd92-18da9a6f6ce8" />

## Step 3. Adding and Texturing the Leaves

1.  **Import Leaves:** Go to **Import** and choose **Image as Plane** (ensure the 'image' add-on is activated in preferences if unavailable).
2.  **Apply Texture:** Attach the leaves texture. The texture should include an **alpha channel** to create transparency.
3.  **Position:** Rotate the plane by `90` degrees, scale it, and move it up.
4.  **Geometry Refinement:** Enter **Edit Mode**, add **subdivision 3 times**.
5.  **Shaping:** Activate the **proportional editing** option. Select vertices and move them down. Scale the leaves a little bit.
6.  **Subdivision and Hiding:** Add the **subdivision modifier**. Scale the leaves on Z and hide them.
7.  **Adjust Top:** Select the middle face of the top of the strawberry and scale it on the Z-axis.
8.  **Position Leaves:** Exit **Edit Mode**, select the leaves, and scale and rotate them on Z. **Smooth** the leaves mesh.
9.  **Add Translucency (Leaves Material):** Select the leaves. In the node editor, add a **Mix Shader** and a **Translucent Shader**. Attach the `Translucent Shader` to the `Mix Shader`. Bring the color from the texture and attach it to the shader input.
10. **Duplicate and Rotate:** **Duplicate** the mesh leaves (**Shift+D**) and rotate them **180 degrees**. Rotate these duplicated leaves **180 degrees** so they are flipping to the upper side.
11. **Randomize Leaves:** **Randomize** the geometry of the leaves also.

<img width="2901" height="1716" alt="image" src="https://github.com/user-attachments/assets/2ae188e8-fb9c-4660-acc7-39dcca3c8491" />
<img width="3451" height="2158" alt="image" src="https://github.com/user-attachments/assets/6b405c9e-8305-4357-a3f1-b1020dda83f1" />
<img width="3451" height="2158" alt="image" src="https://github.com/user-attachments/assets/3fb21caf-d322-4491-95ee-2f2c0b269ced" />


Final Output is named **StrawberryFruit2.blend**

# Composition in Blender

The Image below shows the final geometric node arrangement and a sample generated plant:
<img width="3096" height="1491" alt="image" src="https://github.com/user-attachments/assets/32dcc029-59de-462d-b505-4d91b707304b" />

<img width="3451" height="2158" alt="image" src="https://github.com/user-attachments/assets/59322cae-dbd3-4138-ae39-550eea58dc64" />

The aims are:
1. Create a base curve that represents the stem.
2. Turn that curve into a mesh for the visible stem (using a profile circle).
3. Resample the curve to get evenly spaced points.
4. Use those points to instance different components (leaf, 3-leaf cluster, fruit, flower).
5. Control where each component appears by index / random attributes / curve parameter.
6. Add variation (rotation, scale, tilt) with Random Value and utilities.
7. Join everything and output final geometry.

Very good resources: https://www.youtube.com/playlist?list=PLsGl9GczcgBsDZ3jQPwP1p6evNI22wevP (This resource is needed only for the composition part. It is generally about geometric nodes, but I only used the knowledge for the composition. You would not exactly need it to follow the previous parts. This tutorial is actually very important as the whole composition is based on it. Though the model that was created was not what was used in our case, the geometric node setup is an important resource.), https://youtu.be/9NkMkYVz7bw?si=3gyN7EtOnfPqDMC7 (The "how to make trees" tutorial was the second method I later adopted, so each plant will be a single mesh, but the geometric node setups from the previous method are very relevant and key to the final output I was later able to create, so I recommend that someone go through the two tutorials thoroughly to gain more knowledge on how to maybe in the future make modifications or even change structure of things.)

A new blender file should be created and append all previously modelled into it. 

## Step 1: Main Stem and Input Structure

The first task is to take the input curve and turn it into the main physical stem mesh, complete with organic curvature.

1. **Start the Network:** Apply a **Geometry Nodes Modifier** to a simple **Bezier Curve** object.

2. **Create the Stem Mesh (`Stem` Group):** Use a series of nodes to bend and solidify the input curve:

   * Apply a `Set Position` node combined with a `Noise Texture` and `Vector Math` nodes to introduce random, organic bends and droop into the curve path, using your `Curve Factor` input to control the intensity.

   * Use a `Set Curve Radius` node to define the thickness tapering (thicker at the bottom, thinner at the tips) using a `Spline Parameter` and a `Float Curve`.

   * Use a `Curve to Mesh` node, connecting it to a small `Curve Circle` (radius very small, e.g., 0.005) as the profile to create the final 3D cylindrical stem mesh.

   * **Output:** The result of this group is your main, procedurally bent stem mesh.

## Step 2: Generating and Distributing Root Leaves

The `Root Leaves` group is responsible for creating the cluster of large leaves near the ground, ensuring they don't overlap.

1. **Isolate Distribution Area:** Take the original curve data and focus the distribution on the bottom-most part of the curve.

2. **Scattering Points (`Root Leaves` Group):**

   * Add a **`Distribute Points on Faces`** node.

   * **Set the Method to `Poisson Disk`**. This prevents leaves from being placed too close together, controlling the density and realism.

   * Feed the point geometry into an **`Instance on Points`** node.

3. **Instancing Leaf Geometry:**

   * Add an **`Object Info`** node and select your pre-modeled, fully textured leaf asset. Connect its **Geometry** output to the **Instance** input of the `Instance on Points` node.

4. **Randomization:** Use a **`Random Value`** node (Vector) to drive the **Scale** and another one for the **Rotation** input of the `Instance on Points` node. This ensures no two leaves look exactly the same in terms of size or orientation.

5. **Output:** Feed the final output of this section into a main **`Join Geometry`** node.

## Step 3: Dynamic Selection of Branch Tips (Flower, Fruit, or Leaf)

This section handles the choice of whether a branch tip holds a flower, a fruit, or just a new leaf/apex, and then instances that choice onto the curve endpoints.

1. **Collect Components:** Add three separate **`Object Info`** nodes:

   * One for your `Fruit` model.

   * One for your `Blossom` (Flower) model.

   * One for your `Blossom Tree Leaf` (the smaller leaves at the top of the stalk).

2. **Implement the Selection Switch (`Flower + Fruit` Group):** Make reference to the screenshot above

3. **Distribute the Selection:** Take the resulting geometry (whichever was selected by the switch chain) and feed it into a final **`Instance on Points`** node.

4. **Isolate Tip Points:** The **Points** input for this `Instance on Points` node must come from the stem curve's **endpoints**.

5. **Final Orientation:** Use the `Curve Tangent` of the stem curve combined with an `Align Euler to Vector` node to correctly rotate the instance so the flower/fruit faces outward or upward.

## Step 4: Final Assembly and Output

The final step is joining all the components produced by the previous phases.

1. **Main Join:** Add a **`Join Geometry`** node toward the right side of your network.

2. **Connect all Feeds:** Connect the final geometry outputs from the three main streams into this single `Join Geometry` node:

   * The **Stem Mesh** (Output of the `Stem` Group).

   * The **Root Leaves** (Output of the `Root Leaves` Group).

   * The **Instanced Tips** (Output of the `Instance on Points` from Phase 3).

3. **Group Output:** Connect the final output of the **`Join Geometry`** node to the **`Group Output`**.

The Final file is named **main.blend**

This video shows how to use the resulting main file created to create a plant. https://drive.google.com/file/d/1cq-OrT2SvUuPZ-WAee3equj8pT_o1ABQ/view?usp=drive_link. The video is showing just the side view; the image shows the top view of the plant. It is actually the same quality just the video was recorded in a 2D single view to make it easier while drawing the plant.

# Soil Bed Creation

The aims are:
1. To create a soil bed where the plants will be instanced in Blender.

Relevant resources:

This shows how to model the soil and the containing wood. A Good resource to learn how the tray can be created is https://www.youtube.com/watch?v=Ci3Has4L5W4, while this resource shows how to create and apply the wooden and soil materials: https://www.youtube.com/watch?v=144TWlEYFtM

## Prerequisites

1.  Download **the Soil and wood PBR textures**. https://drive.google.com/file/d/1_aSX7WMhdxNpIKqnjMM_zxTXXKkwtl1w/view?usp=drive_link, https://drive.google.com/file/d/1BhenR4Sovd5H-G44sLXVlg8q9u1Y_ES4/view?usp=drive_link
2.  **Unzip the downloaded** texture files.

## Step 1: Initial Scene Setup

1.  In Blender, press **X** to delete the default object.
2.  Press **Shift A** and add an example **plane**.
3.  Press **S** to scale the plane.
4.  Press **Tab** to enter edit mode.
5.  Right-click and select **subdivide**.
6.  Add a bunch of subdivisions (say 100).

## Step 2: Material and Node Wrangler Setup

7.  Go into the materials tab and **add a new material**.
8.  Drag the top right corner of the viewport to **add a new window**.
9.  To enable an automatic node setup for PBR textures, you need to enable an add-on called **Node Wrangler**, which is included in Blender.

<img width="1597" height="995" alt="Screenshot from 2025-10-27 23-04-49" src="https://github.com/user-attachments/assets/1653aeff-1d4f-4767-b6c2-56f450cee491" />

## Step 3: Applying the PBR Texture

10. Select the **principled node**.
11. Go into Node Wrangler and select **add principled setup**.
12. Select the folder that you had previously unzipped.
13. Select **all of the images** within that folder.
14. Go into **rendered view** to see the texture applied to the plane.

<img width="3456" height="1415" alt="Screenshot from 2025-10-27 23-13-08" src="https://github.com/user-attachments/assets/492dfeed-7fd2-437f-bddf-c90df33cb353" />

## Step 4. Creating the Tray Object

15.  **Add a Cube:** On the left-hand toolbar, press and hold the object icon (showing a cube) and select the option to **add a cube**.
16.  **Define the Base:** Press and hold your mouse to draw the cube. 
17.  **Define the Height:** Release the mouse and drag up slightly to define the height, making the tray **fairly thin** .
18.  **Initial Positioning:** Select the **Move tool** and move the tray over slightly so that it is **not intersecting with the soil** .

## Step 5. Creating the Ridge

10.  **Switch to Edit Mode** by pressing the **Tab key**.
20.  **Select the Top Face:** Use the selection icons at the top to select the **face** option [4]. Click to select the **top face** of the cube.
21.  **Inset the Face:** Use the **Inset tool** (which is an icon on the left-hand side, or shortcut **I key**) [5]. Click on the white circle on the face to adjust the inset and create a **smaller internal face**.
22. **Extrude to Create Depth:** Use the **Extrude tool** (found right above the Inset tool on the left-hand side). Press and hold the plus icon that appears [6], and **lower this new interior face** to create a tray-like shape.

<img width="2090" height="1165" alt="Screenshot from 2025-10-27 23-26-36" src="https://github.com/user-attachments/assets/c1e44c9b-8f36-4c13-9138-5e32fa40a575" />

## Step 6. Final Placement and Materials

23. **Return to Object Mode** by pressing the **Tab key**.
23. **Final Positioning:** Select the **Move tool**  and move the tray over to the soil plane.
24. **Adjust Placement:** Orbit around the view to ensure the soil is sitting **directly on the tray**. Adjust the Z-axis until the cookie is properly placed.
25. **Add Material:** Select the tray [9]. Go to the **Material icon** (in the properties panel) and click **Add** to create a new material and add the wall PBR just like in the soil case.

<img width="2090" height="1165" alt="Screenshot from 2025-10-27 23-32-37" src="https://github.com/user-attachments/assets/f6e188c5-775a-4bb1-9731-8af4493b429c" />

# Running Python Scripts in Blender

You can automate mesh generation, geometry manipulation, or other 3D tasks in Blender using the **Blender Python API (`bpy`)**.  
This allows you to create procedural assets or perform batch operations directly from a Python script.

---

## Example Script: Create a Simple Box Mesh

Save this file as **`box.py`** in your project directory:

```python
import bpy
import bmesh

# Clear existing objects
bpy.ops.object.select_all(action='SELECT')
bpy.ops.object.delete(use_global=False)

# Create a new mesh and object
mesh = bpy.data.meshes.new("MyMesh")
obj = bpy.data.objects.new("MyObject", mesh)

# Link the object to the current collection
bpy.context.collection.objects.link(obj)

# Define a simple cube geometry
bm = bmesh.new()
bmesh.ops.create_cube(bm, size=2.0)
bm.to_mesh(mesh)
bm.free()

# Move object slightly upward
obj.location = (0, 0, 1)

# Save the file automatically
bpy.ops.wm.save_mainfile(filepath="box.blend")

print("Mesh created successfully!")
```
## Run the Script Without Opening Blender’s GUI

Blender provides a **headless (background)** mode that lets you run Python scripts without launching the interface.

```bash
blender --background --python box.py
```
After running the command, a new file called box.blend will be saved in your current directory.

<img width="3454" height="2146" alt="Screenshot from 2025-10-28 19-14-09" src="https://github.com/user-attachments/assets/4a83ab6b-e2b8-4626-bc63-0e932062160b" />

# Greenhouse Modeling

Aim:
To model a strawberry plants greenhouse. 

Resources: https://youtu.be/71xN9BBAd9I?si=wQqc7mzStyGtvO3E

Final results can be found in Greenhouse.blend

# Observations and Findings on Blender Plant Instancing Issue

During this phase of the project, I focused on developing the greenhouse structure, which delayed my earlier update. Regarding the plant instancing process, after conducting several tests with different meshes and configurations, I observed that the issue is not related to computing power, but likely due to a bug in Blender.

<img width="3456" height="2160" alt="Screenshot from 2025-11-07 21-15-40" src="https://github.com/user-attachments/assets/c4005c81-c339-4dc2-8eac-41412fbb14ca" />


Specifically, the system freeze consistently occurs after applying a PBR (Physically Based Rendering) texture to the soil bed mesh. When using a plain mesh without any material, Blender performs as expected. However, once the PBR texture is applied, the software begins to lag and eventually freeze. Notably, even after removing the material, the freezing persists until a new mesh object is created. This behavior strongly suggests a potential internal error or bug within Blender’s material handling system.

Additionally, applying a simple color material to the mesh also introduces minor lag, which can be reasonably attributed to hardware limitations rather than software malfunction.

Although these symptoms appear to stem from a Blender-related issue, it is possible that with deeper knowledge of PBR material properties and Blender’s rendering system, a suitable workaround could be developed.

For the time being, the most practical approach appears to be manually placing each plant instance on the soil bed. I have attached a screenshot illustrating this method. The primary limitation of this approach is that Python scripting cannot be utilized for automation, requiring manual placement of each plant within Blender before exporting the final model as a USD file. (The attached image may not fully reflect the actual rendering quality, as it is a screenshot.)

Moving forward, this manual placement approach can be adopted temporarily to complete the greenhouse setup and begin development of the robotic subsystem. While the robot training progresses, further investigation can be conducted to resolve the Blender instancing issue. A similar problem is anticipated in modeling the hanging plant trays suspended from the greenhouse roof via rods, as this also depends on point instancing — which currently fails when PBR materials are involved.

In summary, manual instancing presents a workable short-term solution while deeper troubleshooting and optimization efforts continue.
