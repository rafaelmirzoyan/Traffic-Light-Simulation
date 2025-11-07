===🚦TRAFFIC LIGHT FSM===

This folder contains a program that simulates a traffic light system 
with a pedestrian crossing button using a finite state machine(FSM). The
simulation runs in the terminal and uses the ncurses library to handle
real-time, non-blocking keyboard input. The system cycles through the
default green-yellow-red pattern, and allows pedestrians to request crossing during the green light phase. 

===⚙️HOW TO BUILD===
1. Make sure you have the ncurses library installed on your system.

2.To complite the program, run: 

	make
	
3. To start the simulation, run:

	./trafficLight

4. To run the simulation in fast mode (shorter light durations), use:

	./trafficLight --fast

5. Use the help flag to see available options and usage information:

	./trafficLight --help

6. Use make clean to remove the compiled executable:

   make clean

===🧠SYSTEM BEHAVIOR===
The state flow is: START -> GREEN -> YELLOW -> RED -> GREEN
pedestrian crossing requests are accepted during the green phase

===🧩State Overview===
        START           -press 's' to begin
        GREEN_NO_PED    -cars move, no pedestrian input
        GREEN_PED_WAIT  -cars move, pedestrian crossing scheduled
        YELLOW          -cars prepare to stop
        RED             -cars stop, pedestrians cross
        EXIT            -cleanup and quit
        
State transitions are triggered either by elapsed timers, or in response
to user input

===💻Expected Output===
During each state, the terminal displays:
1. Current light color
2. Description of system status (e.g. cars go, pedestrians wait)
3. Time elapsed and remaining in that state
4. When 'p' is pressed a message appears scheduling pedestrian crossing
5. When 'e' is pressed the program exits

===⏱️Timing===
Default cycle:
	GREEN_TIME =       120 s
	YELLOW_TIME =       5  s
	RED_TIME =          30 s
	PEDESTRIAN_DELAY =  30 s

Fast cycle:
        GREEN_TIME =        10 s
        YELLOW_TIME =       2  s
        RED_TIME =          8  s
        PEDESTRIAN_DELAY =  3  s

 ===⌨️Keyboard Controls===
	s - Start simulation
	p - Request pedestrian crossing
	e - Exit simulation


===✅END OF README===

