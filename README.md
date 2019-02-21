#include <servo.h> //Libreria para manejo de servos
#include <SoftwareSerial.h> //Libreria para Bluetooth
#define PINSERVODERECHO 6 // Definido el pin del servo derecho
#define PINSERVOIZQUIERDO 11 //Definido el pin del servo izquierdo
#define TXBluetooth 3 //Lugar de conexión d e 1 Blue toothRX
#define RXBluetooth 2 // Lugar de conexión de 1 Blue toothTX

Servo Derecho;
Servo Izquierdo;
SoftwareSerial BT(RXBluetooth,TXBluetooth);


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
