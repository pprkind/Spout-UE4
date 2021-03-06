*Modification of original plugin by [AleDel](https://github.com/AleDel/Spout-UE4) with UE versions 4.19+.*

**This was tested with:**
* 4.19
* 4.20
* 4.21

# Spout-UE4
This is a [Spout](http://spout.zeal.co/) Plugin for Unreal Engine. It allows you to send and receive textures using Spout framework.

Sender and Receiver only DirectX 11.

# Installation and Use

Put the code in _Plugins_ folder (for example "_yourproject/Plugins/SpoutUE4_"). For detailed instructions please refer to [Unreal Engine 4 and Lightact Video Tutorials](https://www.youtube.com/playlist?list=PLcNPGta1d2XDcSsz8zcW0f2lPSawnW3mR) or [Unreal Engine section](https://support.lightact-systems.com/category/1-user-guide/3-0-unreal-engine/) of Lightact User Guides.

## Sending Spout

This is done with the **Spout sender** node which has can send texture either from the Game viewport or from a Render Targert 2D: 
  * **Game Viewport** sends the image of the viewport, but please note that it doesn't work in standalone or packaged game.
  * **TextureRenderTarget2D** in which case you should create a _SceneCaptureComponent2D_ and a *Render target 2D* which you should reference in the node.

use **Close Sender** node to close Spouts. The best way is to connect it to **Event EndPlay** node.

## Install Example

* Create new C++ *First Person* project
* unzip ExampleSpout.zip in the "Content" folder of your project
* unzip code plugin in folder "Plugins" as mentioned above, if there is no "Plugins" folder, create it
* restart project
* load Spout scene
* if you encounter compile errors you have to delete and re-insert identical nodes

[ExampleSpout.zip](http://aledel.github.io/Spout-UE4/exampleSpoutUE4/ExampleSpout.zip)

![CaptureSpout2](http://aledel.github.io/Spout-UE4/images/spout2.jpg)
This image corresponds to the "Spout" scene. 

## Packaged game
To make this plugin work in a packaged game you have to disable using 'pak' files. You do that by:
1. going to File->Package project->Packaging settings
2. once there uncheck 'Use Pak File' checkbox

# Issues
If you get missing Spout.dll error when trying to launch the game manually copy Spout.dll from:
[gameName]\Plugins\SpoutUE4\ThirdParty\Spout\lib\amd64

to: 
[gameName]\Binaries\Win64