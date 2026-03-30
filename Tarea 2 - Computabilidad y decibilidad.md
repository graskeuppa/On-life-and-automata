# Tarea 2 - Computabilidad y decibilidad
- Belmont Zúñiga Javier
- García Bollás Emiliano
- Reyes Ríos Julián Humberto
---
1. Da un procedimiento eficaz intuitivo para encontrar las raíces de todos los polinomios sobre $\mathbb{R}$ de grado a lo más 1 (los de la forma $ax+b$ con $a\neq 0$).
	- No pueden escribir directamente la fórmula cuadrática.
	- Deben descomponer el procedimiento en pasos elementales.	
	- Deben indicar explícitamente: qué operaciones están permitidas, por qué el procedimiento termina, qué datos de entrada son necesarios.

> [!ABSTRACT]  Procedimiento eficaz para obtener las raíces de polinomios de la forma $ax+b$
> 1. Identifica a $a$ como el término multiplicado por una $x$
> 2. Identifica a $b$ como el término que se suma a $ax$.
> 3. Iguala el polinomio a $0$
 >4. Resta $b$ de ambos lados
 >5. Divide ambos lados entre $a$
 >6. El resultado está ahora del lado opuesto a donde está la $x$
 
Las operaciones elementales del proceso son tanto la suma como la multiplicación, pues de no serlo resulta imposible manipular los números para obtener las raíces. El procedimiento termina ya que el único elemento numérico ya no puede reducirse.

2. Da un procedimiento eficaz intuitivo para encontrar las raíces de todos los polinomios sobre $\mathbb{R}$ de grado a lo más 2 (los de la forma $ax^{2}+bx+c$).
	- No pueden escribir directamente la fórmula cuadrática.
	- Deben descomponer el procedimiento en pasos elementales.
	- Deben indicar explícitamente: qué operaciones están permitidas, por qué el procedimiento termina, qué datos de entrada son necesarios.

> [!ABSTRACT] Procedimiento eficaz para obtener las raíces de polinomios de la forma $ax^{2}+bx+c$
> 7. Identifica a $a$ como el número que tiene multiplicada una $x^2$
> 8. Identifica a $b$ como el número que tiene multiplicada una $x$ (no al cuadrado)
> 9. Identifica a $c$ como el número que no tiene multiplicado nada.
> 10. Eleva $b$ al cuadrado
>11. Multiplica 4 por $a$ y por $c$
>12. Resta el resultado de 4. del resultado de 5.
>13. Saca raíz cuadrada del resultado de la operación anterior
>14. En cuentas separadas, multiplica el resultado de la raíz por $1$ y por $-1$
>15. Resta $b$ a ambos
>16. Divide ambos entre  $2a$
>17. Iguala uno a $x_{1}$ y otro a $x_{2}$

De modo similar al ejercicio anterior, las operaciones elementales son la suma, resta, multiplicación, exponenciación y obtención de raíces, puesto que de no serlo es imposible alcanzar algún resultado relevante.
El procedimiento termina dado que las raíces ya no pueden reducirse más.

3. Muestra por qué las respuestas que diste para (1) y (2) son, de hecho, procedimientos eficaces en los términos de los requerimientos de Hilbert-Pasch.
Deben distinguir con claridad entre:
	- Operaciones matemáticas abstractas.
	- Acciones eficazmente ejecutables por una máquina matemática.

> [!TIP] Respuesta
> Las instrucciones de ambos procedimientos resultan ciertamente en un efecto, en particular, el de obtener las raíces de los polinomios dados; además,  los procedimientos están conformados por un conjunto de instrucciones que se siguen para resolver el problema. que no requieren de interpretación/juicio alguno, son elementales (no hay instrucción más pequeña) y están codificadas de modo que son relevantes para el problema.

4. Una máquina matemática se llamará circular (o con círculo/ciclo) si ya no es posible cambiar a otras configuraciones o si es una que imprime basura. Hay máquinas matemáticas que se quedan en la misma $m-$configuración y siguen haciendo bien su trabajo. ¿Por qué esas máquinas no son circulares?

> [!WARNING] Incongruencia en la definición de circularidad
>  No hay tal cosa como una máquina que se mantiene en un mismo estado y no es circular; la definición de circularidad está en conflicto con este hecho, puesto que una máquina será circular si se queda en un mismo estado o imprime basura.

5. Da la especificación de una máquina matemática (en forma tabular) que esté en un ciclo infinto (pero que no sea circular) y escriba SOLAMENTE las primeras 8 posiciones impares de la sucesión de Fibonacci; comenzando desde el índice cero: 0, 1, 1, 2, 3,... La máquina debe hacerlo usando **notación unaria**. Además, exhibe las descripciones instantáneas que describen a la máquina hasta llegar a esas primeras 8 posiciones, y haz lo mismo con las actualizaciones que sufre la cinta utilizando la notación de estados newtoniana.
Explica por qué sí o por qué no serán útiles los $E-$registros de la cinta $T$ para esta computación.

