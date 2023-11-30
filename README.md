# Spasticity-Emulator
Tutorials and code for Operating KinArm Spasticity Emulator
- force_curves.mat : loads Hill Model as 3 separate variables, each of which is a [nx2] matrix with length or velocity and force. For use in post-processing

- {flp.dat, fla.dat, fv.dat, srs.dat} matrices from force_curves converted into 1-D little-endian binary vectors for use in Simulink model as a lookup table. Tutorial on how to convert a 2D matrix into a compatible vector can be found within torque_reflex.slx


- torque_reflex.slx: Simulink model of limb and muscle mechanics. Can be edited to add parameters 
	- requires Dexterit-E task development library installed on MATLAB to edit. This can be done in the lab on the monitor in the KinArm room, or on the laptop. To run the file on the KinArm, use ctrl+B to BUILD the file into a .mldatx. the mldatx build can be put into a folder on the KinArm laptop and run from Dexterit-E.

- demo_script.m : Sample processing script, demonstrating how to load and visualize trial data

