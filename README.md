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
  Derecho.attach(PINSERVODERECHO);
  Izquierdo.attach(PINSERVOIZQUIERDO);
  Serial.begin(9600);
  BT.begin(9600);
 
}

char orden;


void loop() {
  if(Serial.available()>0)
  {
    orden=Serial.read();
    Serial.println(orden);
  }
  if(BT.available()>0)
  {
    orden=BT.read();
    Serial.println(orden);
  }
  if(orden=='w') //Adelante
  {
    Derecho.write(0); //Sentido Horario 
    Izquierdo.write(180); //Sentido Antihorario
  }
  if(orden=='s'); //Atras
  {
    Izquierdo.write(180); //Sentido Horario
    Derecho.write(0); //Sentido Antihorario
  }
  if(orden=='a') //Izquierda
  {
    Izquierdo.write(0); //Sentido Horario
    Derecho.write(90); // Sentido Antihorario  
  }
  if(orden=='d') //Derecha 
  {
    Derecho.write(0); // Sentido Horario
    Izquierdo.write(90); //Sentido Antihorario 
  }
  if(orden=='f') //Parar
  {
    Derecho.write(90); //Detenido
    Izquierdo.write(90); //Detenido
  }
    
} 
