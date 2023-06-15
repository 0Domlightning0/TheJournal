![image](https://github.com/0Domlightning0/TheJournal/assets/99225898/e829030e-e1ab-4974-8c64-6d2b217b160d)


## Programming the arduino in C++

- Arduino code will infinitely repeat itself


## Full code

https://github.com/0Domlightning0/TheJournal/blob/main/SonicPiezoC%2B%2B.md

### Setup 

void setup()
{
  Serial.begin(9600);
  servo_9.attach(9, 500, 2500);
}

