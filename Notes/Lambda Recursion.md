Recursion in [[Lambda Calculus]] is achieved by using a function which calls a function $y$ and then regenerates itself: meet the *Y combinator*:
$$
Y \equiv \lambda y.(\lambda x.y(xx)(\lambda x.y(x x))
$$
Applied to a function $f$:
$$
\begin{align*}
Yf &= (\lambda x.f(x x)(\lambda x.f(x x))) \\
&=f((\lambda x.f(x x)) (\lambda x.f(x x))) \\
&= f(Yf)
\end{align*}
$$
# Simple recursion

Say we wanted to make a function that adds up the first $n$ natural numbers.
This addition can be seen as:
$$
\sum_{i=0}^{n} i = n+\sum_{i=0}^{n-1}i = n+(n-1)+(n-2)+\dots+3+2+1+0
$$
So let's thing of a funtion in blocks:
- If $n$ is $0$ then the sum is also $0$.
- If it isn't, then take $n-1$ and check with it the same conditions, add $n$ to that.
The function ends up being:
$$
R \equiv \lambda rn.Zn 0 (nS(r(Pn)))
$$

- The function takes in $r$ and $n$, with $r$ being the recursive call and $n$ the number to add up to.
- $Zn$ checks if $n$ is $0$, if it is, it returns $0$; if it isn't, it adds n to the recursive call of the function with the predecessor of $n$, $n-1$.

This is identical to doing 

```cpp
int sum (n) {
if (n == 0) return 0;
return n + sum(n-1);
}
```

Let's add up to $3$:

$$
\begin{align*}
YR 3 &= R(YR)3 \\
&=  (\lambda rn.Zn 0 (nS(r(Pn))))(YR)(3) \\
&= (\lambda n.Zn 0 (nS((YR)(Pn))))3 \\
&=Z 3 0(3S(YR(P 3))) \\
&=3S(YR 2) \\
&= 3S 2S 1S 0 \\ 
&=6
\end{align*}
$$

# Tail recursion
Taking the last function as an example, notice how the last line of the expression is $3S 2 S 1 S 0$, the function has to wait until all other numebers are defined to make the addition; if we were to run $YR 1000$ not a single addition will be made until the last $YRN$ is evaluated and returns 0.

How do we solve this?
Use an **accumulator**.

```cpp
int tailSum (n, accumulator) {
	if (n == 0) return accumulator;
	return tailSum (n-1, accumulator + n);
}
```

All the work is being done on the accumulator!

So, to change the $R$ function to use tail recursion, we consider three arguments:
- $r$, the recursive loop
- $n$, the number given in the first place
- $a$, the accumulator

$$
\begin{align*}
R^{!} \equiv \lambda rna.Zna(r(Pn)(nSa))
\end{align*}
$$
The `cpp` function above perfectly describes what this is doing.

Let's run an example! Using $n=3$ and $a=0$:

$$
\begin{align*}
YR^{!}3 &= R^{!}(YR^{!})(3)(0)\\
&= [\lambda rna.Zna(r(Pn)(nSa))](YR^{!})(3)(0)\\
&= [\lambda na.Zna((YR^{!})(Pn)(nSa))](3)(0) \\
&= [\lambda a.Z 3a((YR^{!})(P 3)(3Sa))](0) \\
&= Z 3 0 ((YR^{!})(P 3) (3S 0)) \\
&= YR^{!}(2)(3) \\
&= R^{!}(YR^{!})(2)(3) \\
&= YR^{!}(1)(5) \\
&= YR^{!}(0)(6) \\
&= 6
\end{align*}
$$


Sean:
$$
\begin{align*}

\overline{0}&=\lambda fn.n \\
\overline{1}&=\lambda fn.f(1)  \\
\overline{2}&=\lambda fn.f(2) \\
&\dots \\
succ&= \lambda n.\lambda sz.sn \\
nil & \equiv \lambda nc.n \\
cons & = \lambda htcn.ch(tcn) \\
[a] &= \text{cons a nil} \\
[a,b] &= \text{cons a(cons b nil)} \\
&\dots
\end{align*}
$$
Crea una expresión $\lambda$ que calcule una lista infinta de sucesores de un $n$ en orden inverso. Usa recursión de cola para construir la lista.