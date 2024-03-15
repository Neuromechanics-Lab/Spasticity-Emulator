KinArm Tutorial
Rauf Iftikhar
28 November 2023

Simulink code and MATLAB processing scripts can be found on the lab github under the repository “Spasticity Emulator.” 

The KinArm is located in the ERH basement in room RG20. The machine can be turned on by pressing the 3 power buttons indicated below in any order. 

![KinArm Power Buttons](./Tutorial/kinarm_computers.jpg)

Once the computers and robot are turned on, the monitor attached to the KinArm will turn on. 

From the desktop, select the Dexterit-E app. 
![KinArm Monitor](./Tutorial/desktop.png)


From the interface, select a user {1} (e.g., Nathan Baune, Rauf Iftikhar, Lena Ting etc.) and a subject {2}(e.g. John Doe, Random Participant etc.). Select the custom tasks tab {3}. 

![Dexterit-E Interface](./Tutorial/dext_censored.PNG)


Designate the arm to be assessed and the subject posture, and then select the appropriate folder. The desired folder is **spasticity_model**. This folder contains several different task protocols that can be used to quickly load desired parameters. These are the task protocols currently available: 
1. **Concentric**: Loads a model where muscle activation is 0.75 when muscle is shortening and 0 when the muscle is still or lengthening.
2. **Constant**: Loads a model where muscle activation is always 0.75. All other parameters are inactive.
3. **Eccentric**: Loads a model where muscle activation is 0.75 when muscle is lengthening and 0 when muscle is still or shortening. All other parameters are inactive.
4. **SRS** Loads a model with eccentric muscle activation control and added short-range stiffness (k=10). Velocity-based reflex and added spring stiffness are inactive. 
5. **Spasticity**: Loads a model with all parameters active. These include short-range stiffness (k = 10), added passive stiffness spring (k = 8), and velocity-dependent reflex (k=15). 
loads an augmented version of (4), with short-range stiffness, activation conditions, and added passive stiffness parameters available.

To edit a trial protocol, select the protocol and click the paper and pencil icon.

![Edit Trial Protocol](./Tutorial/TP.PNG)

Before you run a trial, calibrate the robots by pressing the "calibrate" button. Use the interface to reset the zero value of the force sensors in the handle.
To run a trial, press the play icon underneath “Run” and the KinArm will begin to execute the trial protocol. 

Move the handle to the left-hand side of the display, and let the robot guide the handle to appropriate shank lengths. Once the shanks are at a stable length, you can rotate the handle in the left-hand half of the plane. 

![githubmovie](https://github.com/Neuromechanics-Lab/Spasticity-Emulator/assets/65513023/295b39bb-a9f2-4f23-9860-9961f187548e)

As you can see in the gif, the handle position may cause the L2 shank to be the wrong length initially, but it will guide the handle to the correct position once the handle is grasped. 

The torque_reflex trial is structured to involve a static hold followed by user defined sinusoids. A target will appear at the top of the display and after 2 seconds of holding the handle inside the target, it will begin to move in an arc about hte left hand side of the display. The trial will end after a set amount of time, defined by the "Trial Exit" parameter on the TP table in the Dexterit-E Task Protocol. 


Once you are done with the trial, let go of the handle and return to the computer. Press the STOP button on the display. 

The trial data can be viewed by opening Dexterit-E explorer (white letter K icon, underneath Dexterit-E) on the monitor. 
![Dexterit-E Interface](./Tutorial/Dex_Explore_censored.PNG)

Trials are sorted by subject. When you click on a subject’s name, trials will appear. Find the desired trial based on the appropriate date and time. Before you export the data for your own analysis, you can use Dexterit-E explorer to preview the data. You can select signals and trial events to view and use the scroll bar or play button to move along the time of the trial. This is a good step to quickly make sure your program is working properly. 

By right clicking on the desired trial, you can choose to export the file as a csv. Since the computer is not connected to the internet, you must plug in a USB thumb-drive into the KinArm computer (see above the leftmost circle in Fig. 1). Export the file to the thumb-drive and transfer it to your local computer to analyze the data in the manner of your choosing. 

