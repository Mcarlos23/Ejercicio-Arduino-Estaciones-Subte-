# Proyectos-SPD: DOJO Nº 2

Ejercicio de simulación de recorrido de estaciones de Subte con indicación sonora. 

![](https://github.com/Mcarlos23/Ejercicio-Arduino-Estaciones-Subte-/blob/main/ejercicio_subte.jpg?raw=true)

## Comenzando 🚀

Estas instrucciones te permitirán comprender el funcionamiento del proyecto. Además, se incluye el enlace hacia TinkerCad para poder ver el proyecto armado con sus distintos componentes y poner el código en ejecución. 

Ve a la sección de **link al proyecto** para ver el código del proyecto.

## Consigna 🔩

1- Se debe implementar un sistema que permita el usuario identificar en que estación de Subte se encuentra mediante el encendido de una led y una indicación sonora única por estación. 

2- Se debe mostrar en un display de 7 segmentos la cantidad de estaciones restantes para llegar a la estación terminal.

3- El sistema debe iniciar apagado. El mismo se encederá e iniciará el recorrido unicamente tras presionar el botón. 

Nota: se deberán utilizar funciones que tengan mensajes que se muestran por el monitor Serial.


## Función principal 🔩

* * *

 ~~~ C++ 
void encenderSistema(int numero)
{
  switch(numero)
  {
  	case 0:
    Serial.println("Estacion Moreno");
    Serial.println("Final del Recorrido");
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(F, HIGH);
   
    digitalWrite(LED_4, HIGH);
    tone(PIEZO, 1000);
    break;
    
    case 1:
    
    Serial.println("Estacion San Juan");
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(LED_3, HIGH);
    tone(PIEZO, 800);
    break;
    
    case 2:
    Serial.println("Estacion Independencia");
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(G, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(E, HIGH);
    digitalWrite(LED_2, HIGH);
    tone(PIEZO, 600);
    break;
    
    case 3:
    Serial.println("Inicio del recorrido");
    Serial.println("Estacion Constitucion");
    digitalWrite(A, HIGH);
    digitalWrite(B, HIGH);
    digitalWrite(C, HIGH);
    digitalWrite(D, HIGH);
    digitalWrite(G, HIGH);
    
    digitalWrite(LED_1, HIGH);
    tone(PIEZO, 400);
    break;
    
  }
  
  delay(2000);
  apagarTodos();
  delay(1000);
}
 ~~~

Esta función recibe como parámetro un entero que será un contador decremental en cada iteración en el loop principal. A través del uso de la función switch configuraremos el comportamiento de esta función. Según el valor recibido por paramétro se indicará el led que debe encenderse, el sonido que debe emitir el piezo y el mensaje que se imprimirá en consola. 

## Funcionamiento

El proyecta cuenta con los siguientes componentes:

* 1 Placa Arduino uno. 
* 1 Display 7 segmentos. 
* 4 Leds. 
* 1 Buzzer (Piezo). 
* 1 Botón.
* 4 Resistencias de 220Ω.

Usaremos el botón en su configuración pull-up. Una vez presionado el botón, realizaremos la validación e invocaremos a la función principal que hemos descrito en el punto anterior.



## 🤖 Link al proyecto 
Este [enlace](https://www.tinkercad.com/things/aDkOUZ9uI7W-dojo-2/editel?sharecode=uPABeSAVrjzKrpq6tUZM83JOV3as8CjhxyFXHOdvt3w) te llevará al proyecto en TinkerCad.

### Autor ✒️

* **Carlos Marquez** 





⌨️ con ❤️ por Carlos Marquez, DIV G, SPD 2023.
