# Código 

#include <Arduino.h>


/* delete a task when finish,
this will never happen because this is infinity loop */


void funcion1(void * parameter)
{
#define led 16
pinMode(led, OUTPUT);

for(;;)
{
digitalWrite(led, HIGH);
Serial.println("ON");
delay(1000);
digitalWrite(led, LOW);
Serial.println("OFF");vTaskDelete (NULL);
delay(1000);

}

}

void setup()
{
Serial.begin(112500);

xTaskCreate(
funcion1, /* Task function. */
"FUNCION 1", /* name of task. */
10000, /* Stack size of task */
NULL, /* parameter of the task */
1, /* priority of the task */
NULL); /* Task handle to keep track of created task */
}


void loop()
{}

# Diagrama de flujos

![image](https://user-images.githubusercontent.com/101355262/171414265-32a5a15f-1104-4127-819d-554739ebbc97.png)

# Diagrama de tiempos

![image](https://user-images.githubusercontent.com/101355262/171414441-d1c8a705-63af-4f3e-aef3-dc71e7f10052.png)

