# Setup Simulation for a drone

Here we will set up a simulation to simulate a drone that we can in turn send mavlink commands to control, 
based on the ardupilot documentation: https://ardupilot.org/dev/docs/simulation-2.html

We will install a Software in the loop(SITL) programm that runs the ArdiPilot firmware and sends the servo and motor outputs to the simulation,
and the simulator Gazebo that receives the inputs from the SITL and 
