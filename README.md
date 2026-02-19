# MSG-compliant-AI-stepper-gripper

> [!CAUTION]
> The gripper is still in BETA release meaning it will have some bugs from hardware to software!
>

[![License: CERN OHL v2 - Strongly Reciprocal](https://img.shields.io/badge/license-CERN--OHL--S--2.0-blue.svg)](https://spdx.org/licenses/CERN-OHL-S-2.0.html)
   ![Issues](https://img.shields.io/github/issues/PCrnjak/MSG-compliant-AI-stepper-gripper) ![release](https://img.shields.io/github/v/release/PCrnjak/MSG-compliant-AI-stepper-gripper) 
<p align="left">
  <a href="https://source-robotics.github.io/PAROL-docs/"><img src="https://img.shields.io/badge/doc-page-orange" alt="Documentation"></a>
  <a href="http://discord.gg/prjUvjmGpZ"><img src="https://img.shields.io/discord/1072498136284667955?logo=discord&color=blue" alt="Discord"></a>
  <a href="https://source-robotics.com//"><img src="https://img.shields.io/badge/Shop-shopping-purple?logo=shopify" alt="Shop"></a>
  <a href="https://www.linkedin.com/company/source-robotics/"><img src="https://img.shields.io/badge/LinkedIn-Follow-blue?logo=linkedin" alt="LinkedIn"></a>
  <a href="https://x.com/SourceRobotics"><img src="https://img.shields.io/badge/X-Follow-black?logo=x" alt="X"></a>
  <a href="https://www.youtube.com/@source-robotics"><img src="https://img.shields.io/badge/YouTube-Subscribe-red?logo=youtube" alt="YouTube"></a>
</p>



<img src="Photos/MSG_banner.png" alt="drawing" width="1000"/>

## 📖 Project Overview
**MSG compliant AI stepper gripper** is a gripper based on [StepFOC stepper drivers](https://source-robotics.com/products/stepfoc-stepper-controller). It is a gripper capable of controlling its gripping force (We use FOC control on steppers), making it perfect for assembly tasks and human-robot collaboration AND AI training application because of its designed with cameras in mind! This gripper is modular in nature in 2 ways:
* Adjust grip length with different linear rails with options of 100mm,150mm and 200mm.
* Adjust grip strength with different stepper sizes, supporting steppers of lenght 21.5mm, 40mm and 60mm

Grip force can be adjusted allowing you to grasp a wide range of items; from delicate and soft to rigid and sturdy. 

Mechanical files and firmware are open source allowing you to add a custom griping tool and attach it to any robotic arm or robot. Gripper software is also open-source.

## ⚒️How to build / Where to buy?

You can buy MSG gripper on our website: https://source-robotics.com/products/msg-gripper

If you want to Source all the parts yourself and build your own follow these steps:

Print files from STEP files folder
* Example: For 100 mm rail style gripper
   - print everything from "common parts" folder
   - everything from "Linear rail dependant parts" folder -> "100mm rail" folder
   - everything from "Stepper dependant parts" folder depending on what stepper size you are using

* Source all the parts from the [BOM](https://github.com/PCrnjak/MSG-compliant-AI-stepper-gripper/blob/main/BOM.md)
* Follow [Assembly instructions *coming soon](https://github.com/PCrnjak/SSG-48-adaptive-electric-gripper/tree/main/Assembly%20manual) or [Video instructions](https://www.youtube.com/watch?v=127zXHKuqIg) to assemble your gripper
* Follow [DOCS](https://source-robotics.github.io/MSG-gripper-docs/) to get your gripper up and running.

## 📚Documentation:
- [Official website](https://source-robotics.com)
- [Python API](https://github.com/PCrnjak/Spectral-BLDC-Python/tree/main)
- [Building instructions *coming soon](https://github.com/PCrnjak/MSG-compliant-AI-stepper-gripper/tree/main/Building%20instructions)
- [BOM](https://github.com/PCrnjak/MSG-compliant-AI-stepper-gripper/blob/main/BOM.md)
- [DOCS](https://source-robotics.github.io/MSG-gripper-docs/)

## 💻Quick start code example

```python
import Spectral_BLDC as Spectral
import time

Communication1 = Spectral.CanCommunication(bustype='slcan', channel='COM20', bitrate=1000000)
Motor1 = Spectral.SpectralCAN(node_id=0, communication=Communication1)

Motor1.Send_Clear_Error()
Motor1.Send_gripper_calibrate()
time.sleep(4)

temp_var = 0
while True:
   if temp_var == 0:
      Motor1.Send_gripper_data_pack(50,100,700,1,1,0,0) 
      temp_var = 1
   elif temp_var == 1:
      Motor1.Send_gripper_data_pack(240,100,700,1,1,0,0) 
      temp_var = 0

   message, UnpackedMessageID = Communication1.receive_can_messages(timeout=0.2) 

   if message is not None:
      print(f"Message is: {message}")
      print(f"Node ID is : {UnpackedMessageID.node_id}")
      print(f"Message ID is: {UnpackedMessageID.command_id}")
      print(f"Error bit is: {UnpackedMessageID.error_bit}")
      print(f"Timestamp is: {message.timestamp}")

   time.sleep(3)
```

## 🌐 More about MSG gripper

| YouTube | Instagram | Twitter | LinkedIn |
|--------|-----------|---------|----------|
| [![YouTube](https://img.shields.io/badge/YouTube-FF0000?logo=youtube&logoColor=white)](https://www.youtube.com/@source-robotics) | [![Instagram](https://img.shields.io/badge/Instagram-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/source_robotics/) | [![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?logo=twitter&logoColor=white)](https://twitter.com/SourceRobotics) | [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/company/source-robotics) |


| Discord | Forum | Hackaday | Blog |
|--------|-------|------| ------|
| [![Discord](https://img.shields.io/badge/Discord-5865F2?logo=discord&logoColor=white)](https://discord.com/invite/prjUvjmGpZ) | [![Forum](https://img.shields.io/badge/Forum-0A0A0A)](https://discourse.source-robotics.com/) | [![Hackaday](https://img.shields.io/badge/Hackaday-000000?logo=hackaday&logoColor=white)](https://hackaday.io/project/191860-parol6-desktop-robotic-arm) | [![Blog](https://img.shields.io/badge/Blog-Source%20Robotics-blue)](https://source-robotics.com/blogs/blog) 


## ⚠️ Safety, Liability & Disclaimer
This project includes experimental software, hardware designs, and assembly documentation that are still under development and may contain bugs, errors, or incomplete features. By using, building, or modifying this project, you acknowledge that:

* You use this project entirely at your own risk
* You are solely responsible for safe assembly, testing, and operation
* No guarantee is made regarding correctness, safety, or reliability
* The authors are not responsible for any damage, injury, or loss resulting from the use or misuse of this project
* Hardware performance and safety depend on user assembly, component quality, calibration, and handling, which cannot be guaranteed
* This project is provided “as is.” If you choose to build a device yourself using these files, designs, or instructions, you do so without any warranties or guarantees, including regarding safety, reliability, or suitability for any particular purpose.

THIS PROJECT INVOLVES LETHAL VOLTAGES AND OTHER SERIOUS HAZARDS THAT CAN CAUSE SEVERE INJURY. YOU MUST READ THE FULL [SAFETY WARNING AND DISCLAIMER DOCUMENT](SAFETY_WARNING_AND_DISCLAIMER.md)  BEFORE USING ANY PROJECT FILES. BY PROCEEDING, YOU ACKNOWLEDGE AND ACCEPT ALL RISKS AND AGREE TO USE THIS PROJECT ENTIRELY AT YOUR OWN RESPONSIBILITY.

## 💸Support us

The majority of this project is open source and freely available to everyone. Your assistance, whether through donations or advice, is highly valued. Thank you!

 [![General badge](https://img.shields.io/badge/PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/PCrnjak?locale.x=en_US)
[![General badge](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://www.patreon.com/PCrnjak)

## 🛡️ Licensing
 Project is under [CERN Open Hardware Licence Version 2 - Strongly Reciprocal](https://github.com/PCrnjak/MSG-compliant-AI-stepper-gripper?tab=CERN-OHL-S-2.0-1-ov-file)
