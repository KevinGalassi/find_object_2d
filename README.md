## find-object (standalone) 

## find_object_2d (ROS package)

### Install

Binaries:
```bash
# ROS Kinetic:
 $ sudo apt-get install ros-kinetic-find-object-2d
```

Source:

 * If you want SURF/SIFT on Indigo/Jade/Kinetic (Hydro has already SIFT/SURF), you have to build [OpenCV](http://opencv.org/) from source to have access to *nonfree* module. Install it in `/usr/local` (default) and the Find-Object should link with it instead of the one installed in ROS.

     * On Kinetic, I recommend to use OpenCV3+[xfeatures2d](https://github.com/Itseez/opencv_contrib/tree/master/modules/xfeatures2d) module (*to confirm* OpenCV3 installed with ROS already includes SIFT/SURF, so no need to rebuild OpenCV). You can also install OpenCV2, but find_object_2d package will have libraries conflict as cv-bridge is depending on OpenCV3. Thus if you want OpenCV2 on Kinetic, you should build ros [vision-opencv](https://github.com/ros-perception/vision_opencv) package yourself (and all ros packages depending on it) so it can link on OpenCV2.




### Run
```bash
 $ roscore 
 $ rosrun usb_cam usb_cam
```

In another terminale

```
$ ssh -Y lar-UR5 -l lar
$ export ROS_MASTER_URI=http://192.168.7.95:11311
$ rosrun find_object_2d find_object_2d image:=/usb_cam/image_raw
```


