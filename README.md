# Práctica 3
# Integrantes
* Gabriel Magaña Rendón
* Abel Morales Lino
* Agustín Téllez-Girón Sánchez
* Salvador Zaragoza Maldonado
# Introducción
<div align="justify">

En la tercera práctica de laboratorio, se retomaron conceptos previamente vistos, como la movilización del robot en modo "world". Esto fue fundamental para avanzar en la creación de puntos clave utilizando la opción "Jog & Teach", que se encuentra dentro del panel de control de "Robot Manager". Esta opción permite al operador manipular el robot de manera precisa y registrar posiciones específicas en el espacio de trabajo, las cuales serán empleadas posteriormente en la secuencia de movimientos del robot.

La práctica también introdujo la carga de código al brazo robótico Epson C4, permitiendo no solo la creación de puntos de interés, sino también la programación de la secuencia de activación de cada uno de esos puntos mediante los comandos "Go" y "Home", comandos fundamentales para la navegación del robot entre posiciones previamente definidas, asegurando un movimiento eficiente y controlado.

Además, se trabajó con la activación de la pinza neumática, un accesorio esencial del brazo robótico que permite manipular objetos dentro del entorno de trabajo. La correcta sincronización entre los movimientos del brazo y el control de la pinza es clave para garantizar una operación precisa y segura en aplicaciones de automatización industrial.

</div>

# Objetivo
<div align="justify">
Intercambiar de lugar dos fusibles, de la estación 3 y 4, empleando la opción "Jog & Teach" del "Robot Manager" para grabar y posteriormente ejecutar una secuencia de movimiento.
</div>

# Instrucciones 
<div align="justify">
Se comenzó por crear un proyecto nuevo en el software Epson RC+, en el cual se reemplazaron los valores del HOME. Para ello, se abrió el apartado de "Robot Manager" y se configuró el movimiento del robot en modo "Joint" para poder mover J6 a un valor de 90 grados. Una vez hecho esto, se abrió el apartado de "Home Config", se leyeron las posiciones y se configuraron como un nuevo HOME, como se muestra en la Figura 1. [1]

![Figura 1](Figura1NH.png)
  
*Figura 1. Configuración de un nuevo Home.*


Aquí tienes el texto corregido:

Posteriormente, se estableció comunicación mediante el puerto USB con el brazo robótico. Empleando el modo "World", se comenzaron a realizar manualmente una serie de movimientos a prueba y error para grabar los puntos que más adelante fueron utilizados en la secuencia que permitió mover un primer fusible de la estación 3 a un lugar de reposo, en este caso una caja, para luego recoger el segundo fusible de la estación 4 y llevarlo a la estación 3, y finalmente regresar por el primer fusible y colocarlo en la estación 4.

La información de cada uno de los puntos guardados se podrá ver en el apartado "Points" dentro del mismo "Robot Manager", donde se podrá revisar la etiqueta con la que se guardó ese punto en específico, además de tener todas las coordenadas de la posición. Desde aquí se pueden administrar los puntos ya creados, como se muestra en la Figura 2. [1]

![Figura 2](Figura2Puntos.jpg)

Figura 2. Sección Points dentro del robot manager*

Por ultimo se muestra la secuencia empleada para cumplir el objetivo de la práctica.

```
Function main
Home
On 2
Go primero
Go segundo
Off 2
Go primero
Home
Go tercero
On 2
Home
Go cuarto
Go quinto
Off 2
Go cuarto
Home
Go primero
Go segundo
On 2
Go primero
Home
Go tercero
Off 2
Home
Go cuarto
Go quinto
On 2
Go cuarto
Home
Fend
```
Es importante recalcar que en las lineas de código donde se tienen los comandos On y Off es debida a la activación de la pinza del brazo y se pone el número 2 debido a que se encuentra en dicho Bit de las salidas, esto se puede visualizar en la sección "I/O Monitor".

Acontinuación se agrega el video del funcionamiento de la secuencia previamente descrita.

[![Video de la secuencia](image.png)](https://drive.google.com/file/d/1C9VOyp0twD5em_AlmO6HtenzBoFVtHih/view?usp=drive_link)

*Video de la secuencia programada en el brazo.*
# Conclusiones 
<div align="justify">
  
  __Gabriel Magaña Rendón:__ 
</div>

<br/>

<div align="justify">
  
__Abel Morales Lino:__ 
</div>

<br/>
<div align="justify">
  
__Agustín Téllez-Girón Sánchez:__ 
</div>

<br/>
<div align="justify">
  
__Salvador Zaragoza Maldonado:__ 
</div>

# Referencias Bibliográficas
[1] Seiko Epson Corporation, *Robots de 6 ejes Serie C4 MANUAL DEL MANIPULADOR*, 2020, https://files.support.epson.com/far/docs/epson_c4-series_robot_manual(r20)_spanish_cpd60389.pdf.
