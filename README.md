# ProtestXR
Repository for the app used during the 3/5 MIHC playtest

This is a simple demo application which scans a fiducial marker and places a pre-determined model over it. In this case, as part of the course, all the students were scanned holding a 'protest' stance using [Trnio](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=2ahUKEwjT_dz-zbHoAhXloFsKHSMaByMQFjAAegQIAxAB&url=https%3A%2F%2Fapps.apple.com%2Fus%2Fapp%2Ftrnio%2Fid683053382&usg=AOvVaw19Zq5W2Bn0NQDkFp2zOLPO). The resulting models were stiched together in Maya before being brought into Unreal. 

The slider at the top of the application screen can be used to scale the model up, while the "Show Debug Menu" button at the bottom of the screen contains a modified version of Unreal's demo application debug menu, containing options to show the world origin, detected planes, and pins.  

<p align="center">
  <img src="https://i.imgur.com/7NGUy9y.jpg" width="200"> 
</p>
<p align="center">
  <em>Application screen-shot showing Darica's model above the fiducial marker</em>
</p>

### Modify the app
I have only one fiducial marker currently being detected in this app; to change it, find the `AR Candidate Image` under root named `fiducial` and change the set image to your own (first import the image to Unreal and change its compression settings to `UserInterface2D`).

To change the model being used, under Blueprints>Placeable, change the StaticMesh associated with `BP_Placeable`.

You can add more fidicuals by creating more `AR Candidate Image` objects and adding them to the `Candidate Images` array belonging to `D_ARSessionConfig`.

### Build the app
In order to build, your build-related settings should follow those described in the [Augmented Reality Quick-Start](https://docs.unrealengine.com/en-US/Platforms/AR/HandheldAR/ARQuickStart/index.html) according to your desired platform.
