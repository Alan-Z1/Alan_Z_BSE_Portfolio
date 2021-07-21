# Object Avoiding Robot
A robot that can avoid obstacles in its way when moving

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Alan Z | Leigh | Engineering | Incoming Junior

![Headstone Image](image url 
  
# Final Milestone



[![Final Milestone](

# Second Milestone

My second milestone was building the chassis, which included the motors and wheels. I also wired up the L298N motor driver with the motors and the Arduino. This was difficult, particularly wiring the motor driver and motors together, because the wires tended to slip loose and fall out. Then, I uploaded some code to test the motors' basic functions. The code I used to test the motors is shown below.

```
// Motor A connections
int enA = 9;
int in1 = 8;
int in2 = 7;
// Motor B connections
int enB = 3;
int in3 = 5;
int in4 = 4;

void setup() {
	// Set all the motor control pins to outputs
	pinMode(enA, OUTPUT);
	pinMode(enB, OUTPUT);
	pinMode(in1, OUTPUT);
	pinMode(in2, OUTPUT);
	pinMode(in3, OUTPUT);
	pinMode(in4, OUTPUT);
	
	// Turn off motors - Initial state
	digitalWrite(in1, LOW);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, LOW);
}

void loop() {
	directionControl();
	delay(1000);
//	speedControl();
	delay(1000);
}


// This function lets you control spinning direction of motors
void directionControl() {
	// Set motors to maximum speed
	// For PWM maximum possible values are 0 to 255
	analogWrite(enA, 255);
	analogWrite(enB, 255);

	// Turn on motor A & B
	digitalWrite(in1, HIGH);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, HIGH);
	delay(2000);
	
	// Now change motor directions
	digitalWrite(in1, LOW);
	digitalWrite(in2, HIGH);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);
	delay(2000);
	
	// Turn off motors
	digitalWrite(in1, LOW);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, LOW);
}

// This function lets you control speed of the motors
void speedControl() {
	// Turn on motors
	digitalWrite(in1, LOW);
	digitalWrite(in2, HIGH);
	digitalWrite(in3, HIGH);
	digitalWrite(in4, LOW);

	// Accelerate from zero to maximum speed
	for (int i = 0; i < 256; i++) {
		analogWrite(enA, i);
		analogWrite(enB, i);
		delay(20);
	}
	
	// Decelerate from maximum speed to zero
	for (int i = 255; i >= 0; --i) {
		analogWrite(enA, i);
		analogWrite(enB, i);
		delay(20);
	}
	
	// Now turn off motors
	digitalWrite(in1, LOW);
	digitalWrite(in2, LOW);
	digitalWrite(in3, LOW);
	digitalWrite(in4, LOW);
}
```

[![Second Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1626886019/video_to_markdown/images/youtube--hsiMysgAM8c-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/hsiMysgAM8c "Alan Z Milestone 2")


# First Milestone

My first milestone was setting up the ultrasonic distance sensor and wiring it up with the Arduino and breadboard. First, I had to find a way to upload code to the Arduino with my Chromebook, so I decided to use Arduino Cloud. I also had to figure out how to code the Arduino so that I could see the distance when it ran. Eventually, I was able to make the ultrasonic distance sensor work properly. The distance in centimeters was printed out on my screen with each interval of time that passed. The code I used is shown below. The interval of time between each printout is 1000 millseconds, or 1 second.

```
const int trigPin = 9; 
const int echoPin = 10;
float duration, distance; 

void setup() {
    pinMode(trigPin, OUTPUT); 
    pinMode(echoPin, INPUT); 
    Serial.begin(9600); 
}

void loop() {
 digitalWrite(trigPin, LOW); 
 delayMicroseconds(2); 
 digitalWrite(trigPin, HIGH); 
 delayMicroseconds(10); 
 digitalWrite(trigPin, LOW); 
 duration = pulseIn(echoPin, HIGH); 
 distance = (duration*.0343)/2; 
 Serial.print("Distance: "); 
 Serial.println(distance); 
 delay(1000); 
}
```

[![First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1626452357/video_to_markdown/images/youtube--52GaqGRs94M-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/52GaqGRs94M "Alan Z Milestone 1")


