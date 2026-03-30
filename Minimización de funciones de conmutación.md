Las [[Funciones de conmutación]] no tienen expresiones únicas, existen diversas maneras de expresar la misma función. Entre estas, son de interés aquellas que son *mínimas*.

---
Puedes intentar reducir función por medio de *manipulación algebráica*, en línea con los axiomas y teoremas vistos en [[Álgebra Booleana y los postulados de Huntington]], sin embargo, esto no es una labor trivial.

La otra, es usar el método gráfico inventado por Maurice Karnaugh

### Los mapas de Karnaugh
La técnica consiste en acomodar la tabla de verdad de una función en un mapa cuadriculado, de forma que queden contiguas las entradas de la tabla cuyo índice difiere en sólo un bit y luego agrupas las celdas de adentro siguiendo un conjunto de reglas:
- Los grupos no pueden contener 0
- Pueden crecer vertical y horizontalmente
- Deben de contener un número de celdas de la forma $2^{k}$ (potencias de 2)
- Cada grupo debe ser lo más grande posible
- Todo 1 debe estar en al menos un grupo
- Los grupos pueden tener intersección no vacía
- Intenta minimizar el número de grupos
- Si permanece como 0, se niega
- Si permanece como 1, se mantiene
- Si cambia de 0 a 1 o de 1 a 0, se elimina

Por ejemplo:
![[Pasted image 20260316215740.png]]
Es el mapa correspondiente a la función que se usó de ejemplo en [[Funciones de conmutación]].
$$
\begin{align*}
F(x_{2},x_{1},x_{0}) = &\overline{x_{2}x_{1}x_{0}}+\overline{x_{2}}x_{1}\overline{x_{0}}+\overline{x_{2}}x_{1}x_{0}+ \\
&x_{2}\overline{x_{1}}x_{0}+x_{2}x_{1}\overline{x_{0}}+x_{2}x_{1}x_{0}
\end{align*}
$$
¿Cómo se interpreta esto entonces?
Por cada grupo, revisa qué cambia y qué no.

En este ejemplo hay tres grupos, revisemos uno por uno

1. $x_{2}$ se queda en 0, se niega. $x_{0}$ se queda en 0, se niega. $x_{1}$ cambia, se elimina: $\overline{x_{2}x_{0}}$.
2. $x_{2}$ se queda en 1, se mantiene. $x_{0}$ se queda en 1, se mantiene, $x_{1}$ cambia, se elimina: $x_{2}x_{0}$
3. $x_{2}$ cambia, se elimina. $x_{1}$ se queda en 1, se mantiene. $x_{0}$ cambia, se elimina: $x_{1}$
Por lo tanto, $F(x_{2},x_{1},x_{0})=\overline{x_{2}x_{0}}+x_{2}x_{0}+x_{1}$

### Método de Quine-McCluskey
Se trata de un método algorítmico que se deshace de las ocasionales fallas del método de Karnaugh; es particularmente útil cuando hay que reducir funciones con más de cinco variables.

Se construye por medio de los *implicantes primos* de la expresión original dada en *mintérminos*.
Se construye una tabla con los renglones de la tabla de verdad de la función y se les agrupa por su peso de **Hamming** (la cantida de unos en su expresión binaria).

**PENDIENTE**