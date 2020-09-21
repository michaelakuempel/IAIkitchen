# IAIkitchen
Basic VR IAI kitchen setup in Unity, a minimalistic version of the Unreal IAI kitchen https://github.com/robcog-iai/RobCoG
This version does not include lighting/ walls etc. since its intended use is to simulate communication to the Knowledge Graph (Tutorial for this can be found here: https://github.com/michaelakuempel/Unity-REST-KG). It will then be deployed to AR.


To set up the project with Unity 2018 using the .Net framework:
Go to Edit -> Project Settings
- check the Windows Store icon
Player settings:
in -> Other section
- change Scripting Backend to .Net
in -> Publishing section
- check the following Capabilities: 
    InternetClientServer
    PrivateNetworkClientServer
    SpatialPerception (if you want to include object recognition and/ or anchors for AR)
in -> XR Settings
- check: Virtual Reality Supported (ensure Windows Mixed Reality is set)
	 Vuforia Augmented Reality Supported (again for object recognition -> will be used in later version with AR)
Quality settings:
- set the quality for your used system to low


Project setup for Mixed Reality and VR:
 1.   Select Main Camera in the Hierarchy panel
 2.   In the Inspector panel, find the Transform component and change the Position from (X: 0, Y: 1, Z: -10) to (X: 0, Y: 0, Z: 0)

Additionally, for HoloLens:
 3.   With the Main Camera still selected in the Hierarchy panel, find the Camera component in the Inspector panel and change the Clear Flags dropdown from Skybox to Solid Color.
 4.   Select the Background color picker and change the RGBA values to (0, 0, 0, 0)
 5.   With the Main Camera still selected in the Hierarchy panel, find the Camera component in the Inspector panel and change the Near Clip Plane field from the default 0.3 to the HoloLens recommended 0.85.
 
For VR keep the Skybox setting etc.


In file -> build settings
change to Universal Windows Platform, add open scene and check Unity C# Projects, click on switch platform

to build the project, click build, create a new folder named App for your finished project

To load the project (HoloLens), go to the created folder and click on LabScan.sln to open the project in Visual Studio.
In Visual Studio, change the Config to Release, Platform to x86 and build to device
