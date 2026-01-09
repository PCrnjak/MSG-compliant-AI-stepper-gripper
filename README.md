# MSG-compliant-AI-stepper-gripper

> [!CAUTION]
> The gripper is still in BETA release meaning it will have some bugs from hardware to software!
>

[![License: CERN OHL v2 - Strongly Reciprocal](https://img.shields.io/badge/license-CERN--OHL--S--2.0-blue.svg)](https://spdx.org/licenses/CERN-OHL-S-2.0.html)
   ![Issues](https://img.shields.io/github/issues/PCrnjak/PAROL6-Desktop-robot-arm) ![release](https://img.shields.io/github/v/release/PCrnjak/PAROL6-Desktop-robot-arm) 
<p align="left">
  <a href="https://source-robotics.github.io/PAROL-docs/"><img src="https://img.shields.io/badge/doc-page-orange" alt="Documentation"></a>
  <a href="http://discord.gg/prjUvjmGpZ"><img src="https://img.shields.io/discord/1072498136284667955?logo=discord&color=blue" alt="Discord"></a>
  <a href="https://source-robotics.com//"><img src="https://img.shields.io/badge/Shop-shopping-purple?logo=shopify" alt="Shop"></a>
  <a href="https://www.linkedin.com/company/source-robotics/"><img src="https://img.shields.io/badge/LinkedIn-Follow-blue?logo=linkedin" alt="LinkedIn"></a>
  <a href="https://x.com/SourceRobotics"><img src="https://img.shields.io/badge/X-Follow-black?logo=x" alt="X"></a>
  <a href="https://www.youtube.com/@source-robotics"><img src="https://img.shields.io/badge/YouTube-Subscribe-red?logo=youtube" alt="YouTube"></a>
</p>



<img src="Photos/MSG gripper.png" alt="drawing" width="5000"/>

[Video of gripper!](https://www.youtube.com/shorts/DQgi8Ua-VAU)

**MSG compliant AI stepper gripper** is a gripper based on [StepFOC stepper drivers](https://source-robotics.com/products/spectral-micro-bldc-controller). It is a gripper capable of controlling its gripping force (We use FOC control on steppers :D), making it perfect for assembly tasks and human-robot collaboration AND AI training application because of its designed with cameras in mind! This gripper is modular in nature in 2 ways:
* Adjust grip length with different linear rails with options of 100mm,150mm and 200mm.
* Adjust grip strength with different stepper sizes, supporting steppers of lenght 21.5mm, 40mm and 60mm

Grip force can be adjusted allowing you to grasp a wide range of items; from delicate and soft to rigid and sturdy. 

Mechanical files and firmware are open source allowing you to add a custom griping tool and attach it to any robotic arm or robot. Gripper software is also open-source.

# How to build / Where to buy?

You can buy MSG gripper on our website: https://source-robotics.com/products/compliant-gripper

If you want to Source all the parts yourself and build your own follow these steps:

Print files from STEP files folder
* Example: For 100 mm rail style gripper
   - print everything from "common parts" folder
   - everything from "Linear rail dependant parts" folder -> "100mm rail" folder
   - everything from "Stepper dependant parts" folder depending on what stepper size you are using

* Source all the parts from the [BOM](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/BOM)
* Follow [Assembly instructions](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/Assembly%20manual) or [Video instructions](https://www.youtube.com/watch?v=127zXHKuqIg) to assemble your gripper
* Follow [DOCS](https://source-robotics.github.io/SSG48-gripper-docs/page1_about_the_gripper/) to get your gripper up and running.

# Documentation:
- [Official website](https://source-robotics.com)
- [Python API](https://github.com/PCrnjak/PAROL6-python-API)
- [Building instructions](https://github.com/PCrnjak/PAROL6-Desktop-robot-arm/tree/main/Building%20instructions)
- [BOM](https://github.com/PCrnjak/PAROL6-Desktop-robot-arm/tree/main/BOM)
- [DOCS](https://source-robotics.github.io/PAROL-docs/)
- [Video tutorials](https://youtube.com/playlist?list=PLSueoDrBt5MMTL9O8qAWZiJrNIf8-29Qz&si=Zca3UZKENje9ifow)

  
# More about our projects
- [Forum](https://discourse.source-robotics.com/)
- [Blog](https://source-robotics.com/blogs/blog)
- [Youtube](https://www.youtube.com/channel/UCp3sDRwVkbm7b2M-2qwf5aQ)
- [Hackaday](https://hackaday.io/project/191860-parol6-desktop-robotic-arm)
- [Instagram](https://www.instagram.com/source_robotics/)
- [DOCS](https://source-robotics.github.io/PAROL-docs/)
- [Twitter](https://twitter.com/SourceRobotics)


# ⚠️ Safety, Liability & Disclaimer

This project includes experimental software, hardware designs, and assembly documentation that are still under development and may contain bugs, errors, or incomplete features.
By using, building, or modifying this project, you acknowledge and agree that:
* You use this project entirely at your own risk
* You are solely responsible for safe assembly, testing, and operation
* No guarantee is made regarding correctness, safety, or reliability
* The authors are not responsible for any damage, injury, or loss resulting from the use or misuse of this project 
* Hardware performance and safety depend on user assembly, component quality, calibration, and handling, which cannot be guaranteed

This project is provided “as is.” If you choose to build a device yourself using these files, designs, or instructions, you do so without any warranties or guarantees, including regarding safety, reliability, or suitability for any particular purpose.

# Support

The majority of this project is open source and freely available to everyone. Your assistance, whether through donations or advice, is highly valued. Thank you!

 [![General badge](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/PCrnjak?locale.x=en_US)
[![General badge](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/PCrnjak)

## Project is under [CERN Open Hardware Licence Version 2 - Strongly Reciprocal](https://github.com/PCrnjak/MSG-compliant-AI-stepper-gripper?tab=CERN-OHL-S-2.0-1-ov-file)
