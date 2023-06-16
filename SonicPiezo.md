![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/e829030e-e1ab-4974-8c64-6d2b217b160d)


## Programming the arduino in C++

- Arduino code will infinitely repeat itself, but void setup will only occur once


## Full code

https://github.com/0Domlightning0/TheJournal/blob/main/SonicPiezoC%2B%2B.md

### Setup 

void setup()
{
  Serial.begin(9600);
  servo_9.attach(9, 500, 2500);
}

#### servo_9.attach(pin, min, max)

pin - pin of arduino you are attaching to

![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/33d4aeb7-5b79-4076-8d76-44c75f719a79)

min - min pulse width

max - max pulse width

#### Ultrasonic

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

- repeatidly sends and recives sound signals and returns the amount of milliseconds, which is converted into inches/cm later


### Loop

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

#### readUltrasonicDistance(5, 7)
- (5,7) set to your tigger and echo pins in that order

#### 0.006783 * readUltrasonicDistance(5, 7)
- converts the milliseconds from the sensor into a distance, this case in inches
