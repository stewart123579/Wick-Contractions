# LaTeX document style for generating Wick contractions.

    If you don't know what Wick contactions are then you need to do more Physics!

    Stewart V. Wright,  May 2001.

(Thanks to [resuscv](http://github.com/resuscv) for maintaining these for the
last decade and then transferring them back to me.)

As these macros are TeX, they will work with LaTeX too.

These macros were written by Dan Schroeder (of Peskin and Schroeder
fame) and emailed to me.  I've put all this crap at the start,
called it a .sty file and modified it so it will do 4 contractions
rather than just three.

To use, you need to put `\usepackage{contractions}` in your LaTeX
file.

Some examples of use are shown at the bottom of this file.


## COMMANDS

### `\begC`

begins a new contraction; its first argument is a number from 1 to 3, indicating
      the vertical level; its second argument is the character or group of
      characters over which the vertical line is to be centered.

### `\conC`

continues any ongoing contractions, putting the necessary horizontal lines over
the text of its argument.

### `\endC`
ends a contraction, taking a number from 1 to 3 as its first argument and the
symbol(s) as its second argument, just like `\begC`.

These macros have the side effect of leaving enough vertical space for all three
levels, even if you use only one level.  Use `\smash` and `\vphantom` if
necessary to take up the extra vertical white space.

The contraction macros are set up for 10pt Computer Modern type. for other fonts
or sizes the numerical parameters should be tweaked by trial and error.


EXAMPLES
--------

Some examples of using the contraction macros:

```latex
$$
  \begC1\phi\conC{(x)}\endC1\phi(y)
$$
```

```latex
$$
  \begC1{\phi_1}\endC1{\phi_2}\begC1{\phi_3}\endC1{\phi_4}
  +\begC1{\phi_1}\begC2{\phi_2}\endC1{\phi_3}\endC2{\phi_4}
  +\begC2{\phi_1}\begC1{\phi_2}\endC1{\phi_3}\endC2{\phi_4}
$$
```

```latex
$$
  \begC2{\phi(x)}\begC3{\phi(y)}\conC{\,{1\over3!}
  \bigl({-i\lambda\over4!}\bigr)^3\int\!d^4z\,}\endC2{\phi}\begC1{\phi}
  \endC1\phi\begC1\phi\conC{\,\int\!d^4w\,}\endC1\phi\begC2\phi
  \begC1\phi\endC3\phi\conC{\,\int\!d^4u\,}\endC1\phi\endC2\phi
  \begC1\phi\endC1\phi
$$
```

```latex
$$
  \begC4\phi\begC3\phi\begC2\phi\begC1\phi
  \endC4\phi\endC1\phi\endC2\phi\endC3\phi
$$
```

```latex
\begin{eqnarray}
  a & = & b \\
  & = & \begC2{\phi_1}\begC1{\phi_2}\endC1{\phi_3}\endC2{\phi_4} \\
  & = & \begC4\phi\begC3\phi\begC2\phi\begC1\phi
  \endC4\phi\endC1\phi\endC2\phi\endC3\phi \\
  & = & d
\end{eqnarray}
```
