# Pid Controller using a Light Detecting sensor With Arduino to control a geared 12V DC motor.

In this blog I have used a LDR light detecting resistor as a sensor to calculate the output needed for controlling a DC motor.

If the intensity of light to the LDR decreases, then the motor starts turning clockwise and likewise if the light to the LDR increases - then the motor starts spinning in the reverse ( anti clockwise ) direction.

A simple experiment would be if I moved my finger on the LDR and as I come close and try to cover it then the motor spins clockwise, and as I withdraw my finger from my LDR - the motor spins anticlockwise.


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


References :

https://en.wikipedia.org/wiki/PID_controller
https://www.allaboutcircuits.com/projects/control-a-motor-with-an-arduino/
https://en.wikipedia.org/wiki/Sensor
https://github.com/br3ttb/Arduino-PID-Library/blob/master/PID_v1.h
https://www.arduino.cc/

