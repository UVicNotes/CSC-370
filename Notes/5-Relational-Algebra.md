# Relational Algebra

_defintion_: In the relational model, operations can be expressed in algebra called **relational algebra**. In relational algebra, *relations* are the *operands* and we apply *operators* to them.

## Basic Operations

* Union, $\cup$
* Intersection, $\cap$
* Difference, $-$

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

