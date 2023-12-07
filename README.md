# Spasticity-Emulator
Tutorials and code for Operating KinArm Spasticity Emulator **ADD FURTHER DESCRIPTION and hyperlinks **


 1. START HERE: **KinArm Tutorial.md**: Written instructions with visuals for using the KinArm in lab. Use this file to operate the KinArm and collect your data
 2.  **demo** : Once you have collected data, use this document as a reference for processing your data.
 Folder with sample matlab code and instructions demonstrating how to process and analyze trial data. To view the demo, download the entire folder and open the demo_script.html file on your browser. 

## OTHER FILES
- **force_curves.mat**: loads Hill Model as 3 separate variables, each of which is a [nx2] matrix with length or velocity and force. For use in post-processing

- **{flp.dat, fla.dat, fv.dat, srs.dat}**: matrices from force_curves converted into 1-D little-endian binary vectors for use in Simulink model as a lookup table. Tutorial on how to convert a 2D matrix into a compatible vector can be found within torque_reflex.slx. These files are already uploaded to the build folder on the KinArm computer, you do not need them locally. 

- **torque_reflex.slx**: Simulink model of limb and muscle mechanics. Can be edited to add, remove or modify model parameters. 
	- requires Dexterit-E task development library installed on MATLAB to edit. This can be done in the lab on the monitor in the KinArm room, or on the laptop. To run the file on the KinArm, use ctrl+B to BUILD the file into a .mldatx. This build can be put into the Dexterit-E custom tasks folder on the KinArm computer and run from Dexterit-E.
	- Do NOT change the .mldatx file name or you will get an error and not be able to use the build.
 	- The Simulink build essentially creates the abstraction for your task. i.e, it creates the folder that can have task protocols (.dtp files) populating it. You will need to add create individual task protocols to actually run a trial, but these task protocols will be defined through the set of variables and parameters you created in the Simulink build.



