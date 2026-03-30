What's the next logical steps for [[Lambda Calculus]] after looking at [[Lambda Functions]]?
Why, arithmetic of course!

---
# Numerals
Remember **Peano**? 
Numbers start with the same notion he used to define $\mathbb{N}$, supposing the existence of a 0 and computing its *successors*.
$$
0\equiv\lambda s.\lambda z.z=\lambda sz.z
$$
Notice how this function has two arguments, this is analogous to having $f(x,y)$. We abbreviate it to $\lambda sz.z$, with $s$ being the first substitution and $z$ the second.
$$
\begin{align*}
0 &\equiv \lambda sz.z \\
1 &\equiv \lambda sz.s(z) \\
2 &\equiv \lambda sz.s(s(z)) \\
3 &\equiv \lambda sz.s(s(s(z))) \\\
&\dots
\end{align*}
$$
Which makes perfectly good sense, but how is the *successor function* defined?
$$
\begin{align*}

S &\equiv \lambda w.\lambda y.\lambda x.y(wyx)\\
&=\lambda wyx.y(wyx)
\end{align*}
$$
*What. The. Fuck*
Let's break it down:
- The first argument, $w$, is the current numeral
- The second, $y$, is the function to apply
- The third, $x$, the starting value

Let's see it in action:
$$
\begin{align*}

 S 0 &\equiv [\lambda wyx.y(wyx)](\lambda sz.z) \\
&= \lambda yx.y((\lambda sz.z)yx) \\
&= \lambda yx.y((\lambda z.z)x) \\ 
&= \lambda yx.y(x) \\ 
&\equiv \lambda sz.s(z) \equiv 1
\end{align*}
$$
And now for a more complex one:
$$
\begin{align*}
S 1 &\equiv[\lambda wyx.y(wyx)](\lambda sz.s(z)) \\
&= \lambda yx.y((\lambda sz.s(z))yx) \\
&= \lambda yx.y((\lambda z.y(z))x) \\
&= \lambda yx.y(y(x)) \\
& \equiv \lambda sz.s(s(z)) \equiv 2
\end{align*}
$$
---
## Basic operations
Being able to compute the succesor of a number isn't much use if we can't use that to make some other abstractions, let's look at the most basic arithmetic operations.

### Addition
Think of $2+3=5$, we can achieve the same result by computing $s(s(3))=s(4)=5$. 
$$
\begin{align*}
2S 3 & \equiv \underbrace{[\lambda sz.s(s(z))]}_{2} \underbrace{[\lambda wyx.y(wyx)]}_{S} \underbrace{[\lambda uv.u(u(u(v)))]}_{3} \\
&= (\lambda z.S(S(z)))3 \\
&=S(S(3)) \\ 
&= \underbrace{[\lambda wyx.y(wyx)]}_{S}\underbrace{[\lambda wyx.y(wyx)]}_{S} \underbrace{[\lambda uv.u(u(u(v)))]}_{3} \\
&= [\lambda wyx.y(wyx)][\lambda yx.y( (\lambda uv.u(u(u(v)))) yx)] \\
&= [\lambda wyx.y(wyx)][\lambda yx.y( (\lambda v.y(y(y(v))))x)] \\
&= \underbrace{[\lambda wyx.y(wyx)]}_{S}\underbrace{[\lambda yx.y(y(y(y(x))))]}_{4} \\ \\
&(\implies [y\to a,x\to b][\lambda wyx.y(wyx)] = \lambda wab.a(wab)) \\ \\
&= \lambda ab.a( (\lambda yx.y(y(y(y(x))))) )ab) \\
&= \lambda ab.a((\lambda x.a(a(a(a(x)))))b) \\
&= \lambda ab.a(a(a(a(a(b))))) \equiv 5
\end{align*}
$$
So in more general terms, the addition of two numbers $a$ and $b$ is defined as $aSb$ or $bSa$, which is pretty cool if you remember that numerals are *functions of funtions*.
### Multiplication

$$
M \equiv(\lambda xyz.x(yz))
$$
Where:
- $x$ is the first number
- $y$ is the second
- $z$ is the function to apply
So $x(yz)$ means apply $x$ times the action of applying a function $y$ times.
This is close to intuition, whenever we say something like $3\times 2$ we really mean *Add three 2 times / two 3 times*.
Let's look at an example:

$$
\begin{align*}

M 23 & \equiv \underbrace{[\lambda xyz.x(yz)]}_{M}\underbrace{[\lambda ab.a(a(b))]}_{2}\underbrace{[\lambda cd.c(c(c(d)))]}_{3} \\
&(\implies [x\to 2, y \to 3]  ) \\
&= [\lambda z.\underbrace{[\lambda ab.a(ab)]}_{2}(\underbrace{([\lambda cd.c(c(cd))])}_{3}z) \\
&= [\lambda z.[\lambda ab.a(ab)]([\lambda d.z(z(zd))]) \\
&= [\lambda z.[\lambda b.([\lambda d.z(z(zd))])(([\lambda d.z(z(zd))])b)] \\
&= [\lambda z.[\lambda b.(\lambda d.z(z(zd)))(z(z(zb)))] \\
&= [\lambda z.[\lambda b.(z(z(z(z(z(zb))))))] \\
&= \lambda zb.(z(z(z(z(z(zb)))))) \equiv 6
\end{align*} 
$$
$$
\begin{align*}
(\lambda xyz.x(yz))22 &= \lambda z.2(2z) \\
&= \lambda z.[\lambda ab.a(ab)]([\lambda cd.c(cd)]z) \\
&= \lambda z.[\lambda ab.a(ab)](\lambda d.z(zd)) \\
&= \lambda z.[\lambda b.(\lambda d.z(zd))((\lambda d.z(zd))b)] \\
&= \lambda z. [\lambda b.(\lambda d.z(zd))](z(z(b))) \\
&= \lambda z.\lambda b.z(z(z(zb))) = \lambda zb.z(z(z(zb))) \equiv 4
\end{align*}
$$