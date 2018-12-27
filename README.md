# QuadControl_fh
The following 3 files are modified for Project 3: Control of a 3D Quadrotor.
* src/QuadControl.cpp
* src/QuadControl.h
* config/QuadControlParams.txt

It passed all test cases in scenarios 2, 3, 4, and 5. A green box appears on each test case. A video, 3D_hub Control_Quadcopter.gif, is recorded about these scenarios and uploaded to this github repo.

## Scenario 2
GenerateMotorCommands(), BodyRateControl(), and RollPitchControl() are developed for this. It took me some amount of work to figure out the right equations in GenerateMotorCommands(). In this project, we use x-axis as airplane body and y-axis as wings of an airplane. Positive x points to forward moving direction. In out video lectures, we use the other way in examples. Also which directions are positive angles for roll, pitch, and yaw. When the equations in GenerateMotorCommands() for four forces were not correct for this project, the quadcopter crashed in scenario 2 or 3.

