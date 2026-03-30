# Preguntas
- Emiliano García Bollás
---
1. ¿Qué es un **Circuto Secuencial Tolerante a Fallos**?
	¿Podemos hacer tolerante a fallos el contador y el bando de registros que construímos?
>
	- Se trata de un sistema diseñado para seguir funcionando aún cuando se sufren errores internos.
	- Sí, de hecho, se haría uso de un método conocido como *Triple Modular Redundancy*, que consiste de replicar un circuito tres veces y usar algún mecanismo para determinar quién genera la salida. Así, en caso de que uno falle, los demás sostienen potencialmente el output esperado.
>
2. Existen dos tipos de máquinas de estado finito que usan *Flip-Flops.* ¿Cuáles son?
	¿En qué se diferencían?
>
	- Son la *Máquina de Moore* y la *Máquina de Mealy*.
	En la primera, las salidas dependen únicamente del estado actual de la máquina; mientras que en la segunda estas dependen no solamente del estado actual, sino también de las entradas.
	La primera suele requerir más estados que la segunda, además de que es relativamente más estable en comparación con la segunda, que pese a perder un poco de estabiliad, tiene un tiempo de reacción menor a las entradas.
>

1. ¿Qué es el **Sesgo de Reloj (Clock Skew)**?, ¿este fenómeno impacta la frecuencia máxima de un sistema?
>
	- El *Clock Skew* es la diferencia de tiempo de llegada de alguna señal del reloj que se da entre diferentes componentes por longitudes de circuito distintas o configuraciones diferentes de compuertas lógicas. Y sí, el impacto en la frecuencia máxima del sistema es norme, pues reduice el tiempo efectivo en el que la lógica combinacional pueda procesar los datos, suscitando situaciones análogas a las *race conditions*.
>
2. En el contexto de los *biestables*: ¿Qué es el problema de la **meta-estabilidad**?, ¿cómo puedes reducir la meta estabilidad en sistemas reales?
	- La metaestabilidad sucede cuando los tiempos de *setup* y de *hold* de un *Flip-Flop* son violados. El biestable se encuentra oscilando o en un estado indefinido entre los valores binarios antes de poder estabilizarse, que puede resultar en errores de lógica.
	Es posible reducirla haciendo uso de *sincronizadores*, que consisten de cadenas de dos o más *Flip-Flops* en serie; o bien aumentando la frecuencia del reloj.