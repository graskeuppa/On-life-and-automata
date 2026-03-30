Siguiendo lo que mencionaba antes en [[Sistemas numéricos posicionales]], veamos cómo hacer conversiones entre los sistemas numéricos.

### Base 2 <-> Base 10

> [!example] Binario -> Decimal
> Para pasar un número en base 2 a base 10:
> $$
010_{2} = 0 \times 2^{2} + 1 \times 2^{1} + 0 \times 2^{0}=2_{10}
> $$


La operación inversa lleva un par más de pasos; dado un número $n_{10}$, su expresión equivalente en base 2 se obtiene aplicando el [[Algorítmo de Euclídes]] a este número tantas veces sea necesario hasta que el cociente sea 0, la expresión binaría serán los residuos en orden opuesto.

Por ejemplo:

> [!example] Decimal -> Binario
> Pasando 21 a binario
> $$
\begin{gathered}
21 = 2(10) + 1 \\\\
10 = 2(5) + 0 \\\\
5 = 2(2) + 1 \\\\
2 = 2(1) + 0 \\\\
1 = 2(0) + 1 \\\\
\end{gathered}
> $$
>Entonces, tomando los residuos en orden reverso, $21_{10} = 10101_{2}$.

Esto es cierto también para números en cualquier otra base.

### Base 2 <-> Base 8 y 16

Probablemente las conversiones más sencillas.

> [!example] Binario -> Octal
> Agrupa, de izquierda a derecha y de tres en tres, los bits del número y escribe su valor haciendo crossreference con la tabla de valores.
> 
| Oct | Bin | Oct | Bin | Oct | Bin | Oct | Bin |
| ----- | ------- | ----- | ------- | ----- | ------- | ----- | ------- |
| 0     | 000     | 2     | 010     | 4     | 100     | 6     | 110     |
| 1     | 001     | 3     | 011     | 5     | 101     | 7     | 111     |
Así, por ejemplo,
>$$
101001_{2} = 101 \ 001_{2} = 5\ 1_{8} = 51_{8}
>$$

Y lo mismo es cierto para la base hexadecimal:

> [!example] Binario -> Hexadecimal
> Igual que en la anterior, sólo que en grupos de 4.![[Pasted image 20260312165847.png]]
>Por ejemplo, 
>$$
101001_{2} = 10 \ 1001_{2} = 0010\ 1001_{2} = 2\ 9_{16} = 29_{16}
>$$

Y en sentido contrario el proceso es el mismo, haz crossreference con la tabla por cada dígito en base 8 o 16 y reemplaza.


