# ROS-Driver for Roboteq

# Introduction

**Note from Roboteq**
```
 -This ROS driver only supports firmware version 2.0 or 2.0+. 
 -You can check your firmware version from Roborun+ console tab by querying - "?fid". 
 -If firmware is not the latest one then please update it with the latest one available on Roboteq website 
  or contact "techsupport.roboteq@mail.nidec.com".
```
This repository contains the ROS driver for Roboteq controllers. The package requires ROS system to be installed properly to your system  and proper connection of Roboteq controller. For detailed controller setup instructions, please refer to our documentation.

The roboteq driver is designed to be dynamic and users can publish the controller queries as per their requirements. The publishing queries is not limited to any value. By default total 9 queries are published by launching this driver. Users can change or add queries in configuration file. For that go to config/query.yaml

**Note from Doan Nguyen:**
- It originally worked at a fixed rate of 5 Hz while querying system's states. I did **major** mofifications in this work, making it work at a frequency you want to.
- They did also specified 3 separate query frequencies in [the config file](config/query.yaml): `frequencyH`, `frequencyL`, and `frequencyG`. However, it's not the case (or quite complicated). Here in this work, I cleaned all of it and only keep a default `frequency` for all queries. It's sufficient for me, and hopefully for you too.
- I only used the `driver.launch` for now. So `diff_odom` is kept as original. Later, I might make it works, but probably by modifying the `roboteq_controller_node`, not putting in a separated file to make it a little bit efficent. This package is tested on XDC2460. In general, it uses serial communication so feel free to test it on your roboteq device. Please let me know it you do so, whether it works, any issues. Thank you.

**Credit**
Full credit to Roboteq for creating this driver and Doan Nguyen for major improvement that he did for the driver. It was really helpful and I can't thank him enough for the amazing contribution. Thank you Doan Nguyen.

**Note from Zharif**
This repository is a modified version of Doan's where I used it for a Roboteq SBL2360T driver with a differential mobile robot configuration. I just changed some configuration, parameters and will provide extra walkthrough for newcomers (and future me) to understand the driver. Additional notes will be added from time to time especially guides and further explaination on the queries and how to use the driver. 

# Installation Guide
```bash
cd catkin_ws/src/
git clone https://github.com/DoanNguyenTrong/roboteq_controller_ros.git
cd catkin_ws
catkin build roboteq_controller
source devel/setup.bash
roslaunch roboteq_controller driver.launch
```
