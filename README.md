# Transitions_Conditions_States
This is simply about applying Transitions, Conditions and States in a Stateflow chart(Automation)

I will start to build that model, beginning with the Off and Seeking states.

## Step 1
start to build that model, beginning with the Off and Seeking states
<img width="558" height="320" alt="Task1" src="https://github.com/user-attachments/assets/da23677b-fd2c-4bcb-801b-e239687fe0fb" />

## Step 2
Without a transition condition, Stateflow switches states at every simulation time step.
For this task two input signals that simulate object trackers have been connected to the Chart block. The values of these signals become Stateflow data.
These data, Power and objectFound, can each have a value of 0 or 1. They represent whether the power button is pressed and whether an object has been detected.
Now, add the transition condition Power == 1 to the transition from Off to Seeking and add the transition condition Power == 0 to the transition from Seeking to Off.

<img width="500" height="221" alt="Task2" src="https://github.com/user-attachments/assets/a1d3fcb6-412b-488e-afad-4464ddb7b551" />

## Step 3
Add a new state to the model and name it Tracking. Add transitions from Seeking to Tracking and from Tracking to Seeking.

<img width="517" height="307" alt="Task3" src="https://github.com/user-attachments/assets/c671c961-7342-4221-b94e-31c15fbaa23e" />

## Step 4 
The data objectFound represents whether an object has been detected. The chart moves from Seeking to Tracking when objectFound equals 1 and from Tracking back to Seeking when objectFound is 0.
Add the transition conditions that guard the transitions between the Seeking and Tracking states.

<img width="539" height="290" alt="Task4" src="https://github.com/user-attachments/assets/d3a3f8d2-7ea9-4636-b182-9778c5260e4d" />

## Step 5
This machine should also turn off from the Tracking state if the power is turned off. Hence, add a transition between Tracking and Off with the condition Power == 0.

<img width="518" height="311" alt="Task5" src="https://github.com/user-attachments/assets/3e6437a9-4d2e-4051-ab65-70805de32a6c" />

## Step 6 
The transition execution order specifies the sequence in which transitions are tested. In this chart, responding to the power turning off should take priority over switching between Seeking and Tracking.
Select the transition from Tracking to Off. In the Transition tab in the toolstrip, change Execution Order to 1.

<img width="943" height="549" alt="Task6" src="https://github.com/user-attachments/assets/650ed110-9692-4d12-bf2e-70a0b5ba6d27" />

