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


Designate the arm to be assessed and the subject posture, and then select the appropriate folder. The following folders are of interest:
1. **spring_graphic**: loads a spring with fixed position haptic feedback VR target.
2. **spring_damper** : loads a spring and damper system with sinusoidal oscillating haptic feedback VR target
3. **hill_model**: loads a hill-model with the handle acting as the end of a muscle and sinusoidal oscillating haptic feedback VR target.
4. **torque_model** loads a hill-model on a limb with handle acting as the end of a limb with a muscle creating a torque about a joint
5. **torque_reflex** loads an augmented version of (4), with short-range stiffness, activation conditions, and added passive stiffness parameters available.

For the spasticity emulator, this will be the “torque_reflex” folder {4}. Under the folder, trial protocols will appear, such as “eccentric”, “concentric” and “spastic”. To run the spasticity emulator, choose the “spasticity” trial protocol. Once selected, you can edit the parameters of the trial protocol by clicking the paper and pencil icon, which opens up a new window with the target table, load table etc. {5}.  

![Edit Trial Protocol](./Tutorial/TP.PNG)

Before you run a trial, calibrate the robots by pressing the "calibrate" button. Use the interface to reset the zero value of the force sensors in the handle.
To run a trial, press the play icon underneath “Run” and the KinArm will begin to execute the trial protocol. 

Move the handle to the left-hand side of the display, and let the robot guide the handle to appropriate shank lengths. Once the shanks are at a stable length, you can rotate the handle in the left-hand half of the plane. 

**add figure here and explanation of a trial**

The torque_reflex trial is structured to involve a static hold followed by user defined sinusoids. A target will appear at the top of the display and after 2 seconds of holding the handle inside the target, it will begin to move in an arc about hte left hand side of the display. The trial will end after a set amount of time, defined by the "Trial Exit" parameter on the TP table in the Dexterit-E Task Protocol. 


Once you are done with the trial, let go of the handle and return to the computer. Press the STOP button on the display. 

The trial data can be viewed by opening Dexterit-E explorer (white letter K icon, underneath Dexterit-E) on the monitor. 
![Dexterit-E Interface](./Tutorial/Dex_Explore_censored.PNG)

Trials are sorted by subject. When you click on a subject’s name, trials will appear. Find the desired trial based on the appropriate date and time. Before you export the data for your own analysis, you can use Dexterit-E explorer to preview the data. You can select signals and trial events to view and use the scroll bar or play button to move along the time of the trial. This is a good step to quickly make sure your program is working properly. 

By right clicking on the desired trial, you can choose to export the file as a csv. Since the computer is not connected to the internet, you must plug in a USB thumb-drive into the KinArm computer (see above the leftmost circle in Fig. 1). Export the file to the thumb-drive and transfer it to your local computer to analyze the data in the manner of your choosing. 

