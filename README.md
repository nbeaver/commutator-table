What is this project about?
===========================

This is a table of commutation relations for quantum mechanical operators. They are useful for deriving relationships between physical quantities in quantum mechanics.

The commutator is a binary operation of two operators. If the operators are `A` and `B`, their commutator is:

    [A, B] = AB - BA

https://en.wikipedia.org/wiki/Commutator#Ring_theory

Why are commutators important?
==============================

Commutation relations have deep physical significance in quantum physics.

Operators which commute have simultaneous eigenstates in common. Many derivations rely on this fact.

Hermitian operators which commute are known as compatible observables, and can be measured simultaneously in the same physical system.

Hermitian operators which do not commute are known as incompatible observables. The most famous of these is the canonical commutation relation:

https://en.wikipedia.org/wiki/Canonical_commutation_relation

An operator which commutes with the Hamiltonian is a conserved quantity over time, like angular momentum or spin.

Finally, commutation relations have freedom of representation, i.e. they do not depend on choice of basis. The relations work just as well in position space as they do in momentum space.

https://en.wikipedia.org/wiki/Position_and_momentum_space

Why is this compilation of commutation relations useful?
========================================================

No textbooks compile an exhaustive list of commutation relations, they just use the ones necessary for relevant derivations. This is fine, as long as you can find the ones you need.

The trouble is that the square bracket notation make finding a particular commutation relation very difficult. This keeps the relations compact, but since the same notation is used for grouping expressions (among other things) it can be difficult to scan through the pages quickly. Moreover, some textbooks contain misprints or are ambiguous about which operators commute and under what circumstances.

A complete set of commutation relations is both useful for quick reference and aesthetically pleasing.

Since this table uses `LaTeX`, all of the mathematical notation is available and links to references are straightforward to implement.

To make it manageable to use the tabular data, the `LaTeX` package `datatool` transforms a CSV file into a LaTeX table automatically during compilation. 

Datatool is already included in standard `LaTeX` installations, but you can see the CTAN package here:

http://www.ctan.org/tex-archive/macros/latex/contrib/datatool

If you want to get learn how to get started, look in `how-to.markdown` for more information.
