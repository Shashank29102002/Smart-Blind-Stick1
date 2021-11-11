# Smart-Blind-Stick1
The smart blind stick automatically detects the obstacle in front of the person and give him a response to the person by vibrating the stick and also with a warning sound. Through this, the blind person can aware about the obstacles in front of him. We used Ultrasonic sensor for detecting the obstacles.
/* * make a smart stick that helps the Blind */
#define trigPin 9
 #define echoPin 8
#define Buzzer1 5//active
#define Buzzer2 7//passive
 #define Led1 6//Vibration
 int sound = 250;
 void setup()
 {
 Serial.begin (9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);
 pinMode(Buzzer1, OUTPUT);
 pinMode(Buzzer2, OUTPUT);
 pinMode(Led1, OUTPUT);
 }
 void loop()
 {
Serial.begin(9600);
 long duration, distance;
 digitalWrite(trigPin, LOW);
 delay(2);
digitalWrite(trigPin, HIGH);
delay(10);
 digitalWrite(trigPin, LOW);
duration = pulseIn(echoPin, HIGH);
 distance = (duration/2) / 29.1;
digitalWrite(Buzzer1, LOW);
digitalWrite(Buzzer2, LOW);
digitalWrite(Led1, LOW);
 if (distance<40)
 {
digitalWrite(Led1, HIGH);
 delay(2000);
 }
 if (distance<20)
 {
 digitalWrite(Led1, HIGH);
 delay(2000);
 digitalWrite(Buzzer1, HIGH);
delay(2000);
 }
if (distance<10)
 {
 digitalWrite(Led1, HIGH);
 delay(2000);
digitalWrite(Buzzer1, HIGH);
delay(2000);
 digitalWrite(Buzzer2, HIGH);
 delay(2000);
}
} 

