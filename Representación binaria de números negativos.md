¿Cómo hacemos que un número representado en base 2 sea negativo?
Ciertamente no podemos precederle de un $-$ o siquiera un $+$ como hacemos cotidianamente.

Algunos métodos incluyen
### Signo y magnitud
Consiste de dedicar un único *bit* (*bi*nary digi*t*) a actuar como un signo, por convención, $+=0$ y $-=1$.
$$
1\ 101_{2} = -5_{10}
$$
Este bit que se coloca hasta la izquierda **no** tiene asociada ninguna potencia de dos, y se decide inicialmente que contendrá únicamente información sobre el signo del número.

El problema con esto es que... pues hay dos ceros... $1\ 0$ o $0\ 0$, que es incorrecto e imposible. Esto es problemático para cuando se quieren hacer comparaciones con el cero, pues ahora tendrían que hacerse dos.

### Complemento a 1
Es útil pensar en la generalización:

El complemento a $b-1$ de un número $r_{b}$ con $k$ dígitos es:
$$
C_{b-1}(r_{b})= (b-1_{k}\dots b-1_{1})-r_{b}
$$
Viéndolo en un ejemplo, el complemento a 1 de $01101_{2}$ se computa como:
$$
C_{1}(01101_{2}) = 11111 -01101=10010_{2}
$$
Que, resultó ser la inversión de cada bit.
Pero, jaja, el problema con el 0 se mantiene, pues es tanto $0\dots 0$ como $1\dots 1$.

### Complemento a 2
Se hace con fin de liberarse del problema de que el 0 se pueda representar de dos maneras.
La generalización se sigue de la anterior, ajustando únicamente los índices
$$
C_{b}(r_{b})= (10_{k}\dots 0_{1})-r_{b}
$$
Que resulta ser el complemento a $b-1$, pero agregando 1 :o.
Habíamos visto que el complemento a 1 de un número en binario es ese número pero con sus bits invertidos, así que solo sumamos 1.
$$
C_{2}(01101_{2})=10010+00001=10011_{2}
$$
