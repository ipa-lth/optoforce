This document describes how to start the driver of the [OptoForce OMD-45-FE-1000N FT](http://optoforce.com/3dsensor/) sensor.

 1. Clone the repository in your catkin workspace:

	```
	$ cd ~/catkin_ws/src
	$ clone git@github.com:shadow-robot/optoforce.git
	```
 2. Add yourself to the group *dialout* in order to get access the serial port `$sudo usermode -a -G dialout $USER`. You need to log-out/log-in to apply the changes. :
 
 3. Launch the driver:
	
	```
	$ roslaunch optoforce optoforce.launch type:=s-ch/3-axis scaling_file:='$(find optoforce)/config/single_channel_3_axis_generic_scale.yaml'
	```
 4. The messages are published on the topic */optoforce_0*. To display these messages execute the command `$ rostopic echo /optoforce_0`
 
 **Note**: 
	 The flash memory stick that comes with the sensor contains a linux application to visualize the data measured by the sensor: `DAQ material/USB/ODV/ODV_3D/LINUX/ODV3D_v1.6.6.tar.gz`. Unpack and run the application. The driver and the *OptoForce Data Visualization Software* can not be run on the same time because they use the same port.
