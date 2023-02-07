# Robotics in Animation
Workshop on Robotics in Animation | _[San José State University Department of Design](https://www.sjsu.edu/design/undergraduate-programs/animation-illustration/index.php)_ | February 2023


## Background

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

## Software Tools
Here are list of cutting-edge tools that may help in your production pipeline:

[![Runway ML Frame Interpolation](https://img.youtube.com/vi/_1lOBWFgAyo/sddefault.jpg)](https://www.youtube.com/watch?v=_1lOBWFgAyo)

- Runway's [Frame Interpolation](https://runwayml.com/ai-magic-tools/frame-interpolation/)

## Useful links

- [Robots](https://github.com/visose/Robots) for Grasshopper
  - A fanstastic, open source Rhino Grasshopper plug-in to control Universal Robots.
  
- Universal Robots
  - [Programming Manual](https://s3-eu-west-1.amazonaws.com/ur-support-site/105198/scriptManual_SW5.10.pdf)
  - [UR5e](https://www.universal-robots.com/products/ur5-robot/) | [Datasheet](https://www.universal-robots.com/media/1807465/ur5e-rgb-fact-sheet-landscape-a4.pdf)
  - [UR3e](https://www.universal-robots.com/products/ur3-robot/) | [Datasheet](https://www.universal-robots.com/media/1807464/ur3e-rgb-fact-sheet-landscape-a4.pdf)
  
## Connecting to the Robot

> Begin by powering on the robot and pressing Start.

1. Connect via ethernet and [setup your network](https://pureinfotech.com/set-static-ip-address-windows-10/) on a _static address_ that is on the same network as the UR5e.

> SJSU Laptop login info: .\roboto , pw: Robotrobotrobot1

> The UR5e has the static IP address `10.0.0.10`, subnet mask `255.255.255.0` and default gateway `10.0.0.1`.

> Set your static IP address to `10.0.0.XXX` (e.g., `10.0.0.100`) and copy the same subnet mask and default gateway as the robot.

2. Do a [`ping` test](https://www.hellotech.com/guide/for/how-to-do-a-ping-test-windows-10) to check your connectivity.

> Windows Users: if the ping test fails, your firewall is likely blocking incoming and/or outgoing connections. See troubleshoout tips [here](https://windowsreport.com/windows-10-unable-to-ping-other-computers/#:~:text=What%20can%20I%20do%20if%20I%20can%E2%80%99t%20ping%20other%20computers%20in%20Windows%2010%3F).

3. Once you get a response from the `ping`, you are ready to send a program to the robot.

4. When you are ready to receive a program from Grasshopper, put the robot into [`Remote` mode](https://robodk.com/doc/en/Robots-Universal-Robots-How-enable-Remote-Control-URe.html).

## Running .urscript from Rhino / Grasshopper

1. Install the [Robots](https://github.com/visose/Robots) for  Grasshopper plugin using these instructions:

> 1. Install in Rhino 7 using the _PackageManager_ command, search for Robots.

> 2. Restart Rhino and open Grasshopper. There should be a new tab in Grasshopper named Robots.

2. Open the `follow_target.3dm` file, run the `Grasshopper` command to start Grasshopper, then open the `follow_target.gh` file in Grasshopper.
3. Navigate to the `GREEN` panel and verify that IP address input is the same as the robot's IP address.
4. When you're ready, press the `Send Button` to send the camera path to the robot.

> `CAUTION`: stand clear of the robot before moving and be close to the emergency stop — especially on the first run.

5. When successfully sent, you should see a pop-up window on the teach pendant asking if you are ready to go to the first position.

> `WARNING`: the robot can take unpredictable route to the first position.

6. Press `Continue` to move the the first position.
7. A pop-up window appears after every motion so you can decide when the robot should advance to the next position.