> [!TIP] Descripción
> Para esta máquina *hardcodearemos* las primeras 8 posiciones impares de la sucesión de Fibonacci usando notación unaria; como no habrá lógica de lectura (más allá de ver la celda vacía), no se usarán los $E-$registros.
> 
$q_{i_{n}}$ serán los estados que imprimen cada número, con $i$ siendo la posición impar de Fibonacci y $n$ el dígito del número.
>

| $q_{i} / S_{0}$     | $S_{0}$              |
| ------------------- | -------------------- |
| $q_{1_{I}}$         | $1,RR,q_{1_{e}}$     |
| $q_{1_{e}}$         | $0,RR,q_{3_{I}}$     |
| $q_{3_{I}}$         | $1,RR,q_{3_{II}}$    |
| $q_{3_{II}}$        | $1,RR,q_{3_{e}}$     |
| $q_{3_{e}}$         | $0,RR,q_{5_{I}}$     |
| $q_{5_{I}}$         | $1,RR,q_{5_{II}}$    |
| $q_{5_{II}}$        | $1,RR,q_{5_{III}}$   |
| $q_{5_{III}}$       | $1,RR,q_{5_{IV}}$    |
| $q_{5_{IV}}$        | $1,RR,q_{5_{V}}$     |
| $q_{5_{V}}$         | $1,RR,q_{5_{e}}$     |
| $q_{5_{e}}$         | $0,RR,q_{7_{I}}$     |
| $q_{7_{I}}$         | $1,RR,q_{7_{II}}$    |
| $q_{7_{II}}$        | $1,RR,q_{7_{III}}$   |
| $q_{7_{III}}$       | $1,RR,q_{7_{IV}}$    |
| $q_{7_{IV}}$        | $1,RR,q_{7_{V}}$     |
| $q_{7_{V}}$         | $1,RR,q_{7_{VI}}$    |
| $q_{7_{VI}}$        | $1,RR,q_{7_{VII}}$   |
| $q_{7_{VII}}$       | $1,RR,q_{7_{VIII}}$  |
| $q_{7_{VIII}}$      | $1,RR,q_{7_{IX}}$    |
| $q_{7_{IX}}$        | $1,RR,q_{7_{X}}$     |
| $q_{7_{X}}$         | $1,RR,q_{7_{XI}}$    |
| $q_{7_{XI}}$        | $1,RR,q_{7_{XII}}$   |
| $q_{7_{XII}}$       | $1,RR,q_{7_{XIII}}$  |
| $q_{7_{XIII}}$      | $1,RR,q_{7_{e}}$     |
| $q_{7_{e}}$         | $0,RR,q_{9_{I}}$     |
| $q_{9_{I}}$         | $1,RR,q_{9_{II}}$    |
| $q_{9_{II}}$        | $1,RR,q_{9_{III}}$   |
| $q_{9_{III}}$       | $1,RR,q_{9_{IV}}$    |
| $q_{9_{IV}}$        | $1,RR,q_{9_{V}}$     |
| $q_{9_{V}}$         | $1,RR,q_{9_{VI}}$    |
| $q_{9_{VI}}$        | $1,RR,q_{9_{VII}}$   |
| $q_{9_{VII}}$       | $1,RR,q_{9_{VIII}}$  |
| $q_{9_{VIII}}$      | $1,RR,q_{9_{IX}}$    |
| $q_{9_{IX}}$        | $1,RR,q_{9_{X}}$     |
| $q_{9_{X}}$         | $1,RR,q_{9_{XI}}$    |
| $q_{9_{XI}}$        | $1,RR,q_{9_{XII}}$   |
| $q_{9_{XII}}$       | $1,RR,q_{9_{XIII}}$  |
| $q_{9_{XIII}}$      | $1,RR,q_{9_{XIV}}$   |
| $q_{9_{XIV}}$       | $1,RR,q_{9_{XV}}$    |
| $q_{9_{XV}}$        | $1,RR,q_{9_{XVI}}$   |
| $q_{9_{XVI}}$       | $1,RR,q_{9_{XVII}}$  |
| $q_{9_{XVII}}$      | $1,RR,q_{9_{XVIII}}$ |
| $q_{9_{XIX}}$       | $1,RR,q_{9_{XX}}$    |
| $q_{9_{XX}}$        | $1,RR,q_{9_{XXI}}$   |
| $q_{9_{XXI}}$       | $1,RR,q_{9_{XXII}}$  |
| $q_{9_{XXII}}$      | $1,RR,q_{9_{XXIII}}$ |
| ...                 | ...                  |
| $q_{9_{XXXIV}}$     | $1,RR, q_{9_{e}}$    |
| $q_{9_{e}}$         | $0,RR,q_{11_{I}}$    |
| $q_{11_{I}}$        | $1,RR,q_{11_{II}}$   |
| $q_{11_{II}}$       | $1,RR,q_{11_{III}}$  |
| $q_{11_{III}}$      | $1,RR,q_{11_{IV}}$   |
| $q_{11_{IV}}$       | $1,RR,q_{11_{V}}$    |
| $q_{11_{V}}$        | $1,RR,q_{11_{VI}}$   |
| ...                 | ...                  |
| $q_{11_{LXXXIX}}$   | $1,RR,q_{11_{e}}$    |
| $q_{11_{e}}$        | $0,RR,q_{13_{I}}$    |
| $q_{13_{I}}$        | $1,RR,q_{13_{II}}$   |
| $q_{13_{II}}$       | $1,RR,q_{13_{III}}$  |
| $q_{13_{III}}$      | $1,RR,q_{13_{IV}}$   |
| $q_{13_{IV}}$       | $1,RR,q_{13_{V}}$    |
| $q_{13_{V}}$        | $1,RR,q_{13_{VI}}$   |
| ...                 | ...                  |
| $q_{13_{CCXXXIII}}$ | $1,R R, q_{13_{e}}$  |
| $q_{13_{e}}$        | $0, R R, q_{15_{I}}$ |
| $q_{15_{I}}$        | $1,RR,q_{15_{II}}$   |
| $q_{15_{II}}$       | $1,RR,q_{15_{III}}$  |
| $q_{15_{III}}$      | $1,RR,q_{15_{IV}}$   |
| $q_{15_{IV}}$       | $1,RR,q_{15_{V}}$    |
| $q_{15_{V}}$        | $1,RR,q_{15_{VI}}$   |
| ...                 | ...                  |
| $q_{15_{DCX}}$      | $1, R R, q_{15_{e}}$ |
| $q_{15_{e}}$        | $0, R R, q_{1_{I}}$  |

