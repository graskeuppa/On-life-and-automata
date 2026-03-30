# Numerales
Además, usando [[Cálculo lambda]], podemos pensar en los números, particularmente, *numerales*.

$$
\begin{gathered}
0 \equiv \lambda f.\lambda x.x
\end{gathered}
$$
Donde $f$ es una función, a la que recibo una x. No aplico $x$ a $f$ ninguna vez, así que el 1 sería $1\equiv \lambda f.\lambda x.f.x$ $2\equiv \lambda f.\lambda x.f.(f.x)$, $3\equiv \lambda f.\lambda x.f.(f.(f.x))$.

Todo numeral recibe un par de cosas: Una función que indica cuántas veces se aplica, y la otra un parámetro cualquiera.

# Función sucesor
En base a esto podemos construir la *función sucesor*
Cualquier numeral aplica $n$ veces la función que recibe a su parámetro.
$$
\begin{gathered} 
n\equiv \lambda f.\lambda x.f^{0N}x \\\\
0 \equiv \lambda f.\lambda x.x \\\\
S \equiv \lambda n.\lambda f.\lambda x.(n\ f\ x) \\\\
S \equiv \lambda n.\lambda f.\lambda x.f(f^{0N}x) 
\end{gathered}
$$

Por ejemplo, el sucesor del 3
$$
\begin{gathered}
S_{3} \equiv(\lambda n.\lambda f.\lambda x.f(nfx))3 \\\\

\rightarrow_{\beta} \lambda f.\lambda x.f.(3.f.x) \\\\
\rightarrow_{\beta} \lambda f.\lambda x.f.((\lambda g.\lambda y.g(g.(g.x))).f.x) \\\\
\rightarrow_{\beta} \lambda f.\lambda x.f.(\lambda y.f.(f.(f.x))).x \\\\
\rightarrow_{\beta} \lambda f.\lambda x.f.(f.(f.(f.x)))
\end{gathered}
$$

# Producto
 $$
\begin{gathered}
*\equiv \lambda a.\lambda b.b (+a)0  \\\\
\end{gathered}
$$
Veamos $2*2$
$$
\begin{gathered}
*(2 \ 3) \\\\
(\lambda a.\lambda b.(+a)0)2\ 3 \\\\
(\lambda b.b.(+2)0)3 \\\\
(3(+2)0) \\\\
(\lambda f.\lambda x.\ f(f(f\ x))) (+\ 2)\ 0 \\\\
(\lambda x.(+2)((+2)((+2)x))) \ 0 \\\\
((+2)[(+2)[(+2)0]]) \\\\
\text{La suma parcial se resuelve como: } \\\\

((\lambda a.\lambda b.aSb)2)0 \\\\
(\lambda b.2Sb )0 \\\\
2S 0
(\lambda f.\lambda x.f(f\ x))S\ 0 \\\\
(\lambda x.S(S\ X))0 \\\\
\text{-----------------}
\end{gathered}
$$