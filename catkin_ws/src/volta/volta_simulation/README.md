# Volta
ROS packages used to run the Volta in simulation

* volta_simulation - Gazebo simulation world file.

## Steps to Launch Volta:

### 1. Launching a Gazebo Simulation environment
 * To bring up a gazebo world, launch the gazebo node by running:  
```
$ roslaunch volta_simulation gazebo.launch 
```
 * Once the gazebo simulation environment is launched, run the following to spawn the Volta robot:  
 ```
$ roslaunch volta_simulation simulation.launch 
```
 * For visualization, launch rviz by running:        
 ```
 $ rosrun rviz rviz
```
   The configuration file, volta.rviz which is located under volta_description->rviz_params, can be opened in the rviz tool to load the volta configured rviz environment

 * In order to start the teleoperation node using keyboard, run the following:  :        
 ```
 $ roslaunch volta_teleoperator volta_teleoperator.launch keyboard:=true 
```
 * To launch the joystick node, set the keyboard argument to False (Default case:= false) or run the following:       
 ```
 $ roslaunch volta_teleoperator volta_teleoperator.launch  
```
   
   
### 2. Mapping an environment with Volta
 * Once the gazebo world is launched and the Volta robot is spawned into the simulation environment, the mapping node can be launched by running:   
```
$ roslaunch volta_navigation navigation.launch gmapping:=true  
```

 * This will launch the gmapping node. On a separate terminal, launch the rviz visualization tool by running:   
```
$ rosrun rviz rviz  
```
You can then open the volta configured rviz environment by opening the volta rviz config file, located under volta_navigation->rviz_config->navigation.rviz, from the rviz tool 
 
 * In order to control the robot, launch the teleoperation node by running:     
```
$ roslaunch volta_teleoperator teleoperator.launch keyboard:=true 
```
    
 * Once the mapping of the entire environment is completed, the map can be saved by running:     
```
$ roslaunch map_server map_saver –f <filename>
```
   
### 3. Navigation with Volta
 * Once the gazebo world is launched and the Volta robot is spawned into the simulation environment, the navigaation node can be launched by running:   
```
$ roslaunch volta_navigation navigation.launch 
```

 * This will launch the navigation node. On a separate terminal, launch the rviz visualization tool by running:   
```
$ rosrun rviz rviz  
```
You can then open the volta configured rviz environment by opening the volta rviz config file, located under volta_navigation->rviz_config->navigation.rviz, from the rviz tool 
 
Use the 2D Nav Goal tool in the top toolbar to select a navigation goal in the visualizer. Ensure that the nav goal is given in a mapped section of the map 