> [!EXAMPLE] Estados de la cinta en notación newtoniana
> $\sqcup \sqcup \sqcup \sqcup \sqcup \sqcup \sqcup \sqcup \dots$
> $\sqcup q_{1_{I}} \sqcup \sqcup \sqcup \sqcup \sqcup \sqcup \dots$
> $1 \sqcup \sqcup q_{I_{e}}\sqcup  \sqcup \sqcup \sqcup \sqcup \dots$
> $1 \sqcup 0 \sqcup \sqcup q_{3_{I}} \sqcup \sqcup \sqcup \dots$
> $1 \sqcup 0 \sqcup 1  \sqcup \sqcup q_{3_{II}} \sqcup \dots$
> $1 \sqcup 0 \sqcup 1  \sqcup 1 \sqcup \sqcup q_{3_{e}}\dots$
> $\dots$
> $1 \sqcup 0 \sqcup 1  \sqcup 1 \sqcup 0 \sqcup 1 \sqcup 1 \sqcup 1 \sqcup 1 \sqcup 1 \sqcup 0 \sqcup \underbrace{1 \sqcup 1 \sqcup\dots\sqcup 1}_{\text{13 veces}}\sqcup 0 \sqcup \underbrace{1 \sqcup 1 \sqcup \dots \sqcup 1}_{\text{34 veces}}\sqcup 0$
> $\sqcup \ \underbrace{1 \sqcup 1 \sqcup \dots \sqcup 1}_{\text{89 veces}}\sqcup 0 \sqcup\ \underbrace{1 \sqcup 1 \sqcup \dots \sqcup 1}_{\text{233 veces}}\sqcup 0 \sqcup\ \underbrace{1 \sqcup 1 \sqcup \dots \sqcup 1}_{\text{610 veces}} \sqcup 0\sqcup 1 \sqcup 0 \sqcup 1\sqcup 1\sqcup \dots$


6. ¿Qué significa que las instrucciones de la máquina matemática sean "atómicas"? Relaciona esto con los requerimientos de Pasch y Hilbert.

> [!TIP] Atomicidad en las instrucciones
> Significa que las instrucciones no están sujetas a la interpretación o creatividad de aquél que las realiza, se encuentran definidas dentro de operaciones que la máquina entendería, son indivisibles y además son potencialmente infinitas.

7. Para la máquina matemática que imprime indefinidamente 010101... y que está en el ejemplo 1 de la sección 4.A de las notas, muestra que es posible construir otra máquina matemática pero con menos $m-$configuraciones.

