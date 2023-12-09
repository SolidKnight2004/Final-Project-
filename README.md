This project will introduce a button on and off the LED and an Ultrasonic Distance Sensor. In the first part, it will have the LED light up when you hold the button and go off when you let go. The second part will be an Ultrasonic Distance Sensor that will measure the distance of an object when it comes close to the sensor.


Components needed
Raspberry Pi
Breadboard
Resistors
HC-SR04 Distance Sensor
Buttons
LEDs
Jumper Wires


LED Button On and Off





Step 1
First connect the LED Light on the breadboard, put the short end of the LED at the far end of number 10 and long end to the left at the far end of number 8. After that, get a resistor 


Step 2
To connect the Raspberry Pi to the breadboard, you need two jumper wires. First, connect the black wire to the Ground at number 39 on the Raspberry Pi, and then connect the white wire to GPIO 26. On the breadboard, connect the white wire (ground wire) to number 8 and the black wire (GPIO 26 wire) to number 13. It will establish a connection between the Raspberry Pi and the breadboard.

Get two jumper wires and connect them on the Raspberry Pi at the bottom left. The black wire is connected to the Ground at number 39 and white wire is connected to GPIO 26. After that, connect the other ends to the breadboard, connect the white wire (ground wire) to number 8 and the black wire (GPIO 26 wire) to number 13 on the breadboard .


Step 3
Then connect the button to the breadboard 


Step 4 
Use the code I used in the project and go login to your Raspberry Pi. click on the Raspberry logo at the top left of the screen, then click on Programming and go down to click on Thonny. Next copy the code and paste it to Thonny, then click Run at the top to run the code.


from gpiozero import PWMLED
from time import sleep

led = PWMLED(26)

while True:
    led.value = 0  # off
    sleep(1)
    led.value = 0.5  # half brightness
    sleep(1)
    led.value = 1  # full brightness
    sleep(1)


Distance Sensor Setup



Step 1 
First you want to get the Distance Sensor and put it to the left side of your breadboard at numbers 6 and 9.

Step 2
Then get two resistors to prevent voltage from overheating the sensor. Place the first resistor on numbers 7 and 12 and the second one on 6 and 12 in the breadboard.

Step 3 
Next get four jumper wires 

Step 4
Use the code I used in the project and go login to your Raspberry Pi. click on the Raspberry logo at the top left of the screen, then click on Programming and go down to click on Thonny. Next copy the code and paste it to Thonny, then click Run at the top to run the code.

#!/bin/python

from gpiozero import DistanceSensor

from time import sleep

sensor = DistanceSensor(echo=23, trigger=24, max_distance=2.0)

while True:
        
       
        distance = sensor.distance * 100
       
        print("Distance: %.2f", % distance)
        
        sleep(0.5)


Conclusion 
![unnamed](https://github.com/SolidKnight2004/Final-Project-/assets/153010427/1b1eced8-ee49-4acb-ad5f-6c96c3b88ad2)

