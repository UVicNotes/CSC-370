# Relational Algebra

_defintion_: In the relational model, operations can be expressed in algebra called **relational algebra**. In relational algebra, *relations* are the *operands* and we apply *operators* to them.

## Basic Operations

### Union

Union ($\cup$) is all tuples from each operand. For example,

$$
  R \cup S
$$

is all the tuples in $R$ **or** in $S$, or both.

### Intersection

Intersection ($\cap$) is all tuples from both operands. For example,

$$
  R \cap S
$$

is all the tuples in both $R$ **and** in $S$.

### Difference

Difference ($-$) is the difference between the tuples from each operand. For example,

$$
  R - S
$$

is all the tuples in $R$ but **not** in $S$. Note $R - S \neq S - R$.


## Removal Operations

### Selection

Selection ($\sigma$) eliminates some rows, for example

$$
  \sigma_{A < 2}(R)
$$

is a new relation with rows from $R$ where $A$ is less than $2$.

### Projection

Projection ($\pi$) eliminates some columns, for example

$$
  \pi_{A_1,\ldots,A_n}(R)
$$

is a new relation with columns $A_1,\ldots,A_n$ from $R$.

## Combination Operations

### Cartesian Product

The Cartesian Product ($\times$) is all tuples with the first part from the first operand and the second part from the second operand. Common attributes should be prefixed with the relation name. For example, given the relation $R$

 $A$ | $B$
:---:|:---:
$a_1$|$b_1$
$a_2$|$b_2$

and the relation $S$

 $B$ | $C$ | $D$
:---:|:---:|:---:
$b_3$|$c_1$|$d_1$
$b_4$|$c_2$|$d_2$
$b_5$|$c_3$|$d_3$

then the relation $R \times S$ is

 $A$ |$R.B$|$S.B$| $C$ | $D$
:---:|:---:|:---:|:---:|:---:
$a_1$|$b_1$|$b_3$|$c_1$|$d_1$
$a_1$|$b_1$|$b_4$|$c_2$|$d_2$
$a_1$|$b_1$|$b_5$|$c_3$|$d_3$
$a_2$|$b_2$|$b_3$|$c_1$|$d_1$
$a_2$|$b_2$|$b_4$|$c_2$|$d_2$
$a_2$|$b_2$|$b_5$|$c_3$|$d_3$

### Join


