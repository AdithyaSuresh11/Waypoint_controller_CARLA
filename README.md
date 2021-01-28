# Lane-Keeping-Assist-on-CARLA
## Introduction
<p align="center">
  <img  src="controller_output/CARLA.png">
</p>

This is an assignment from [Introduction to Self-Driving Cars](https://www.coursera.org/learn/intro-self-driving-cars) course of [Self-Driving Cars Specialization](https://www.coursera.org/specializations/self-driving-cars?) on Coursera.org.

This assignment implements Lane Keeping Assist function by applying pure pursuit and Stanley methods for lateral control and PID controller for longitudinal control using Python as the programming language.

The waypoints and corresponding velocities for the track are pre-defined.

To realize this function, the open sourse simulator [CARLA](http://carla.org) is introduced.

## Prerequisites
First CARLA must be installed on your machine, the CARLA loader requires **Ubuntu 16.04 or later** to run

Please go through **CARLA-Setup-Guide-_Ubuntu_.pdf** and install CARLA and all other dependencies properly.

## How to run it
First clone this repository and put it under **PythonClient** directory.

### 1. Load the simulator
Open a terminal and do `cd ~/opt/CarlaSimulator`.

Then do `./CarlaUE4.sh /Game/Maps/RaceTrack -windowed -carla-server -benchmark -quality-level=Low -fps=30
`
### 2. Run the LKA controller
Open another terminal and do `cd ~/opt/CarlaSimulator/PythonClient/Lane-Keeping-Assist-on-CARLA`.

(optional) do `sudo apt-get install python3-tk` in case you do not have `Tkinter` module.

Run `python3 module_7.py` to execute the controller(default is MPC control method)

To select 3 different control methods:

MPC - `python3 module_7.py --control-method MPC`

Stanley - `python3 module_7.py --control-method Stanley`

Pure Pursuit - `python3 module_7.py --control-method PurePursuit`

The vehicle should starting driving and following the track.

## Simulation results
The images shown below is the result of vehicle trajectory(MPC, Stanley and Pure Pursuit method).

The green line is the track(ground truth) and the orange line is the trajectory.

<p align="center"><b>MPC Method</b></p>
<p align="center">
  <img  src="controller_output/trajectory_MPC.png">
</p>

<p align="center"><b>Stanley Method</b></p>
<p align="center">
  <img  src="controller_output/trajectory_Stanley.png">
</p>

<p align="center"><b>Pure Pursuit Method</b></p>
<p align="center">
  <img  src="controller_output/trajectory_PurePursuit.png">
</p>


