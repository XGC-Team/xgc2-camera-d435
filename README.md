# xgc2-camera-d435

XGC2 D435 / D435i assembly. This is a child of
[`xgc2-camera-driver`](https://github.com/XGC-Team/xgc2-camera-driver) and of
the [`xgc2-camera`](https://github.com/XGC-Team/xgc2-camera) camera product.

Capture is still `realsense2_camera` (Intel). This package owns the XGC2
topic/layout contract:

| Stream | Topic | Size |
| --- | --- | --- |
| color | `/camera/color/image_raw` | 640×480 |
| depth | `/camera/depth/image_rect_raw` | 848×480 |
| infra1 | `/camera/infra1/image_rect_raw` | off unless `enable_infra1:=true` |

```bash
roslaunch xgc_camera_d435 d435.launch
roslaunch xgc_camera_d435 d435i.launch
```

Media Edge source roster: `config/sources.json`. Encode with the shared
`ros_image_rtp_adapter`, not a vehicle-local RTP fork.

Vehicle products (Scout, lab PC) only include this launch. They do not vendor
another RealSense tree.
