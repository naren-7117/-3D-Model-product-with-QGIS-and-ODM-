**Creation of 3D Model product with QGIS and ODM**  

**Introduction:**

In this Project I have created 3d Model of India’s First Organic caper product and located at “NEERAVIPUTHUPATTI” where specially grown in 40 degree Celsius in Black soil. 

**Used Software** 

ffmpeg

Blender 

QGIS

ODM 

Docker

**Configuring ffmpeg**

The FFmpeg Windows executable file was acquired from the FFmpeg-Builds repository by BtbN. Unpack the .zip file into your preferred destination and subsequently append the directory path (excluding the file name) of ffmpeg.exe to the path variable in your System environment variables.

**Configuring OpenDroneMap ODM**

ODM, the open source command line toolkit of OpenDroneMap, relies on the presence of Docker. To utilize this toolkit, please refer to the ODM Quickstart guide

**Extracting video Frames** 

Create a new folder that will be your working directory  and put the video into the empty folder. Use ffmpeg to extract the  frames. You can experiment with different frame rates but generally  there will be little value in extracting at 60fps or whatever your phone  natively shoots at.

**Note**: When shooting the video with your phone, ensure the entire object fits in the video frame through out the video.

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
. ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ab055b87-d0c5-458a-81da-625f7c5bb1db/Untitled.png)
From the Download assets. Downlead the model 

In-order to use Alternative of Initializing web-ODM in Local computer Web based processing is also computed. and Speed and computation is compared
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9f324e60-44de-4b0b-993a-13c399601d91/Untitled.png)
Blender Processing

If you used the ODM processing steps outlined in after processing, download the assets for the textured model :
Next, fire up Blender, create a new General project, delete the default block and import the textured model Wavefront OBJ file:

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d19d9034-93ed-487f-ac88-88443ae63a58/Untitled.png)

Remove unwanted objects around model: After putting Blender into edit mode, select everything in the scene using the keyboard shortcut, A, and change your viewpoint so that you have a clear view of the axis you would like to cut along
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f7d6a513-3104-4be5-a688-c0dda600bb5b/Untitled.png)
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b2875f85-92ba-40d2-b3e0-5638308032b1/Untitled.png)

Switch back to View mode, add your texture back on, spin the model around and admire (ahem: quality check) your model. You can export the cleaned up model for back up purposes by writing the model to a Wavefront OBJ file,
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e93dd633-f091-437e-bdef-db3c9a6264e0/Untitled.png)
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d3295146-71b5-43b4-a2e7-ddc12aed8f49/Untitled.png)
Next we want to simplify the model as much as possible. QGIS is going to grind to a halt if you ask it to render complex models as symbols so we are going to 'decimate' the geometry such that it maintains it's form but loses as many vertices as possible
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ac8e0b68-f738-4c2b-b3ff-dbadf1ac3607/Untitled.png)

**Location identification in Q-GIS** 

Next, QGIS and make a new project with the OpenStreetMap XYZ layer added and create a scratch point layer with Z value. EPSG code is set 3857. According to Location
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/42318261-9361-4ea6-9dfc-9d28c3a6f38a/Untitled.png)

Then in your point layer properties, set the 2d symbology to no symbol
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/945b1f12-9ed6-45ec-a0fa-06961afd1bd7/Untitled.png)

3D view styling is opened in Q-GIS for better visualizations  And the 3D symbology to use your new object file
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/846d2bb4-da82-4b73-a4ac-cb909bc9079d/Untitled.png)

Now navigate to your model in the 3D map and enjoy the 3D awesomeness of your real world model in QGIS is created 
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6ca78018-e631-4e2a-a773-82a9a4559981/Untitled.png)
![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1b79e83a-c166-4283-9b53-e3a28f527256/Untitled.png)
