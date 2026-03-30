This is a deep dive and more complete version of the notes on the [[Cálculo lambda]] noteset.
*$\lambda$ calculus* is the **smallest universal programming language in existence**.
It's really quite simple, it consists of:
- One transformation rule -> variable substitution
- And just one function definition scheme (the $\lambda.x$ thingy)

> It is equivalent to Turing Machines and can express any computable function.

---
# Expressions
Expressions are the crux of $\lambda$c, it is defined recursively as follows:
$$
\begin{align*}
<\text{expression}> &:= &<\text{variable}>|<\text{function}>|<\text{application}> \\
<\text{function}> &:= &\lambda<\text{variable}>.<\text{expression}> \\
<\text{application}> &:= &<\text{expression}><\text{expression}>
\end{align*}
$$
The only reserved keywords are $\lambda$ and $.$ .
Variables do not have a meaning per se, they simply act as placeholders to indicate how to rearragange arguments in a function.

Expressions can be surrounded by parenthesis to avoid any confusion, but since that can make the expression look cluttered, by convention, function application goes from left to right 
$$
E_{1}E_{2}E_{3}\dots E_{n}=(\dots((E_{1}E_{2})E_{3})\dots E_{n})
$$
