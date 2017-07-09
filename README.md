# PID Controller using a Light Detecting Sensor and an Arduino to control a Geared 12V DC motor.

This blog is not about the PID controller ! There are a lot of videos/wiki materials out on the internet that tells about this.

Here I have used the PID algorithm to control a geared DC motor based on inputs from the Light Detecting Resistor.

###This is being superseded by my next version which balances the ball on a rail controlled using Ultrasonic Distance Sensor a Servo motor connected to an Arduino https://github.com/kiranshashiny/PidController_BallBalancingRobot

If the intensity of light to the LDR decreases, then the motor starts turning clockwise and likewise if the light to the LDR increases - then the motor starts spinning in the reverse ( anti clockwise ) direction.

A simple experiment would be if I moved my finger on the LDR and as I come close and try to cover it then the motor spins clockwise, and as I withdraw my finger from my LDR - the motor spins anticlockwise. This is my first foray into tis project and would like to implement or extrapolate on this a little further once I get familiarity in the functioning of the algorithm and it's behavior.

Now, this is all based on an algorithm called PID ( Proportional, Integral and Differential) and one can find a lot of examples, definitions, videos of what a PID is on the internet these days.

The PID in my opinion can be thought of ( without going into the Calculus ) multiple inputs, a Set point which is a constant, and an output in PWM which can be used for any mechanical objects to turn/ spin or do some movements.

The inputs can be in the form of analog signals and they can be from sensors like light sensor, heat sensor, temperature sensor etc and these feed in analog signals to the Arduino.

There is a constant set point that is being fed to the arduino as well which is telling the algorithm that if the inputs reach the set point then produce some output ( like send a PWM - Pulse Width Modulation signal on the output pin of the Arduino )

Essentially, this blog is about the Arduino running a code which uses the PID algorithm and senses the light from the LDR on one of the analog pins, compares it to the set point and once it reaches or goes above the set point - then send an external signal as an output and in my case a DC motor.

In this demo I have used the following items :
Arduino
LDR
L293D - motor driver
12V geared DC motor
Male to Male/ female to female and some female to male connectors to connect the circuit.


The formula for calculating the PID is as shown in this formula.

<img width="723" alt="screen shot 2017-07-03 at 1 13 07 pm" src="https://user-images.githubusercontent.com/14288989/27782744-62e4fd94-5ff1-11e7-9544-234348dc1458.png">


I've used the Arduino Pid Library PID_v1.h in my sketch as shown.

<img width="565" alt="screen shot 2017-07-03 at 1 18 55 pm" src="https://user-images.githubusercontent.com/14288989/27783035-43dcc336-5ff2-11e7-862b-b234eee5ff25.png">

<img width="694" alt="screen shot 2017-07-03 at 1 19 18 pm" src="https://user-images.githubusercontent.com/14288989/27783034-439ccf56-5ff2-11e7-9da0-694c4c2a70c3.png">

The connections are as follows :
Arduino  Motor Driver L293D

===========================
Pin  9      Enable 1 

Pin  5      IN1

Pin  6      IN2

### Motor Driver L293D
Pin 3 and 6 - to Motor Inputs.

Pin 2 and 7 are inputs from the Arduino

Pin 1 is connected to Pin 9 ( EN1) of the Arduino

Pin 4 and 5 are connected to GND.

Pin 8 is connected to 12V DC wall adapter. 

The Inputs of the LDR:

+5V -> one end of the 220 ohm resistor
Other end is connected to 


References :



https://en.wikipedia.org/wiki/PID_controller

https://www.allaboutcircuits.com/projects/control-a-motor-with-an-arduino/

https://en.wikipedia.org/wiki/Sensor

https://github.com/br3ttb/Arduino-PID-Library/blob/master/PID_v1.h

https://www.arduino.cc/
