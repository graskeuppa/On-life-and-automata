Se les llama *funciones de conmutación* a aquellas que toman al $0$ y al $1$ del álgebra booleana y los operan para obtenerlos de nuevo.

Estas funciones se pueden especificar por medio de expresiones algebráicas usando las convenciones vistas en [[Álgebra Booleana y los postulados de Huntington]]; o bien de manera tabular.

---

Por ejemplo, mírese la siguiente función dada de forma tabular:
![[Pasted image 20260316192133.png]]

El análisis es análogo a las funciones por casos, nos interesa ver qué condiciones son necesarias para obtener $1$ dada cualquier entrada. 

$$
\begin{align*}
F(x_{0},x_{1},x_{2}) = 
c_{0}\overline{x_{2}x_{1}x_{0}}+c_{1}\overline{x_{2}x_{1}}x_{0} &+ \\
c_{2}\overline{x_{2}}x_{1}x_{0}+c_{3}\overline{x_{2}}x_{1}x_{0} &+ \\
c_{4}x_{2}\overline{x_{1}x_{0}}+c_{5}x_{2}\overline{x_{1}}x_{0} &+ \\
c_{6}x_{2}x_{1}\overline{x_{0}}+c_{7}x_{2}x_{1}x_{0}
\end{align*}
$$
Recordando la notación para la conjunción y disyunción, armamos la función precediendo cada término con una constante $c_{i}$ que indicará si está o no presente en la expresión completa.

Nota que en la notación de función incluímos todas las combinaciones, inclusive las que no dan 1, para ellas, el índice que precede la expresión correspondiente sería 0, así:

$$
\begin{align*}
F(x_{2},x_{1},x_{0}) = &\overline{x_{2}x_{1}x_{0}}+\overline{x_{2}}x_{1}\overline{x_{0}}+\overline{x_{2}}x_{1}x_{0}+ \\
&x_{2}\overline{x_{1}}x_{0}+x_{2}x_{1}\overline{x_{0}}+x_{2}x_{1}x_{0}
\end{align*}
$$
---
### Suma de productos v. Producto de sumas
La simplificación de la función de la sección anterior resulta de ver qué combinaciones de estados de la función resultan en $1s$ y despreciar de aquellas que culminan en 0. 
A los productos de arriba se les llama *mintérminos*, cada uno etiquetado $m_{i}$, la función que obtuvimos se puede ver como:
$$
F(x_{2}x_{1}x_{0})=m_{0}+m_{2}+m_{3}+m_{5}+m_{6}+m_{7}=\sum_{i\in \{ 0,2,3,5,6,7 \}}m_{i}
$$
Esta expresión es la **Forma Canónica Normal *Disjuntiva* (CDNF)**.

Pero como muchas cosas en la vida, existe cierta dualidad en esta definición, ya que lo podemos ver igual como el producto de sumas, llamados *maxtérminos*, mismos que se etiquetan $M_{i}$. Construímos estas expresiones fijándonos en que casos las variables negadas llevan a una evaluación en 0:
$$
\begin{align*}
F(x_{2}x_{1}x_{0}) &= (x_{2}+x_{1}+\overline{x_{0}})(\overline{x_{2}}+x_{1}+x_{0}) \\
&=M_{1}\cdot M_{4} \\
&= \prod_{i \in \{ 1,4 \}}M_{i}
\end{align*}
$$
Y a esta forma se llama **Forma Canónica Normal *Conjuntiva* (CCNF)**.
Y claro:
$$
\sum_{i\in \{ 0,2,3,5,6,7 \}}m_{i}=\prod_{i \in \{ 1,4 \}}M_{i}
$$
