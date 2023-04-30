# Udacity Control and Trajectory Tracking for Autonomous Vehicle

### The code and results
Find the results graphs and videos in folder images above with some fail trials videos as I am trying to tune the pid to have final 2 accepted but no good trials.

Find the code used exists separtly as named main.cpp , pid_controller.cpp and pid_controller.h. 
it is possible to take those codes content to copy in Udacity workspace instead of exist codes and run
or follow installation method to have same results.

### Installation

Run the following commands to install the starter code in the Udacity Workspace:

Clone the <a href="https://github.com/Shenhapy/Udacity_Control-and-Trajectory-Tracking_project.git" target="_blank">repository</a>:

`git clone https://github.com/Shenhapy/Udacity_Control-and-Trajectory-Tracking_project.git`

## Run Carla Simulator

Open new window

* `su - student`
// Will say permission denied, ignore and continue
* `cd /opt/carla-simulator/`
* `SDL_VIDEODRIVER=offscreen ./CarlaUE4.sh -opengl`

## Compile and Run the Controller

Open new window

* `cd Udacity_Control-and-Trajectory-Tracking_project/project`
* `./install-ubuntu.sh`
* `cd pid_controller/`
* `rm -rf rpclib`
* `git clone https://github.com/rpclib/rpclib.git`
* `cmake .`
* `make` (This last command compiles your c++ code, run it after every change in your code)

## Testing

To test your installation run the following commands.

* `cd Udacity_Control-and-Trajectory-Tracking_project/project`
* `./run_main_pid.sh`
This will silently fail `ctrl + C` to stop
* `./run_main_pid.sh` (again)
Go to desktop mode to see CARLA

If error bind is already in use, or address already being used

* `ps -aux | grep carla`
* `kill id`


## The Project

I build the steer and throttle controller so that the car follows the trajectory.

In the directory [/pid_controller](https://github.com/udacity/nd013-c6-control-starter/tree/master/project/pid_controller)  you will find the files [pid_controller.cpp](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/pid_controller.cpp)  and [pid_controller.h](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/pid_controller.h). This is where you will code your pid controller.
The function pid is called in [main.cpp](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/main.cpp).

### Step 1: Build the PID controller object
Complete the TODO in the [pid_controller.h](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/pid_controller.h) and [pid_controller.cpp](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/pid_controller.cpp).

Run the simulator and see in the desktop mode the car in the CARLA simulator. Take a screenshot and add it to your report. The car should not move in the simulation.
To find this result shown in image below and the car not moving
<img src='images/cntrl1.png'/>

### Step 2: PID controller for throttle and steer:
In [main.cpp](https://github.com/udacity/nd013-c6-control-starter/blob/master/project/pid_controller/main.cpp)
The code is Comment and I Tune the parameters of the pid as possible.

Find the result video in folder images with some other videos for tunning trials in folder bad and trio crash
### Step 3: Evaluate the PID efficiency
Finally the evaluation of the results
<img src='a1/cntrl1.png'/>
<img src='a2/cntrl1.png'/>

Answer the following questions:
- Add the plots to your report and explain them (describe what you see)
- What is the effect of the PID according to the plots, how each part of the PID affects the control command?
- How would you design a way to automatically tune the PID parameters?
- PID controller is a model free controller, i.e. it does not use a model of the car. Could you explain the pros and cons of this type of controller?
- (Optional) What would you do to improve the PID controller?


### Tips:

- When you wil be testing your c++ code, restart the Carla simulator to remove the former car from the simulation.
- If the simulation freezes on the desktop mode but is still running on the terminal, close the desktop and restart it.
- When you will be tuning the PID parameters, try between those values:

