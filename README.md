//Leidy Lopez - Luis Manuel Jiménez Tabares.
#include<Servo.h> //Libreria para manejo de servos
#define PINSERVODERECHO 6// Definido el pin del servo derecho
#define PINSERVOIZQUIERDO 11
Servo Derecho;
Servo Izquierdo;
int orden = '0';
void setup() {
  Derecho.attach(PINSERVODERECHO);
  Izquierdo.attach(PINSERVOIZQUIERDO);
  Derecho.write(90);  //Motor en stop
  Izquierdo.write(90); //Motor en stop
  Serial.begin(9600);
}

void loop() {
   if (Serial.available() > 0) {    // lee el bluetooth y almacena en estado
    orden = Serial.read();
    Serial.println(orden);
  }
    
  if(orden == 'S'){
    Derecho.write(90);    //Motor en stop
    Izquierdo.write(90);   //Motor en stop
    
  }
  else{
  if (orden == 'w') //ADELANTE
  {
    Derecho.write(0);
    Izquierdo.write(180);
    
  }
  if (orden == 's') //ATRAS
  {
    Derecho.write(180);
    Izquierdo.write(0);
  }
  if (orden == 'd') //DERECHA
  {
    Derecho.write(180);
    Izquierdo.write(180);
 
  }
  if (orden == 'a') //izquierda
  {
  Derecho.write(0);
  Izquierdo.write(0);
 
  }
   if(orden== 'p')
   {
  Derecho.write(90);
  Izquierdo.write(90);
   }



  }
 
