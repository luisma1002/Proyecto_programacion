#include <servo.h>
# define PINSERVODERECHO 12
# define PINSERVOIZQUIERDO 11
SERVO MOTORDERECHO;

SERVO MOTORIZQUIERDO;


void setup() {
  Serial.begin(9.600);
  MOTORDERECHO.attach(pinservoderecho);
  MOTORIZQUIERDO.attach(pinservoizquierdo);
  // put your setup code here, to run once:

}

void loop() {
  char orden;
  if(Serial.available()>0);
  {
    orden=Serial.read();
    Serial.println(orden);
  }
  if(orden
  
  MOTORDERECHO.write(0);//girar el sentido horario
    delay (1000);
  MOTORIZQUIERDO.write(180);
  l
  
  
} 
