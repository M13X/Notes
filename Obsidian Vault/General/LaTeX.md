

```css
% Settings -> Apparence -> CSS Snippets
/* Change the LaTeX font and increase the font size */
.math-block, .math-inline {
    font-family: "Hack Nerd Font Mono", sans-serif;
    font-size: 1.5em; /* Adjust the font size as needed */
}

.MathJax { font-size: 1.5em; }
```

In line `$\pi$` = $\pi$
Centered `$$\frac{\pi}{\Sigma}$$` $$\frac{\pi}{\Sigma}$$
$\textbf{input}$ `$\textbf{input}$`

$\sqrt[n]{x}$  `$\sqrt[n]{x}$`

$X^{yz}$  `$X^{yz}$`

$X_{ij}$  `$X_{ij}$`

$frac{\frac{x}{\pi}}{\sum{n}}$  `$frac{\frac{x}{\pi}}{\sum{n}}$`

$\sum_{j=0}^7j^2\pi$  `$\sum_{j=0}^7j^2\pi$`

$\mathcal{Hello}$  `$\mathcal{Hello}$`

$\sigma\,\Sigma$  `$\sigma\,\Sigma$`

$\ldots\,\vdots$  `$\ldots\,\vdots$`

$\{2,\,3,\,\ldots\}$  `$\{2,\,3,\,\ldots\}$`

$(a)[b]\{c\}\langle d \rangle|e|\|f\|$  `$(a)[b]\{c\}\langle d \rangle|e|\|f\|$`
```text
$$
\Bigg\{\,\begin{array}{r(ight alligned)c(enter alligned)l(eft aligned)}
	0&6&7 \\
	9&7&3 \\
	6&4&1 \\
\end{array}\,\Bigg\}
$$
```

$$
\Bigg\{\,\begin{array}{rcl}
	0&6&7 \\
	9&7&3 \\
	6&4&1 \\
\end{array}\,\Bigg\}
$$
## Spaces

| Syntax         | Result       |
| -------------- | ------------ |
| `$x\!y$`       | $x\!y$       |
| `$xy$`         | $xy$         |
| `$x\,y$`       | $x\,y$       |
| `$x\:y$`       | $x\:y$       |
| `$x\;y$`       | $x\;y$       |
| `$x \quad y$`  | $x \quad y$  |
| `$x \qquad y$` | $x \qquad y$ |
| `$x \space y$` | $x \space y$ |

## Colors

| Code                                         | Appearing                                  |
| -------------------------------------------- | ------------------------------------------ |
| `$${\color{red}Red}$$`                       | $${\color{red}Red}$$                       |
| `$${\color{green}Green}$$`                   | $${\color{green}Green}$$                   |
| `$${\color{lightgreen}Light \space Green}$$` | $${\color{lightgreen}Light \space Green}$$ |
| `$${\color{blue}Blue}$$`                     | $${\color{blue}Blue}$$                     |
| `$${\color{lightblue}Light \space Blue}$$`   | $${\color{lightblue}Light \space Blue}$$   |
| `$${\color{black}Black}$$`                   | $${\color{black}Black}$$                   |
| `$${\color{white}White}$$`                   | $${\color{white}White}$$                   |