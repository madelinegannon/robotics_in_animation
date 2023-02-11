# Robotics in Animation
Workshop on Robots and Stop Motion Animation | [San José State University Department of Design](https://www.sjsu.edu/design/undergraduate-programs/animation-illustration/index.php) | February 2023


## Introduction

In this workshop, we'll be designing and programming robotic motion-controlled camera paths for stop motion animation.

We'll be using [Rhino 3D and Grasshopper](https://www.rhino3d.com/6/new/grasshopper/) to design the camera motion and focal points, and the [Robots for Grasshopper](https://github.com/visose/Robots) plug-in to program the UR5e robot arm holding the camera.


## Getting Started

1. Download a trial version of [Rhino 7](https://www.rhino3d.com/download/).
2. Install the [Robots for Grasshopper](https://github.com/visose/Robots) plug-in by following [these](https://github.com/visose/Robots#install) instructions:

  - Install in Rhino 7 using the `_PackageManager` command, search for `Robots`.
  - Restart Rhino and open Grasshopper. There should be a new tab in Grasshopper named Robots.
  - Install a robot library by clicking on the `Libraries` button of a `Load robot system` component.
    - The robots from the library should appear in a value list connected to a `Load robot system` component.

3. For more detailed information on the Robots plug-in, I recommend this great [YouTube playlist](https://www.youtube.com/watch?v=vAe47zN-d48&list=PLqtxhH1qb3Mw5A_YbvHDfrq4DNNfLtcW-) from  [@robin-gdwl](https://github.com/robin-gdwl).


## Connecting to the Robot

> Begin by powering on and starting the robott.

1. Once the robot is fully powered on, connect an ethernet cable from your computer to the ethernet port in the robot's control box.

2. Set up a LAN with a [static IP address](https://pureinfotech.com/set-static-ip-address-windows-10/) on the same network as the UR robot.

    -  Here is [how to find](https://robodk.com/doc/en/Robots-Universal-Robots.html#UR-IP) the robot's IP address.

3. Do a [`ping` test](https://www.hellotech.com/guide/for/how-to-do-a-ping-test-windows-10) to check your connectivity.

> `Windows Users`: if the ping test fails, your firewall is likely blocking incoming and/or outgoing connections. See troubleshouting tips [here](https://windowsreport.com/windows-10-unable-to-ping-other-computers/#:~:text=What%20can%20I%20do%20if%20I%20can%E2%80%99t%20ping%20other%20computers%20in%20Windows%2010%3F).

4. Once you get a response from the `ping`, you are ready to send a program to the robot.

5. When you are ready to receive a program from Grasshopper, put the robot into [`Remote` mode](https://robodk.com/doc/en/Robots-Universal-Robots-How-enable-Remote-Control-URe.html).

## Running `urscript` Remotely from Rhino / Grasshopper

Our Grasshopper scripts allow you to send and run your program directly to the robot at the press of a button. This faster workflow is very useful for quickly iterating and fine-tuning a program.

1. Start Rhino 7 and then run the `Grasshopper` command to start Grasshopper.
2. Open the `.3dm` and `.gh` pairs of files from this repo. For example: open `follow_target.3dm` in Rhino and `follow_target.gh` in Grasshopper.
3. Navigate to the `GREEN` panel and verify that IP address input is the same as the robot's IP address.
4. When you're ready, press the `Send Button` to send the camera path to the robot.

> `CAUTION`: stand clear of the robot before moving and be close to the emergency stop — especially on the first run.

5. When successfully sent, you should see a pop-up window on the teach pendant asking if you are ready to go to the first position.

> `WARNING`: the robot can take unpredictable route to the first position.

6. Press `Continue` to move the the first position.
7. A pop-up window appears after every motion so you can decide when the robot should advance to the next position.

## Running a `.urp` Program from the Teach Pendant

Our Grasshopper scripts also generate a static `.urp` file that you can manually load and run on the Universal Robots robot. This workflow is useful for reliably running and re-running a program, once it has already been fine-tuned.

___

## Inspiration

### AI-powered Video Software
Here are list of cutting-edge tools that may help in your production pipeline:

[![Runway ML Frame Interpolation](https://img.youtube.com/vi/_1lOBWFgAyo/sddefault.jpg)](https://www.youtube.com/watch?v=_1lOBWFgAyo)

- Runway's [Frame Interpolation](https://runwayml.com/ai-magic-tools/frame-interpolation/)


[![KarenX Dolly Zoom](https://img.youtube.com/vi/FgXiPAAAK2A/sddefault.jpg)](https://www.youtube.com/watch?v=FgXiPAAAK2A)

- Luma AI 3D Capture & NeRF [software](https://lumalabs.ai/) and [app](https://apps.apple.com/us/app/luma-ai/id1615849914)
  - [KarenX](https://80.lv/articles/mcdonald-s-commercial-made-using-nerf-luma-ai) NeRF Commercial for McDonalds
  - More NeRF [examples](https://www.nvidia.com/en-us/research/ai-art-gallery/instant-nerf/)

### Visual Engineering

[![Steve Giralt](https://img.youtube.com/vi/HuEyrLbJ25w/sddefault.jpg)](https://www.youtube.com/watch?v=HuEyrLbJ25w)

[Steve Giralt](https://www.the-garage.tv/about), Visual Engineer, Master of Robotic Motion Control for Practical Effects

___

### Virtual Production & Cinema Robots

[![Motorizaed Precision](https://img.youtube.com/vi/X6mzlZ4ZFpg/sddefault.jpg)](https://www.youtube.com/watch?v=X6mzlZ4ZFpg)

[Motorized Precision](https://www.motorizedprecision.com/), US-based cinmena robot integrator | [KIRA](https://www.motorizedprecision.com/compare) robot

---

[![Mark Roberts Motion Control](https://img.youtube.com/vi/WQrrQv1sJcY/mqdefault.jpg)](https://www.youtube.com/watch?v=WQrrQv1sJcY)

[MRMC](https://www.mrmoco.com/), UK-based cinmena robot integrator | [Bolt Mini](https://www.mrmoco.com/motion-control/bolt-mini-model-mover/) robot for moving models

---

[![BTS Virtual Production](https://img.youtube.com/vi/jcozOywzb3E/sddefault.jpg)](https://www.youtube.com/watch?v=jcozOywzb3E)

Cinema Robots on Set

___

### Disney Research
#### Physical Puppets
[![Disney Research Robotic Characters](https://img.youtube.com/vi/MARwhwXEVz8/sddefault.jpg)](https://www.youtube.com/watch?v=MARwhwXEVz8)

- [Designing Cable-Driven Actuation Networks for Kinematic Chains and Trees](https://la.disneyresearch.com/publication/designing-cable-driven-actuation-networks-for-kinematic-chains-and-trees/)
- [Bend-It: Design and Fabrication of Kinetic Wire Characters](https://la.disneyresearch.com/publication/bend-it/)
- [Motion Retargeting for Robotic Characters](https://la.disneyresearch.com/publication/publication-process-vibration-minimizing-motion-retargeting-for-robotic-characters/)


___


## References

### Universal Robot How-Tos

- [Programming Robots in Grasshopper | Robots Plugin for Universal Robots](https://www.youtube.com/watch?v=vAe47zN-d48&list=PLqtxhH1qb3Mw5A_YbvHDfrq4DNNfLtcW-) video tutorials by [@robin-gdwl](https://github.com/robin-gdwl).
- [How To Transfer a Program via FTP](https://robodk.com/doc/en/Robots-Universal-Robots.html#UR-FTP) with [Filezilla](https://filezilla-project.org/download.php) 
- [How To Run a Program or Script from the UR Controller](https://robodk.com/doc/en/Robots-Universal-Robots.html#UR-StartProg)
- [How to enable Remote Control on UR e-Series](https://robodk.com/doc/en/Robots-Universal-Robots.html#DriverURRemoteEnable)
- [How to program a Relative Move from the UR Controller](https://www.universal-robots.com/articles/ur/programming/ur-polyscope-move-with-respect-to-a-custom-featureframe/)

### Universal Robot Manuals
- [Programming Manual](https://s3-eu-west-1.amazonaws.com/ur-support-site/105198/scriptManual_SW5.10.pdf)
- [UR5e](https://www.universal-robots.com/products/ur5-robot/) | [Datasheet](https://www.universal-robots.com/media/1807465/ur5e-rgb-fact-sheet-landscape-a4.pdf)
- [UR3e](https://www.universal-robots.com/products/ur3-robot/) | [Datasheet](https://www.universal-robots.com/media/1807464/ur3e-rgb-fact-sheet-landscape-a4.pdf)
  

