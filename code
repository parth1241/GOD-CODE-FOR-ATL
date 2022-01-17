// VCC ---> 5V For ir Sensor
//GND ---> GND
//Digital Pin For Ir Sensors 8,9
//Analog Pin For Ir Sensors A0,A1
//Pin For Led/Motor ----> 10
//Pin For Servo Signal ----> 11

//Use Serial Monitor For Values 
//ShortCut For The Serial monitor Is Ctrl/Command+Shift+M


#include <Servo.h>


int IRValueA1 = 0;

int IRValueA = 0;

Servo servo_11;

void setup()
{
  pinMode(8, INPUT);
  pinMode(9, INPUT);
  servo_11.attach(11, 500, 2500);

  pinMode(10, OUTPUT);
  Serial.begin(9600);
}

void loop()
{
  IRValueA = digitalRead(8);
  IRValueA1 = digitalRead(9);

  servo_11.write(90);
  if (IRValueA == 1 && IRValueA1 == 1) {
    digitalWrite(10, LOW);
  }
  if (IRValueA == 0 && IRValueA1 == 0) {
    digitalWrite(10, HIGH);
  }
  if (IRValueA == 1 && IRValueA1 == 0) {
    servo_11.write(45);
  }
  if (IRValueA == 0 && IRValueA1 == 1) {
    servo_11.write(135);
  }
  Serial.println(IRValueA);
  Serial.print(IRValueA1);
  delay(10); 
}
