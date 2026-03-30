Los [[Circuitos digitales]] que se han tratado hasta se caracterizan por que su salida está completamente determinada por los valores de entrada. Este tipo de circuito es *combinacional*.

- Se determina un resultado para cada combinación de valores de entrada.
- Se busca minimizar las funciones usando técnicas como las vistas en [[Minimización de funciones de conmutación]].
---
Qué mejor ejemplo para un circuito combinacional que el renombrado *1-bit half-adder*, que toma dos entradas y produce su salida y un *acarreo*.

![[Pasted image 20260320170637.png]]

Si pensamos en el circuito digital correspondiente, es bastante claro que:
$$
S=A\oplus B\ \text{ y } C=AB
$$
Podemos llevar esto aún más lejos y definir el *full-adder*:

![[Pasted image 20260320171320.png]]Tenemos dos funciones conmutación $C_{i+1}$ y $S$ que dependen de tres entradas; un acarreo inicial y dos bits.
Podemos hacer lo mismo que con el half-adder, pero pues ya hicimos la chamba, pensemos en otra manera. 
- El resultado debería ser la suma de $A$ y $B$ sumada con $C_{i}$
- El acarreo $C_{i+1}$ debería resultar de sumar dos o más 1s.
Podemos entonces usar dos half-adders para representarlo:
- Encadenas las sumas para sacar $S$.
- Usar un *OR* con los acarreos para obtener $C_{i+1}$.

![[Lógica combinacional 2026-03-20 17.23.33.excalidraw|999]]
Y podemos construir sumadores de bits arbitrarios usando este diseño y colocándolos conectados en paralelo.
![[Pasted image 20260320174938.png]]

---

El poder de esto está en que todos los circuitos complejos están construídos sobre *módulos* que realizan operaciones sencillas.