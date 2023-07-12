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

1. Create a new project in WebODM using the Add Project button. Name the project and add an optional project description.
2. Upload the `.png`  images into WebODM
3. Run the WebODM processing using the following settings.

![1](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/8ed17ca8-56ae-4463-aa77-e0faafb271cf)

From the Download assets. Download the model 

In order to use an Alternative of Initializing web-ODM in a Local computer Web-based processing is also computed. and Speed and computation are compared

![2](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/2dae95e6-b799-4c36-bd64-a21a542d2aa6)


Blender Processing

If you used the ODM processing steps outlined after processing, download the assets for the textured model :
Next, fire up Blender, create a new General project, delete the default block, and import the textured model Wavefront OBJ file:

![3](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/1e06c2aa-4c25-45e1-892c-a2af791c4e32)

Remove unwanted objects around the model: After putting Blender into edit mode, select everything in the scene using the keyboard shortcut, A, and change your viewpoint so that you have a clear view of the axis you would like to cut along

![4](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/e27dc425-d789-411d-ac34-3c347e53243a)


Switch back to View mode, add your texture back on, spin the model around, and admire (ahem: quality check) your model. You can export the cleaned-up model for backup purposes by writing the model to a Wavefront OBJ file,

![5](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/46b54b52-7618-4bdc-a258-4a1b86568c9a)

![6](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/37a8454b-f302-4688-9cb9-04b8235fb9b4)

![7](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/3af2c283-30c8-4120-b64a-115aee321d67)

Next, we want to simplify the model as much as possible. QGIS is going to grind to a halt if you ask it to render complex models as symbols so we are going to 'decimate' the geometry such that it maintains its form but loses as many vertices as possible

![8](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/f2e1bddd-e413-488e-82a9-7e02156c7d20)



**Location identification in Q-GIS** 

Next, QGIS and make a new project with the OpenStreetMap XYZ layer added and create a scratch point layer with Z value. The EPSG code is set to 3857. According to Location

![9](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/ea961f2a-ee86-459d-8b98-36a269489146)


Then in your point layer properties, set the 2d symbology to no symbol

![10](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/7d2f32de-0d2e-4b2b-b30d-a04d39baebab)


3D view styling is opened in Q-GIS for better visualizations  And the 3D symbology to use your new object file

![11](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/bd162c42-679b-49b6-95e2-b17038691c92)


Now navigate to your model in the 3D map and enjoy the 3D awesomeness of your real-world model in QGIS is created 

![12](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/4f788faa-034d-4204-889e-7d5b324444c1)


![13](https://github.com/naren-7117/-3D-Model-product-with-QGIS-and-ODM-/assets/128035374/3598273c-6e18-4588-9830-b0e2368dd8e5)


