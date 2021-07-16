# Object Avoiding Robot
A robot that can avoid obstacles in its way when moving

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Alan Z | Leigh | Engineering | Incoming Junior

![Headstone Image](image url 
  
# Final Milestone



[![Final Milestone](

# Second Milestone


[![Second Milestone](


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


