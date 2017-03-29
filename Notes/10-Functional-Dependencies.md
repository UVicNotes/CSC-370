# Functional Dependencies and Database Normalization

## Boyce-Codd Normal Form

A relational schema R is in Boyce-Codd normal form if and only if for every one of its dependencies $X \to Y$, at least one of the following conditions hold:

* $X \to Y$ is a trivial functional dependency ($Y \subseteq X$)
* $X$ is a super key for schema $R$.

**Example**

Consider a table $R(A,B,C,D,E,F)$, with the following *functional dependencies*,

$$\begin{aligned}
    AB &\to C \newline
    BC &\to AD \newline
    D &\to E \newline
    CF &\to B.
\end{aligned}$$

If we calculate the closure of $AB$,

$$\begin{aligned}
    X &= \{ A, B \} \newline
    X &= \{ A, B, C \} \newline
    X &= \{ A, B, C, D \} \newline
    X &= \{ A, B, C, D, E \} \newline
\end{aligned}$$

So $\{ A,B \}^+ = AB^+ = ABCDE$. Then is $AB$ a *superkey*? No, because it didn't include $F$, therefore it is a violation.

We can create the tables then,

$$\begin{aligned}
    &R_1 (A, B, C, D, E) \newline
    &R_2 (A, B, F) \newline
\end{aligned}$$

and infer the functional dependencies,

$$\begin{aligned}
    AB &\to E \newline
    AB &\to D.
\end{aligned}$$

We can then compute the closure on each subset of $X$ (but not $X = \varnothing$). If $X^+$ is all attributes the no need to do closure on a subset of $X$.

If we find $X$ such that $X^+$ is **not** all the attrib then we get a violating functional dependency.

**Example**

Consider the table $\text{Movies} ( \text{title}, \text{year}, \text{studioname}, \text{president}, \text{presAddr} )$ with the following functional dependencies,

$$\begin{aligned}
    \text{title}, \text{year} &\to \text{studioname} \newline
    \text{studioname} &\to \text{president} \newline
    \text{president} &\to \text{presAddr}
\end{aligned}$$

where each movie is only produced by one studio. This gives us the closures,

$$\begin{aligned}
    \text{title}^+ &= \text{title} \newline
    \text{year}^+ &= \text{year} \newline
    \text{title, year}^+ &= \text{title}, \text{year}, \text{studioname}, \text{president}, \text{presAddr} \newline
\end{aligned}$$

So $\text{title}, \text{year}$ **is** a superkey. For $\text{studioname}$,

$$\begin{aligned}
    \text{studioname}^+ &= \text{studioname}, \text{president}, \text{presAddr}
\end{aligned}$$

so $\text{studioname}$ is **not** a superkey and is therefore violates Boyce-Codd Normal Form (BCNF). The gives us the dependency,

$$\begin{aligned}
    \text{studioname} \to \text{president}, \text{presAddr}.
\end{aligned}$$

To resolve the violation we can decompose movies into,


$$\begin{aligned}
    &\text{Movies}_1 ( \text{studioname}, \text{president}, \text{presAddr} ) \newline
    &\text{Movies}_2 ( \text{title}, \text{year}, \text{studioname} ) 
\end{aligned}$$

We can verify, $\text{Movies}_2$ is in BCNF however $\text{Movies}_1$ is not since $\text{president} \to \text{presAddr}$. So the closure is,

$$\begin{aligned}
    \text{president}^+ &= \text{president}, \text{presAddr}
\end{aligned}$$

and $\text{president} \to \text{presAddr}$ violates $BCNF$. We can decompose the tables further,

$$\begin{aligned}
    \text{Movies}_{1,1} ~&( \text{president}, \text{presAddr} ) \newline
    \text{Movies}_{1,2} ~&( \text{studioname}, \text{president} ) \newline
    \text{Movies}_2 ~&( \text{title}, \text{year}, \text{studioname} ) 
\end{aligned}$$

## Third-normal Form

An attribute is considered **prime** if it is a member of the same key. The functional dependency

$$
    X \to A
$$

is a violating functional dependency if and only if,

1. $X$ is not a superkey
1. $A$ is not *prime*

**Example**

Consider the relation $R(A,B,C)$ with the following functional dependencies

$$\begin{aligned}
    AB &\to C \newline
    C &\to B
\end{aligned}$$

the only violating functional dependency is $C \to B$. We can decompose into the relations,

$$\begin{aligned}
    &R_1 (C,B) \newline
    &R_2 (C,A).
\end{aligned}$$ 

In this case we could have insertion issues inserting into both relations.
