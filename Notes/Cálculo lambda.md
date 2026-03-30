El formalismo de Church, equivalente a las [[máquina de Turing]].
Se encuentra definido sobre variables.
Es el lenguaje de programación más pequeño que es [[Turing completo]].




$$
M::=Var |\lambda Var.M|MM
$$
$$
Var::= x| y |z
$$
Puedes incluso hacer lógica haciendo algo como:
$$
T=_{\&\&}\lambda x.\lambda y.x 
$$
$$
F=_{\&\&} \lambda x.\lambda y.y
$$

Not como
$$
\lnot= \lambda b.bFT
$$
$$
(\lambda b.bFT)(\lambda x.\lambda y.x)
$$
$$
(bFT)[b:=\lambda x.\lambda y.x]
$$
$$
(\lambda y.\lambda x.X)FT \implies_{\beta} \ (\lambda y.x)[x:=F]T 
$$
$$
(\lambda y.F)T \implies_{B} \ (F)[y:=T]
$$
$$
\implies_{\beta} \ F
$$
Se usó [[Beta reducción]] para reducir esto a $F$, que está en línea con lo que se esperaba.

Para $\land$
$$
\begin{gathered}
\lambda x.\lambda y.xyFV \\\\
(\lambda x.\lambda y.xyF)TF \\\\
(\lambda x.\lambda y.xyF)[x:=T] \\\\
(\lambda y.TyF)F \\\\
(TyF)[y:=F] \\\\
TFF \\\\
(\lambda x.\lambda y.x)FF \implies_{\beta} \ (\lambda y.F)F \implies_{B} \ F
\end{gathered}
$$
