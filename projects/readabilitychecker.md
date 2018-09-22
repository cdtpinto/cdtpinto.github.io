# Readability Checker

Readability Checker is a plugin for the NetBbeans IDE that estimates Java code readability using three different software readability formulas.

## Implemented Formulas

Currently, Readability Checker implements three software readability formulas:

* Comments Ratio
* Software Readability Ease Score (SRES)
* Posnett Hindle Devanbu (PHD)

### Comments Ratio

Proposed, in 2002, by the researchers Krishan K. Aggarwal, Yogesh Singh and Jitender Kumar Chhabra in the article [An Integrated Measure of Software Maintainability](https://ieeexplore.ieee.org/document/981648/).

The proposed formula is:

![equation](http://www.sciweavers.org/tex2img.php?eq=CR%20%3D%20LOC%20%20%2F%20%20LOM&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

where:

LOC is the number of lines of code.
LOM is the number of lines with comments.

##### Implementation notes

#  

This formula analyzes the readability of the project, the class and each of the class methods.

**The implementation of this formula supports Java SE 10.**

### SRES

Theorized by Jürgen Börstler, Michael E. Caspersen e Marie Nordström, the general principles of this readability formula was first introduced in 2007 in the article [Beauty and the Beast Toward a Measurement Framework for Example Program Quality](https://pdfs.semanticscholar.org/8c41/1a1fb987966f2020765069dc21881826e635.pdf), then it's logic was implemented in a readability tool titled [Properties of "Good" Java Examples](http://www8.cs.umu.se/education/examina/Rapporter/NadeemAbbas_v2.pdf) by Nadeem Abbas, and later on, in 2015, the SRES readability formula was actually proposed in the article [Beauty and the Beast: on the readability of object-oriented example programs](https://link.springer.com/article/10.1007/s11219-015-9267-5).

The proposed formula is:

![equation](http://www.sciweavers.org/tex2img.php?eq=SRES%20%3D%20ASL%20-%200.1%20%20%5Ctimes%20%20AWL&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

where:

ASL is the average sentence length.
AWL is the average word length.

##### Implementation notes

# 

**The implementation of this formula supports Java SE 5.**

### PHD

This readability formula was proposed by Daryl Posnett, Abram Hindle and Prem Devanbu, in 2011, in the article [A Simpler Model of Software Readability](https://dl.acm.org/citation.cfm?id=1985454).

The proposed formula is:

![equation](http://www.sciweavers.org/tex2img.php?eq=%20%5Cfrac%7B1%7D%7B1%2B%20e%5E%7B-z%7D%20%7D%20&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

where:

![equation](http://www.sciweavers.org/tex2img.php?eq=z%20%3D%208.87%20-%200.033%20%20%5Ctimes%20%20Volume%20%2B%200.40%20%20%5Ctimes%20%20Lines%20-%201.5%20%20%5Ctimes%20%20Entropymes%20%20AWLLOM&bc=White&fc=Black&im=jpg&fs=12&ff=arev&edit=0)

##### Implementation notes

# 

**The implementation of this formula supports Java SE 5.**
