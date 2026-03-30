[[Lambda Calculus]] can also be used for *logic applications*; let's dive into conditionals!

---

*True* and *false* are, respectively:
$$
\begin{align*}
T \equiv \lambda xy.x \\
F \equiv \lambda xy.y
\end{align*}
$$
Notice how the $0$ from [[Lambda Arithmetic]] is the same as $F$!
# Logical operations

The **AND** function of two arguments is defined as:
$$
\land \equiv \lambda xy.xy(\lambda uv.v) \equiv \lambda xy.xyF
$$
Where $x$ and $y$ are boolean values.

- If $x$ is true, it returns the first argument given to it, and if that argument happens to be true too, then the whole function is true; if that other argument is false, the function returns the $F$ in its definition and $\beta-$reduces to false.
- If $y$ is false, it returns the second argument, which is the $F$ on the definition of the function.
$$
\begin{align*}
\land TT\equiv (\lambda xy.xyF)TT &= TTF \\&= (\lambda xy.x)(\lambda ab.a)(\lambda cd.d) \\
&=\lambda ab.a \equiv T
\end{align*}
$$
$$
\begin{align*}
\land TF = (\lambda xy.xyF)TF&=TFF \\
&= (\lambda xy.x)(\lambda ab.b)(\lambda cd.d) \\
&=\lambda ab.b \equiv F
\end{align*}
$$
$$
\begin{align*}
\land FT = (\lambda xy.xyF)FT &= FTF \\
&=(\lambda xy.y)(\lambda ab.a)(\lambda cd.d) \\
&=\lambda cd.d \equiv F
\end{align*}
$$
$$
\begin{align*}
\land FF = (\lambda xy.xyF)FF &= FFF \\
&=(\lambda xy.y)(\lambda ab.b)(\lambda cd.d) \\
&=\lambda cd.d \equiv F
\end{align*}
$$
**OR** is defined as:
$$
\lor \equiv \lambda xy.x(\lambda uv.u)y\equiv \lambda xy.xTy
$$
- If $x$ is true, then the whole function is true and we can *shortcircuit* to true
- If $y$ is false, then we jump to the second argument and check that argument to be true or false

The most interesting case is
$$
\begin{align*}
\lor FT = (\lambda xy.xTy)FT &= FTT \\
&= (\lambda xy.y)(\lambda ab.a)(\lambda cd.c) \\
&=\lambda cd.c  \equiv T
\end{align*}
$$
All the others play out exactly as stated in the analysis.

The **negation** is defined as:
$$
\neg \equiv \lambda x.x(\lambda uv.v)(\lambda ab.a) \equiv \lambda x.xFT
$$
- If $x$ is true, then it jumps to $F$
- And if $y$ is false, then it jumps to $T$

$$
\begin{align*}
\neg T = (\lambda x.xFT)T &=TFT \\
&=(\lambda xy.x)(\lambda ab.b)(\lambda cd.c) \\
&=\lambda ab.b\equiv F
\end{align*}
$$
# Conditional test
A function that is true whenever a number is 0 and false in any other case can be defined as:
$$
Z \equiv \lambda x.xFT
$$
Remember $0 \equiv F$, so 
$$
\begin{align*}
Z 0 = (\lambda x.xFT)0 &= 0FT \\
&= (\lambda xy.y)(\lambda ab.b)(\lambda cd.c) \\
&=\lambda cd.c \equiv T
\end{align*}
$$
$$
\begin{align*}
Z 1 = (\lambda x.xFT)1 &=1FT \\
&= (\lambda xy.x(y))(\lambda ab.b)(\lambda cd.c) \\
&= (\lambda y.(\lambda ab.b)(y))(\lambda cd.c) \\
&= (\lambda ab.b)(\lambda cd.c) \\
&= \lambda b.b \equiv_{?} F
\end{align*}
$$

# Predecessor function $(n-1)$
The strat for finding the predecessor of $n$ will be to create a pair $(n,n-1)$ and pick the second element.

We can represent a pair as 
$$
\lambda z.zab
$$
And we can extract the first and second elements by applying $T$ and $F$ respectively.
$$
\begin{align*}
(\lambda z.zab)T = Tab = a \\
(\lambda z.zab)F = Fab = b \\
\end{align*}
$$
The following functions takes the pair $(n,n-1)$ and generates $(n+1,n)$:
$$
\begin{align*}
\Phi \equiv \lambda pz.z(S(pT))(pT)
\end{align*}
$$
Let's run $\Phi(0,0)$:
$$
\begin{align*}
\Phi(0,0) &=\Phi(\lambda a.a 0 0) \\
&= [\lambda pz.z(S(pT))(pT)](\lambda a.a 0 0) \\
&= \lambda z.z(S(\lambda a.a 0 0)T)((\lambda a.a 0 0)T) \\
&= \lambda z.z(S(0))(0) = \lambda z.z 10 \equiv(1,0)
\end{align*}
$$
$$
\begin{align*}
\Phi(1,0) &= \Phi(\lambda a.a 10) \\
&=[\lambda pz.z(S(pT))(pT)](\lambda a.a 10) \\
&=\lambda z.z(S(\lambda a.a 1 0)T)((\lambda a.a 1 0)T) \\
&=\lambda z.z(S(1))(1) = \lambda z.z 2 1 \equiv(2,1)
\end{align*}
$$
Now, the **predecessor** function is defined as:
$$
P \equiv (\lambda n.n\Phi(\lambda z.z 0 0))F
$$
Let's look at $P 3$:
$$
\begin{align*}
P 3 &= ((\lambda n.n\Phi(\lambda z.z 0 0))F)3 \\
&= (3\Phi(\lambda z.z 0 0))F = ( (\lambda ab.a(a(ab)))  \Phi(\lambda z.z 0 0))F \\
&= [(\lambda b.\Phi(\Phi(\Phi b)))  (\lambda z.z 0 0)]F \\
&= [\Phi(\Phi(\Phi(\lambda z.z 0 0)))] F \\
&= [\Phi(\Phi(\lambda z.z 1 0))] F \\
&= [\Phi(\lambda z.z 2 1)] F \\ 
&= [\lambda z.z 3 2]F = 2
\end{align*}
$$
