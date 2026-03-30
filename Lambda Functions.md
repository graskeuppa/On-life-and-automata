# Functions
Lambda functions are a form of Lambda Expressions as seen in [[Lambda Calculus]].
$\lambda x.x$ is the identity function, the variable that comes after the $\lambda$ is the *id of the argument of the function*, the expression that comes after the point is the *body* of the definition.

Functions are applied to expressions,
$$
(\lambda x.x)y
$$
(This follows the $<\text{application}>$ signature).
This is the identity function applied to y. What does that mean?
This is a *function application*, and we evaluate it by substituting the *value of the argument* ($y$) in the expression to the right of the $.$
$$
(\lambda x.x)y =[x\to y]x=y
$$
$$
(\lambda x.x)(\lambda y.yx)= [x\to \lambda y.yx]x=\lambda y.yx
$$
With $[x\to y]$ meaning that all $x$s are substituted with $y$ on the expression to the right.

---
## Variables
A variable $x$ is *bound* in the function $\lambda x.x$ if it coincides with the id of the argument of the function, it's a *free* variable otherwise.

So, in $\lambda x.xy$, $x$ and $y$ are bound and free variables respectively.
In $(\lambda x.x)(\lambda y.yx)$, the first $x$ that appears is bound to the first $\lambda$ and the $y$ on the second expression is bound to that second $\lambda$, do note that the second $x$ is completely independent from the one in the first $\lambda$.

However, a variable can be both bound and free in the same expression:
$$
(\lambda x.xy)(\lambda y.y)
$$
Here, $y$ is free on the first one and bound on the second, so it is both on the whole expression.

## Substitutions
Functions in $\lambda c$ are anonymous, making it confusing to work with them at first, formally, you're supposed to write a whole function whenever you want to evaluate it using another, but that sucks ass, so I will use a variety of symbols to reduce cognitive load.

For instance, $I=\lambda x.x$, so $II$ would look like
$$
II=(\lambda x.x)(\lambda y.y)=[x\to \lambda y.y]=\lambda y.y=I
$$
As seen, some substitution result in basically nothing.
This is also called **$\beta-$reduction**.

Another thing to look out for is accidentaly mixing up free and bound occurrences of an id.
$$
(\lambda x.(\lambda y.xy))y
$$
The $y$ to the right is free while the $y$ inside the expression is bound; when something like this happens we *rename* the variables to make our life a tad easier. This is also called **$\alpha-$conversion/substitution**.
$$
(\lambda x.(\lambda t.xt))y=[x\to y](\lambda t.xt)=\lambda t.yt
$$
More generally, if the function $\lambda x.<\text{expression}>$ is applied to $E$, all free occurrences of $x$ in $<\text{expression}>$ are replaced with $E$. However, when the substitiom brings in a free variable from $E$ into an expression in which the same variable is bound, rename the bound variable before doing the $\alpha-$substitution.

Let's look at a more complex example:
$$
\begin{gathered}
&(\lambda x.(\lambda y.(x(\lambda x.xy))))y \\
&\text{The x inside the body is the only that is free and can be substituted} \\
& \implies [y\to t](\lambda y.(x(\lambda x.xy))) \\
&\implies (\lambda x.(\lambda t.(x(\lambda x.xt))))y \\
&= [x\to y](\lambda t.(x(\lambda x.xt))) \\
&= (\lambda t.(y(\lambda x.xt)))
\end{gathered}
$$


