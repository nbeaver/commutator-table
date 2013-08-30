# How do I add a commutation relation? #

Open `commutation-relations.csv` with your favorite tabular data editor (e.g. Libreoffice Calc, Gnumeric, Excel) and navigate to the correct row and column.

Add the value.

Next, we need to link to the value. Do this by wrapping the value in a `hyperref` command, like this: `\hyperref[self]{0}`. This will create a link around the value `0` that will jump to the labeled called `self`.

Finally, add a reference in the reference section in `table.tex`. This will give the link a target to jump to. Ideally, this would include a reference to the work cited.

    \item[0] \label{self} Any operator commutes with itself. See book by *AUTHOR* on page *PAGE*.

# How do I add a new operator? #

Open `commutation-relations.csv` with your favorite tabular data editor (e.g. Libreoffice Calc, Gnumeric, Excel) and make a new row and column with the name of your operator.

Now change the line in `table.tex` like this:

     \DTLloaddb[keys={A,B,C,D,E,F,G,H,I,J,K,L,M}]{commutators}{commutation-relations.csv}

so that it has the number of columns that the CSV requires. This is required for math markup to be available for operator definitions. See here for more information:

<http://tex.stackexchange.com/questions/125060/datatool-cannot-use-math-macros-in-tabular-headers-from-csv-file>

Next, you should define the operator in `table.tex` as described above. The definitions are in the subsection `Operator definitions.` For example, the momentum operator is, in position space, defined as `i/hbar * d/dx`, so the relevant definition is:

    \item \label{def_p_x} $p_x = \frac{\hbar}{i}\frac{\partial}{\partial x}$ in the x-basis. Townsend p.158.
