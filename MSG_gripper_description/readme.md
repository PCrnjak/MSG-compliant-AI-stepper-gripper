
# Source Robotics MSG gripper Description (MJCF) & URDF

> [!IMPORTANT]
> Requires MuJoCo 3.1.3 or later.

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for a full history of changes.


## Overview

This package contains a simplified robot description (MJCF) and URDF files of the [MSG gripper](https://source-robotics.com/products/msg-gripper) developed by [Source Robotics](https://source-robotics.com/).

There are 2 available MJCF files.


## Online mujoco viewer

https://mujoco-viewer.org/


## URDF folder

[URDF](./URDF/) folder contains:
* MSG gripper


More about URDF here: [Link](./urdf.md)

## URDF → MJCF derivation steps

1. Loaded the URDF into MuJoCo and saved a corresponding MJCF.
2. Manually edited the MJCF to extract common properties into the `<default>` section.
3. Added position-controlled actuators for the arm.
4. Added `scene.xml` which includes the robot, with a textured groundplane, skybox, and haze.

## License

This model is released under an [Apache-2.0 License](LICENSE).


## References

Mjcf reference Mujoco managerie
- references: 
- https://mujoco.readthedocs.io/en/stable/XMLreference.html
- https://github.com/google-deepmind/mujoco_menagerie/tree/main/ufactory_lite6
- https://github.com/google-deepmind/mujoco_menagerie/blob/main/trossen_vx300s/vx300s.xml 
- https://github.com/google-deepmind/mujoco_menagerie/blob/main/aloha/aloha.xml
- https://github.com/google-deepmind/mujoco_menagerie/blob/main/franka_emika_panda/panda.xml 
- https://github.com/jeongeun980906/lerobot-mujoco-tutorial/blob/master/asset/robotis_omy/omy.xml 