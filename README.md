# EXPERIMENT-NO--05-Distance measurement using Ultrasonic sensor

## AIM: 
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error
 
### COMPONENTS REQUIRED:
1.	ultrasonic sensor module HC-SR04
2.	1 KΩ resistor 
3.	Arduino Uno 
4.	USB Interfacing cable 
5.	Connecting wires 


### THEORY: 
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats do. It offers excellent non-contact range detection with high accuracy and stable readings in an easy-to-use package from 2 cm to 400 cm or 1” to 13 feet.

The operation is not affected by sunlight or black material, although acoustically, soft materials like cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications
Power Supply − +5V DC
Quiescent Current − <2mA
Working Current − 15mA
Effectual Angle − <15°
Ranging Distance − 2cm – 400 cm/1″ – 13ft
Resolution − 0.3 cm
Measuring Angle − 30 degree

The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:

The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz).
The sound travels through the air. If it finds an object, it bounces back to the module.
The ultrasound receiver (echo pin) receives the reflected sound (echo).
The time between the transmission and reception of the signal allows us to calculate the distance to an object. This is possible because we know the sound’s velocity in the air. Here’s the formula:

distance to an object = ((speed of sound in the air)*time)/2
speed of sound in the air at 20ºC (68ºF) = 343m/s

### FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR 
CIRCUIT DIAGRAM
![Screenshot 2024-03-07 112346](https://github.com/sanjaysivaramakrishnan/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151629616/71963344-1dd0-4d80-837c-4bbceae17958)
SCHEMATIC DIAGRAM
![WhatsApp Image 2024-03-07 at 11 27 46_8183d956](https://github.com/sanjaysivaramakrishnan/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151629616/f20db58e-c66c-44fc-8672-07cf71f52878)


### PROCEDURE:
1.	Connect the circuit as per the circuit diagram 
2.	Connect the board to your computer via the USB cable.
3.	If needed, install the drivers.
4.	Launch the Arduino IDE.
5.	Select the board (If you the board is arduino uno, select accordingly).
6.	Select your serial port, accordingly ( E.g. COM5 )
7.	Open the file of the program  and verify the error , clear if any errors that are existing 
8.	Upload the program and check for the physical working. 
9.	Ensure safety before powering up the device 
10.	Plot the graph for the output voltage vs the resistance 


### PROGRAM 
~~~
const int trigerpin=10;
const int echopin=9;
int red=7,green=6;
long duration;
float  distance;
void setup()
{
  pinMode(trigerpin, OUTPUT);
  pinMode(echopin, INPUT);
  pinMode(red, OUTPUT);
  pinMode(green, OUTPUT);
  Serial.begin(9600);

}

void loop()
{
  digitalWrite (trigerpin,LOW);
  delay(20);
  digitalWrite (trigerpin,HIGH);
  delay(20);
  digitalWrite (trigerpin,LOW);
  duration=pulseIn(echopin,HIGH);
  distance =duration*0.034/2;
  Serial.print(distance);
  Serial.println(" cms");
  if(distance>5)
  {
    digitalWrite(red,HIGH);
    delay(200);
    digitalWrite(red,LOW);
    delay(200);
  }
  else
  {
    digitalWrite(green,HIGH);
    delay(200);
    digitalWrite(green,LOW);
    delay(200);
  }
}
~~~



### Distance vs measurement table 

![WhatsApp Image 2024-03-07 at 11 22 31_3ba08de6](https://github.com/sanjaysivaramakrishnan/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151629616/6075cf7c-e771-41fa-acb9-70fbc0b86afa)
			
 
			
			
			
			
			
			
			Average error = sum/ number of readings 
 

### GRAPH
![WhatsApp Image 2024-03-07 at 11 22 13_deb9a168](https://github.com/sanjaysivaramakrishnan/Experiment--04-Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/151629616/1e1618c2-8958-496d-8f49-568383cb6f2d)







### RESULTS

THUS WE CREATED A CIRTUIT FOR  MEASUREING DISTANCE USING ULTRASONIC SENSOR.
.
 
