// C++ code  
//  
#include <Servo.h>  

int Distance = 0;  

int lolz = 0;  

long readUltrasonicDistance(int triggerPin, int echoPin)  
{
  pinMode(triggerPin, OUTPUT);  // Clear the trigger  
  digitalWrite(triggerPin, LOW);  
  delayMicroseconds(2);  
  // Sets the trigger pin to HIGH state for 10 microseconds  
  digitalWrite(triggerPin, HIGH);  
  delayMicroseconds(10);  
  digitalWrite(triggerPin, LOW);  
  pinMode(echoPin, INPUT);  
  // Reads the echo pin, and returns the sound wave travel time in microseconds  
  return pulseIn(echoPin, HIGH);  
}  

Servo servo_9;  

void setup()  
{  
  Serial.begin(9600);  
  servo_9.attach(9, 500, 2500);  
}  

void loop()  
{  
  Serial.println(0.006783 * readUltrasonicDistance(5, 7));  
  if (15 > 0.006783 * readUltrasonicDistance(5, 7)) {  
    servo_9.write(0);  
  } else {  
    servo_9.write(90);  
  }  
  delay(10); // Delay a little bit to improve simulation performance  
}   
