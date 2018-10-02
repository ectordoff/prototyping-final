#include <Servo.h>

Servo myservo;
int val;
int photocellReading;     // the analog reading from the sensor divider


void setup()
{
myservo.attach(12);
  Serial.begin(9600);   

}
void loop()
{
Serial.print("Analog reading = ");
  //Serial.println(photocellReading);  

  
photocellReading = analogRead(0);
//val = map(photocellReading, 0, 1023, 0, 400);
  Serial.println(photocellReading);  

//if(photocellReading < 200)
//{
//    val=0;
//}
if(photocellReading > 300)
{
    val=60;
}
if(photocellReading > 500)
{
   val=180;
}

myservo.write(val);
delay(15);
} 
