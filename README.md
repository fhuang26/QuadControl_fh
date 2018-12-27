# QuadControl_fh
The following 3 files are modified for Project 3: Control of a 3D Quadrotor, in FCND-Controls-CPP.
* src/QuadControl.cpp
* src/QuadControl.h
* config/QuadControlParams.txt

It passed all test cases in scenarios 2, 3, 4, and 5. A green box appears on each test case. A video, 3D_Control_Quadcopter.gif, is recorded about these scenarios and uploaded to this github repo.

## Scenario 2
GenerateMotorCommands(), BodyRateControl(), and RollPitchControl() are developed for this. It took me some amount of work to figure out the right equations in GenerateMotorCommands(). In this project, we use x-axis as airplane body and y-axis as wings of an airplane. Positive x points to forward moving direction. In the video lectures, we use the other way in examples. Also which directions are positive angles for roll, pitch, and yaw. When the equations in GenerateMotorCommands() for four forces were not correct for this project, the quadcopter crashed in scenario 2 or 3.

## Scenario 3
LateralPositionControl(), AltitudeControl(), YawControl() are developed and a bunch of parameters are tuned for this.

## Scenario 4
This one is somewhat challenging. Integration is added to AltitudeControl() to save the right, red, heavier quadcopter from crash. To make them move fast, then slow down nicely and hover on top of their targets, I made tradeoffs among P (present), I (past), D (future), and a bunch of parameters. Finally I saw the green box appear.

## Scenario 5
This one is also a little tricky. In early runs, the left, orange drone took off, half way turned sharply, and crashed. I traced steps in debugger of Microsoft Visual Studio, but it was hard to find the point or function it went wrong. Then I began to try various parameters. When I decrease maxSpeedXY and maxHorizAccel to reduce the chance of abrupt turns, it works. The left, orange quadcopter flies smoothly following the orange moving marble in figure 8 closely within 0.5m. The right, red quadcopter flies and keeps distance within 1.5m from its moving target.