> [!NOTE] Reducción de estados
>Con completa inspiración en la solución al mismo problema que Turing presenta en *ON COMPUTABLE NUMBERS, WITH AN APPLICATION TO THE ENTSCHEIDUNGSPROBLEM (1936)*, es posible reducir los cuatro estados mentales a uno:

| $q_{0} / S_{i}$ | $S_{0}$         | $S_{1}$            | $S_{2}$            |
| --------------- | --------------- | ------------------ | ------------------ |
| $q_{0}$         | $N,S_{1},q_{0}$ | $R R,S_{2}, q_{0}$ | $R R, S_{1},q_{0}$ |

8. Da la especificación de una máquina matemática que calcule igualdad de números en notación unaria. Es decir, dada una entrada $T_{1}=1\sqcup 1 \sqcup 0 \sqcup 1 \sqcup 1$ la cinta resultante debe ser $T_{1}=1\sqcup 1 \sqcup 0 \sqcup 1 \sqcup 1 \sqcup V$. En otro caso, si la entrada es $T_{2}= 1 \sqcup 1 \sqcup 0 \sqcup 1$ el resultado debe ser $T_{2}= 1 \sqcup 1 \sqcup 0 \sqcup 1 \sqcup F$.

> [!NOTE] Descripción
> Por medio de siete configuraciones (y una para representar el desconectar la máquina) se realizan comparaciones entre los dígitos de los números unarios.  $I$ es el carácter de inicio, $S_{0},S_{1},S_{2}$ son $\sqcup,0,1$ respectivamente y $S_{V},S_{F}$ son V y F.

| $q_{i}/S_{i}$ | $I$         | $S_{0}$         | $S_{1}$         | $S_{2}$         | $S_{3}$         | $S_{4}$         | $S_{v}$         | $S_{F}$         |
| ------------- | ----------- | --------------- | --------------- | --------------- | --------------- | --------------- | --------------- | --------------- |
| $q_{0}$       | $-$         | $S_{0},L,q_{2}$ | $S_{1},R,q_{1}$ | $S_{2},R,q_{1}$ | $-$             | $-$             | $-$             | $-$             |
| $q_{1}$       | $-$         | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ | $S_{3},R,q_{0}$ |
| $q_{2}$       | $-$         | $-$             | $S_{1},L,q_{3}$ | $S_{2},L,q_{2}$ | $-$             | $-$             | $-$             | $-$             |
| $q_{3}$       | $I,R,q_{6}$ | $S_{0},L,q_{3}$ | $S_{1},L,q_{3}$ | $S_{2},L,q_{3}$ | $S_{4},R,q_{4}$ | $S_{4},L,q_{3}$ | $S_{V},L,q_{3}$ | $S_{F},L,q_{3}$ |
| $q_{4}$       | $-$         | $S_{0},R,q_{5}$ | $-$             | $-$             | $S_{2},L,q_{2}$ | $-$             | $-$             | $-$             |
| $q_{5}$       | $-$         | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ | $S_{V},L,q_{f}$ |
| $q_{6}$       | $-$         | $S_{0},R,q_{7}$ | $S_{1},R,q_{6}$ | $S_{2},R,q_{6}$ | $S_{3},R,q_{6}$ | $S_{4},R,q_{6}$ | $S_{V},R,q_{6}$ | $S_{F},R,q_{6}$ |
| $q_{7}$       | $-$         | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ | $S_{F},L,q_{f}$ |
| $q_{f}$       | Fin         | Fin             | Fin             | Fin             | Fin             | Fin             | Fin             | Fin             |
9. Define el problema **CIRC?** y responde: ¿por qué conduce a una contradicción cuando se alimenta la máquina con su propio número descriptor?

> [!WARNING] El problema CIRC? y su inevitable contradicción
> El problema **CIRC?** se interesa en decidir si una máquina matemática $M$ con número descriptor $n$ contiene o no un círculo, mismo que se entiende como la incapacidad de una máquina matemática de cambiar de estado mental.
>
> Este proceso de decisión es posible gracias a la existencia de una máquina $M'$ que simula el comportamiento de cada máquina a partir de su número descriptor para determinar si estas máquinas tienen círculos o no; eventualmente, $M'$ alcanzará el número descriptor de sí misma y deberá simularse, lo que llevará a que la simulación eventualmente llegue a su mismo número descriptor y se simule a sí misma; esto inductivamente hasta el infinito.
>
> La máquina $M'$ jamás cambiará de estado una vez que se evalúe a sí misma. 
La máquina $M'$ es en sí circular; por tanto no existe una máquina que pueda revisar que otras máquinas no tengan círculos, puesto que la misma lo es.
