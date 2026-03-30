En la actualidad trabajamos con *sistemas numéricos posicionales*, donde cada cifra dentro de un número tiene una aportación distinta dependiendo de su posición.

En estos sistemas, todo número puede ser descompuesto como la suma del producto del valor intrínseco de cada cifra con la **base** elevada a su posición. Por ejemplo
$$
2005 = 2\times 10^{3} + 0\times 10^{2} + 0\times 10^{1} +5\times 10^{0}
$$
Para una base $b$, existen $\{ 0,\dots,b-1 \}$ valores intrínsecos; en el caso de la famosa base 10, que es la que se nos enseña desde pequeños, estos valores van del uno al nueve.

### El interés particular de CompSci
En computación existe un interés particular en los sistemas numéricos posicionales con base 2, 8 y 16; esto puesto que es análogo a cómo opera un circuito: qué hacer cuando hay corriente y qué hacer cuando no la hay; para los sistemas base 8 y 16, resulta muy sencillo convertir de base 2 a ellos.