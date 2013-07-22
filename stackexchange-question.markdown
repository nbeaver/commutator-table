I am making a LaTeX table using a CSV file and the `datatools` package.

Here is a minimal working example:

    \documentclass{minimal}
    \usepackage{datatool}
    \usepackage{filecontents}
    
    \begin{filecontents*}{data.csv}
    ,$x$,$p_x$,
    $x$,$0$,$i \hbar$
    \end{filecontents*}
    
    \begin{document}
    
    \DTLloaddb{mytable}{data.csv}
    \DTLdisplaydb{mytable}
    
    \end{document}

This will compile cleanly. However, if I change the first row (which will become the header) to include a macro (e.g. `,$x$,$\hbar$,`) I get a whole bunch of errors on the `\DTLloaddb{mytable}{data.csv}` line.

    ! Missing \endcsname inserted.
    <to be read again>
    \mathchar
    l.12 \DTLloaddb{mytable}{data.csv}
    The control sequence marked <to be read again> should
    not appear between \csname and \endcsname.
    ....(and so forth)...

Things I have tried that did not work:

0. Quoting ("\hbar")
0. Ensuremath (\ensuremath{\hbar})
0. Using tabs as delimiters instead of commas.
0. Unrolling the csv file into equivalent `datatool` commands.

These are the equivalent commands:

    \DTLnewdb{mydata}
    \DTLnewrow{mydata}%
    \DTLnewdbentry{mydata}{}{$x$}%
    \DTLnewdbentry{mydata}{$x$}{$0$}%
    \DTLnewdbentry{mydata}{$p_x$}{$i \hbar$}%
    \DTLdisplaydb{mydata}

They give the same errors as the csv file.

Manually specifying the headers, however, works fine:

    \documentclass{minimal}
    \usepackage{datatool}
    \usepackage{filecontents}
    
    \begin{filecontents*}{data.csv}
    $x$,$0$,$i \hbar$
    \end{filecontents*}
    
    \begin{document}
    
    \DTLloaddb[noheader,headers={,$x$,$\hbar$}]{mytable}{data.csv}
    
    \DTLdisplaydb{mytable}
    
    \end{document}

I would like to avoid manually specifying the headers, however, if possible.
