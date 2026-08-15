# xgc2-camera-d435

Shared D435 / D435i camera product. Any robot that mounts this camera
uses this repository. Vehicle repos only include the launch.

| Package | Role |
| --- | --- |
| `realsense2_camera` | Intel ROS 1 capture driver |
| `realsense2_description` | Camera URDF / meshes |
| `xgc_camera_d435` | XGC2 defaults: 1280×720 color, 848×480 depth |

```bash
roslaunch xgc_camera_d435 d435.launch
roslaunch xgc_camera_d435 d435i.launch
```

| Stream | Topic | Default |
| --- | --- | --- |
| color | `/camera/color/image_raw` | 1280×720 @ 30 |
| depth | `/camera/depth/image_rect_raw` | 848×480 @ 30 |
| infra1 | `/camera/infra1/image_rect_raw` | off |

Needs `librealsense2` on the host (on Xavier it is `/usr/local/lib`).
