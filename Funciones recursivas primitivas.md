# Funciones recursivas primitivas (r.p.)
---

Otro modelo de cómputo con equivalencia a la [[Máquina de Turing]].

> [!NOTE] Primitiva
> No axiomática, pero está en línea con la intuición y se dan por hechas.

- Cero: $\mathbb{N}^{0}\to \mathbb{N}$ , denotada $0()$ es r.p. de grado 0
- F. Sucesor $S:\mathbb{N}\to \mathbb{N}$ es r.p. de grado 1

> [!NOTE] Grado
> El grado de una función es el número de argumentos que recibe.

- Para cualesquiera naturales $k,n \in \mathbb{N}$, $1\leq k\leq n$, la *proyección* $\pi^{n}_{{k}}:\mathbb{N}^{n}\to \mathbb{N}$ es r.p. ($n$ elementos, extrae el $k-$ésimo elemento).
$$
(x_{1},\dots,x_{n}) \to x_{k}
$$
Estamos definiendo a las funciones recursivas como un modelo de cómputo, ¡pero bajo un supuesto de que ya son recursivas! 
Vuelve a aparecer el [[Problema de la circularidad]].