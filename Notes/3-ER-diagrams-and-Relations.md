# E/R Diagrams to Relations 

## Table Terminology

In a table

* *Headings* are **attribute names**.
* *Rows* are **tuples**.
* *Elements* in rows are tuple components

## Entity Sets to Relations

#### Example

![Diagram](img/Relational-Diagram.svg)

The tables are,

* `Movies`: (_`title`_, `year`, `length`, `filmType`, `studioName`) 
* `Studios`: (_`name`_, `address`)
* `Stars`: (_`name`_, `address`)
* `StarsIn`: (_`title`_, `year`, `starName`)

The `movies` table would look like,

`title` | `year` | `length` | `filmType` | `studioName`
:-:|:-:|:-:|:-:|:-:
`Godzilla` | `2014` | `200` | `feature` | `Fox`
... | ... | ... | ... | ...
