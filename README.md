**Creation of 3D Model product with QGIS and ODM**  

**Introduction:**

In this Project, I have created a 3d Model of India’s First Organic caper product located at “NEERAVIPUTHUPATTI” where specially grown at 40 degree Celsius in Black soil. 

**Used Software** 

FFmpeg

Blender 

QGIS

ODM 

Docker

**Configuring ffmpeg**

The FFmpeg Windows executable file was acquired from the FFmpeg-Builds repository by BtbN. Unpack the .zip file into your preferred destination and subsequently append the directory path (excluding the file name) of ffmpeg.exe to the path variable in your System environment variables.

**Configuring OpenDroneMap ODM**

ODM, the open-source command line toolkit of OpenDroneMap, relies on the presence of Docker. To utilize this toolkit, please refer to the ODM Quickstart guide

**Extracting video Frames** 

Create a new folder that will be your working directory  and put the video into the empty folder. Use ffmpeg to extract the  frames. You can experiment with different frame rates but generally,  there will be little value in extracting at 60fps or whatever your phone  natively shoots at.

**Note**: When shooting the video with your phone, ensure the entire object fits in the frame throughout the video.

**Video Details:**

**length**:55/sec

**Frame Width:**1080

**Frame Height:**1920

**Data rate:**32159kbps

**Total Birate**:32416kbps

**Frame rate:** 25.00 frames/second

Open the Windows Command Prompt and change the working directory using the command `cd` to where the video file is located (your working directory). Execute  the command below to extract the frames (images) from the video at 1  frames/second (fps)

The %07d dictates that the ordinal number of each output image will be formatted using 7 digits.

**ffmpeg.exe -i caper.mp4 -vf fps=1 -f image2 image-%07d.png**

**ODM Processing**

The exported `.png` images can now be imported into WebODM. Use the steps below to create a project and then load the images into WebODM:

1. Create a new project in WebODM using the Add project button. Name the project and add an optional project description.
2. Upload the `.png`  images into WebODM
3. Run the WebODM processing using the following settings.
   
![1](https://github.com/naren-7117/3d/assets/128035374/ea0dc4ca-1d27-4566-b1cb-31b49064c472)

From the Download assets. Download the model 

In order to use an Alternative of Initializing web-ODM in a Local computer Web-based processing is also computed. and Speed and computation are compared

![2](https://github.com/naren-7117/3d/assets/128035374/01bde6f7-43dd-4eb5-b34e-94eca6c66668)

Blender Processing

If you used the ODM processing steps outlined in after processing, download the assets for the textured model :
Next, fire up Blender, create a new General project, delete the default block, and import the textured model Wavefront OBJ file:

![3](https://github.com/naren-7117/3d/assets/128035374/1a8b7be4-8db8-4d54-9779-03da255e6532)

Remove unwanted objects around the model: After putting Blender into edit mode, select everything in the scene using the keyboard shortcut, A, and change your viewpoint so that you have a clear view of the axis you would like to cut along

![4](https://github.com/naren-7117/3d/assets/128035374/98b2a9e7-e072-452c-8d86-9420a166d2d8)

Switch back to View mode, add your texture back on, spin the model around, and admire (ahem: quality check) your model. You can export the cleaned-up model for backup purposes by writing the model to a Wavefront OBJ file,

![5](https://github.com/naren-7117/3d/assets/128035374/349fc219-2455-44d6-aa9d-7b18cfbfa176)

![6](https://github.com/naren-7117/3d/assets/128035374/3732a95f-e636-4da5-a826-838a5c2a399c)

![7](https://github.com/naren-7117/3d/assets/128035374/38859163-3fef-453b-bc59-1f6c17c77f85)


Next, we want to simplify the model as much as possible. QGIS is going to grind to a halt if you ask it to render complex models as symbols so we are going to 'decimate' the geometry such that it maintains its form but loses as many vertices as possible

![8](https://github.com/naren-7117/3d/assets/128035374/ada91879-89d9-456d-b883-09e74391a3ae)


**Location identification in Q-GIS** 

Next, QGIS and make a new project with the OpenStreetMap XYZ layer added and create a scratch point layer with Z value. EPSG code is set 3857. According to Location

![9](https://github.com/naren-7117/3d/assets/128035374/21124264-d45f-4f82-86f5-616dd11485a8)

Then in your point layer properties, set the 2d symbology to no symbol

![10](https://github.com/naren-7117/3d/assets/128035374/d98a02bf-3ed1-424c-b9bc-26710bbf6784)


3D view styling is opened in Q-GIS for better visualizations  And the 3D symbology to use your new object file

![11](https://github.com/naren-7117/3d/assets/128035374/e30bd506-adfb-4d43-a117-40fb86e82d03)


Now navigate to your model in the 3D map and enjoy the 3D awesomeness of your real world model in QGIS is created 

![12](https://github.com/naren-7117/3d/assets/128035374/9221ca8f-1b07-4e77-9223-d5d7047593d7)

![13](https://github.com/naren-7117/3d/assets/128035374/58689837-49c6-4061-8e3d-61d0c94eea3d)

