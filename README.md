# DOJO-1

**Semaforo doble**

![semaforodoble](https://user-images.githubusercontent.com/108504690/234933574-becf2738-38af-443b-a599-07bf217374ae.png)

**Integrantes**
°Ezequiel Gonzalez 
°Julian conti 
°juan Ignacio Feas 

**Proyecto**

![ejemplo del profe sobre el semaforo](https://user-images.githubusercontent.com/108504690/234929566-c3030303-2764-4c7f-918e-4bc98bb7ff79.png)

**descripcion**
es un semaforo y sirve para controlar el trafico en las calles y ayudar a los no videntes con un buzzler

**Link proyecto**
https://www.tinkercad.com/things/agkGXpDME00-dojo-ezequiel-gonzalez-1-semaforo-/editel?sharecode=GZGUNVGA3hQxRMQqhsORcb-P98bmYIMT7CeTNEk-TZU

**codigo principal**

este codigo se encarga de prender y apagar las luces teniendo en cuenta el buzzler como indicador de tiempo para el amarillo y el rojo mientras que el verde tiene un delay para indicar cuanto tiempo esta prendido

```c++
void loop() //semaforo :
{
  digitalWrite(LEDVERDE1, HIGH);
  digitalWrite(LEDVERDE2, HIGH);
  
  delay(45000);
  
  digitalWrite(LEDVERDE1, LOW);
  digitalWrite(LEDVERDE2, LOW);
  digitalWrite(LEDAMARILLO1, HIGH);
  digitalWrite(LEDAMARILLO2, HIGH);
  
  for (int CantPitidos = 0; CantPitidos < 2; CantPitidos++)
  {
    tone(BUZZLER, 500);
    delay(1000);
    noTone(BUZZLER); 
    delay(2000); 
    //dura 5 segundos
  }
  
  digitalWrite(LEDAMARILLO1, LOW);
  digitalWrite(LEDAMARILLO2, LOW);
  digitalWrite(LEDROJO1, HIGH);
  digitalWrite(LEDROJO2, HIGH);
  
  for (int CantPitidos = 0; CantPitidos < 30; CantPitidos++)
  {
    tone(BUZZLER, 1000);
    delay(500);
    noTone(BUZZLER);
    delay(500);
    //dura 30 segundos
  }
  
  digitalWrite(LEDROJO1, LOW);
  digitalWrite(LEDROJO2, LOW);
}

