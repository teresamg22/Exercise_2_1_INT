# Exercise_2_1_INT
Exercise 2.1 Integration for Master on Robotics UVIC

**6. What are the arguments of usb_cam-test.launch?**

If we open the launch file, we can see that there aren’t any arguments. 

```
<launch>
  <node name="usb_cam" pkg="usb_cam" type="usb_cam_node" output="screen" >
    <param name="video_device" value="/dev/video0" />
    <param name="image_width" value="640" />
    <param name="image_height" value="480" />
    <param name="pixel_format" value="yuyv" />
    <param name="camera_frame_id" value="usb_cam" />
    <param name="io_method" value="mmap"/>
  </node>
  <node name="image_view" pkg="image_view" type="image_view" respawn="false" output="screen">
    <remap from="image" to="/usb_cam/image_raw"/>
    <param name="autosize" value="true" />
  </node>
</launch>
```

Also if we apply the command: 

```
 roslaunch usb_cam usb_cam-test.launch --ros-args
```

It also appears that this file doesn’t have any argument.  
