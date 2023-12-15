# Spasticity-Emulator
Tutorials and code for Operating KinArm Spasticity Emulator. 

This project aims to develop a robotic emulator of spasticity based on physiological mechanisms. [Spasticity](https://www.pennmedicine.org/for-patients-and-visitors/patient-information/conditions-treated-a-to-z/spasticity#:~:text=Definition,other%20activities%20of%20daily%20living.) is a motor disorder characterized by increased muscle tone and exaggerated muscle activation in response to passive stretching, affecting patients with conditions such as cerebral palsy and stroke. 

Clinical evaluations of spasticity include the [Modified Ashworth Scale](https://www.ncbi.nlm.nih.gov/books/NBK554572/), the [Modified Tardieu Scale](https://www.physio-pedia.com/Tardieu_Scale), amongst others. These evaluations of spasticity involve manual movement of a patient's limb at different speeds to differentiate between levels of muscle resistance. However, such methods are limited by subjective grading of both speed and muscle resistance. Moreover, manual evaluations, as well as other [quantitative methods](https://pubmed.ncbi.nlm.nih.gov/23994052/) of evaluating spasticity fail to elucidate the mechanisms underlying the disorder. 

Fortunately, [recent computational models](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0208811) show that increased muscle short-range stiffness coupled with a short-latency reflex based on force feedback can mechanistically reproduce quantitative measurements of spasticity. However, it is not clear whether these mechanisms reproduce that resistance felt by the clinician. Such models appear valid in simulation, but have not been validated physically. Implementing computational models on a physical robot could help bridge that gap.

Thus, we have here built a code repository to simulate a spastic limb on the KinArm Endpoint Robot platform. 

##  IN THIS REPOSITORY: 
 1. [KinArm Tutorial](https://github.com/Neuromechanics-Lab/Spasticity-Emulator/blob/main/KinArm%20Tutorial.md):  Written instructions with visuals for using the KinArm in lab. Use this file to operate the KinArm and collect your data
 2.  **Data Processing Tutorial** : Once you have collected data, use this document as a reference for processing your data.
 If you have access to the Neuromechanics Lab Repository, you can click this link and log into your github account [![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=Neuromechanics-Lab/Spasticity-Emulator&file=kinarm_tutorial.mlx){:target="_blank"}

If you do not have access, you cannot use the Live Editor but can instead open this [HTML file](https://htmlpreview.github.io/?https://github.com/Neuromechanics-Lab/Spasticity-Emulator/blob/main/kinarm_tutorial.html).

 

## OTHER FILES
- **force_curves.mat**: loads Hill Model as 3 separate variables, each of which is a [nx2] matrix with length or velocity and force. For use in post-processing

- **{flp.dat, fla.dat, fv.dat, srs.dat}**: matrices from force_curves converted into 1-D little-endian binary vectors for use in Simulink model as a lookup table. Tutorial on how to convert a 2D matrix into a compatible vector can be found within torque_reflex.slx. These files are already uploaded to the build folder on the KinArm computer, you do not need them locally. 

- **torque_reflex.slx**: Simulink model of limb and muscle mechanics. Can be edited to add, remove or modify model parameters. 
	- requires Dexterit-E task development library installed on MATLAB to edit. This can be done in the lab on the monitor in the KinArm room, or on the laptop. To run the file on the KinArm, use ctrl+B to BUILD the file into a .mldatx. This build can be put into the Dexterit-E custom tasks folder on the KinArm computer and run from Dexterit-E.
	- Do NOT change the .mldatx file name or you will get an error and not be able to use the build.
 	- The Simulink build essentially creates the abstraction for your task. i.e, it creates the folder that can have task protocols (.dtp files) populating it. You will need to add create individual task protocols to actually run a trial, but these task protocols will be defined through the set of variables and parameters you created in the Simulink build.



