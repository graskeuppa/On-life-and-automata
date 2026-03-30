Mirando a la frecuencia de operación de un CPU, se puede calcular el tiempo en que un procesador tarda en ejecutar un programa

### Tiempo total de ejecución $T$
Sea $T$ el *tiempo total de ejecución* de un programa, $C$ el *número de ciclos necesarios para ejecutarlo* y $D$ la *duración de cada ciclo*.
$$
T=C \cdot D
$$
Otro modo de medir el tiempo de CPU es,
$$
T= \frac{C}{F}
$$
Donde $F=\frac{1}{D}$ es la *frecuencia de operación del reloj*.

### Tiempo promedio de ciclos por instrucción $R$

Sea $R$ el *tiempo promedio de ciclos por instrucción*, $I$ el *número de instrucciones* y C el de arriba:
$$
\begin{gathered}
R=\frac{C}{I} \\\\
C=R \cdot I
\end{gathered}
$$
Reemplazando en la ecuación anterior de esta sección,
$$
\begin{gathered}
T= R \cdot I \cdot D \\\\
\text{O bien} \\\\
T = \frac{R \cdot I}{F}
\end{gathered}
$$
La expresión mide $\frac{segundos}{programa}$.

> [!NOTE] Factores que influyen en el desempeño
> 1. Frecuencia del reloj
> 	- Depende del hardware
> 2. Cantidad de ciclos por cada instrucción
> 	- Depende de la organización y arquitectura
> 3. Contador de instrucciones por programa
> 	- Arquitectura del conjunto de instrucciones


