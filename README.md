# ROS-Driver for Roboteq

# Introduction

**Note from Zharif:**
This repository is a modified version of Doan's where I used it for a Roboteq SBL2360T driver with a differential mobile robot configuration. I just changed some configuration, parameters and will provide extra walkthrough for newcomers (and future me) to understand the driver. Additional notes will be added from time to time especially guides and further explaination on the queries and how to use the driver. 

**Credit**
Full credit to Roboteq for creating this driver and Doan Nguyen for major improvement that he did for the driver. It was really helpful and I can't thank him enough for the amazing contribution. Thank you Doan Nguyen.

# Installation Guide
```bash
cd catkin_ws/src/
git clone https://github.com/DoanNguyenTrong/roboteq_controller_ros.git
cd catkin_ws
catkin build roboteq_controller
source devel/setup.bash
roslaunch roboteq_controller driver.launch
```
