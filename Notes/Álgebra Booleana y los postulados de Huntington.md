*George Bool* se interesa en dotar a la lógica proposicional de un lenguaje algebraico formal.

*Edward Huntington* lo formaliza a como lo estudiamos hoy.

## Postulados de Huntington

Un **álgebra booleana $\mathbb{B}$** es una terna $(B,+,\cdot)$ donde $B$ es el conjunto con al menos dos elementos distintos, + la suma y $\cdot$ el producto. La suma es análoga al $\lor$ y el producto al $\land$ de la lógica proposicional.

- Se cumple que $B$ es cerrado bajo sus dos operaciones
- Existen elementos neutros para ambas operaciones $x+0=0$ y $x \cdot 1=x$
- Las operaciones son conmutativas y distributivas
- Para todo elemento $x$ existe un inverso $\bar{x}$ tal que $x+\bar{x}=1$ y $x \cdot \bar{x}=0$

La $\bar{}$ es análoga a la negación el la lógica proposicional y el 0 a $false$ y el 1 a $true$.

---
## Teoremas de la álgebra booleana
### 1. Idempotencia
Se cumple que:
- $x+x=x$
- $x \cdot x=x$
### 2. Aniquilación
- $x+1=1$ (x or 1 siempre es 1)
- $x \cdot 0 =0$ (x and 0 siempre es 0)
### 3. Absorción
- $x+xy=x$

> [!example] Demostración
>$$
\begin{gathered}
x+xy = x \cdot 1 +xy \\\\
= x(1+y) \\\\
= x(y+1) \\\\
=x\cdot 1 \\\\
=x
\end{gathered}
>$$

- $x(x+y)=x$ (se sigue del anterior)
### 4. Involución
- $\overline{(\overline{x})}=x$
### 5. Eliminación
- $x+\overline{x}y=x+y$
- $x(\overline{x}+y)=xy$

> [!example] Demostración
> $$
\begin{align*}
x+\overline{xy} &= x+xy + \overline{x}y &\text{Por teorema 2} \\
&= x+0 + xy +\overline{x}y \\
&= x+ \overline{x}x + xy + \overline{x}y \\
&= x x +  \overline{x}x + xy + \overline{x}y \\
&= x x + x y + \overline{x}x + \overline{x}y \\
&= x \cdot (x+y) + \overline{x}\cdot (x+y) \\
&= (x+y)(x+\overline{x}) \\
&=(x+y) \cdot 1 \\
&= x+y
\end{align*}
> $$

### 6. Asociatividad
- $x+(y+z) = (x+y)+z$
- $x\cdot (y\cdot z) = (x\cdot y)\cdot z$

### 7. Consenso
- $xy + \overline{x}z+yz=xy +\overline{x}z$

> [!example] Demostración
> $$
\begin{align*}
xy + \overline{x}z+yz &= xy + \overline{x}z+yz \cdot 1 \\
&=  xy + \overline{x}z+yz \cdot (x + \overline{x}) \\
&=  xy + \overline{x}z+xyz +\overline{x}yz \\
&= xy(1+z) + \overline{x}z(1+y) \\
&= xy \cdot 1+ \overline{x}z \cdot 1&\text{Por teorema 2} \\
&= xy + \overline{xz}
\end{align*}
> $$

- $(x+y)(\overline{x}+z)(y+z)=(x+y)(\overline{x}+z)$
La demostración es análoga a la anterior

### 8. Leyes De Morgan
- $\overline{x+y}= \overline{x} \cdot \overline{y}$
- $\overline{x \cdot y}= \overline{x}+ \overline{y}$

