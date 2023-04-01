# Robot-navigation-using-deep-learning

The code is available in TD3 folder.
The simulation environment is created using following dependencies:
 ``` 
  1. Ubuntu 20.04
  2. Ros Noetic
  3. Python 3.8.10
  4. Libraries Used:
   a. Pytorch 1.10
   b. Tensorboard
  ```
Instructions to create a simulation environment and complete the training process:
  1. Install Ubuntu 20.04 and Install Ros Noetic
  2. Copy and paste the necessary files attached to this assignment in any directory.
  3. Open terminal and RUN following commands:

    cd Folder_name/catkin_ws
    catkin_make_isolated
    
4. To run the neural network training in ROS, some variables first need to be exported and sourced. This can be done by executing the following lines in the terminal:
  ```
  export ROS_HOSTNAME=localhost
  export ROS_MASTER_URI=http://localhost:11311
  export ROS_PORT_SIM=11311
  export GAZEBO_RESOURCE_PATH = EEE598_Project/catkin_ws/catkin_ws/src/multi_robot_scenario/launch
  source ~/.bashrc
  cd Folder_name/catkin_ws
  source devel_isolated/setup.bash
```

(Note: These commands set up the sources in your terminal. Remember to run them, every time you open a new terminal window.)

5. Now, we can start the training by running following command in terminal: 
```
cd Folder_name/TD3
python3 train_velodyne_td3.py
  ```
6. We can see the Rviz is opened, and training process has been started and robot with laser equipped reads the environment and starts moving.

8. To see the 3D simulation of robot navigating training process in gazebo by running following command in another terminal:
```
  Run gzclient
  ```
8. We, can see the training process in Tensorboard by running following commands in terminal:
```
  cd Folder_name/TD3
  tensorboard --logdir runs
  ```
  After running following commands, hold CTRL and simply click on <http://localhost:6006/> and the page will open automatically.
9. After completing the training, to test the network:

  Run python3 test_velodyne_TD3
10. To stop training, Press CTRL + C in a terminal where training started and run following command to kill all the running processes:
```
  killall -9 rosout roslaunch rosmaster gzserver nodelet robot_state_publisher gzclient python python3
  ```
11. Install any additional Python dependencies to run training process by installing pip3:
```
  Run sudo apt install python3-pip
  Run pip3 install <python_package_name>```
  
