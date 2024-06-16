---
layout: default
---

# Settings

```css
% Settings -> Apparence -> CSS Snippets
/* Change the LaTeX font and increase the font size */
.math-block, .math-inline {
    font-family: "Hack Nerd Font Mono", sans-serif;
    font-size: 1.5em; /* Adjust the font size as needed */
}

.MathJax { font-size: 1.5em; }
```

---
# Styling

In line `$\pi$` = $\pi$

Centered `$$\frac{\pi}{\Sigma}$$` $$\frac{\pi}{\Sigma}$$

## Spaces

| Syntax         | Result       |
| -------------- | ------------ |
| `$x\!y$`       | $x\!y$       |
| `$xy$`         | $xy$         |
| `$x\space y$`  | $x\space y$  |
| `$x\:y$`       | $x\:y$       |
| `$x\;y$`       | $x\;y$       |
| `$x \quad y$`  | $x \quad y$  |
| `$x \qquad y$` | $x \qquad y$ |
| `$x \space y$` | $x \space y$ |

## Colors

| Syntax                                       | Result                                     |
| -------------------------------------------- | ------------------------------------------ |
| `$${\color{red}Red}$$`                       | $${\color{red}Red}$$                       |
| `$${\color{green}Green}$$`                   | $${\color{green}Green}$$                   |
| `$${\color{lightgreen}Light \space Green}$$` | $${\color{lightgreen}Light \space Green}$$ |
| `$${\color{blue}Blue}$$`                     | $${\color{blue}Blue}$$                     |
| `$${\color{lightblue}Light \space Blue}$$`   | $${\color{lightblue}Light \space Blue}$$   |
| `$${\color{black}Black}$$`                   | $${\color{black}Black}$$                   |
| `$${\color{white}White}$$`                   | $${\color{white}White}$$                   |

`$\textbf{input}$`

$\textbf{input}$

`$\mathcal{Hello}$`

$\mathcal{Hello}$

`$\sigma\space \Sigma$`

$\sigma\space \Sigma$

`$\ldots\space \vdots$`

$\ldots\space \vdots$

`$\{2,\space 3,\space \ldots\}$`

$\{2,\space 3,\space \ldots\}$

`$(a)[b]\{c\}\langle d \rangle|e|\|f\|$`

$(a) \space [b] \space \{c\} \space \langle d \rangle \space |e| \space \|f\|$

`$\lbrace \space \rbrace \space \underbrace{x-y}_z \space \overbrace{x+y}^z$`

$\lbrace \space \rbrace \space \underbrace{x-y}_z \space \overbrace{x+y}^z$


---
# Functions

## Fraction
 `$\frac{x}{\pi}$`
 
$\frac{x}{\pi}$

## Power
`$X^{yz}$`

$X^{yz}$ 

## Index
`$X_{ij}$`

$X_{ij}$

## Logarithm
`$\log_b a$`

$\log_b a$

`$\ln{x}$`

$\ln{x}$

## Sum
`$f(x) = \sum\limits_{i=0}^{n} a_i x^i$`

$f(x) = \sum\limits_{i=0}^{n} a_i x^i$
## Product
`$g(x) = \prod\limits_{i=0}^{n} a_i x^i$`

$g(x) = \prod\limits_{i=0}^{n} a_i x^i$

## Square
`$\sqrt[n]{x}$`

$\sqrt[n]{x}$

## Limits
`\lim_{x \to +\infty}`, `\inf_{x > s}` and `\sup_K`

$\lim_{x \to +\infty}, \inf_{x > s} and \sup_K$

## Integral
`$\int\limits_a^b f(x)\,dx.$`

$\int\limits_a^b f(x)\,dx.$
`\int\limits_0^1 \! \int\limits_0^1 x^2 y^2\,dx\,dy.`

$\int\limits_0^1 \! \int\limits_0^1 x^2 y^2\,dx\,dy.$

## Derivative
`\frac{du}{dt}` and `\frac{d^2 u}{dx^2}`

$\frac{du}{dt} \space \mathcal{and} \space \frac{d^2 u}{dx^2}$

## Matrix

```text
$$
\Bigg\\{\space \begin{array}{r(ight alligned)c(enter alligned)l(eft aligned)}
	0&6&7 \\
	9&7&3 \\
	6&4&1 \\
\end{array}\space \Bigg\\}
$$
```

$$
\Bigg\\{\space \begin{array}{rcl}
	0&6&7 \\
	9&7&3 \\
	6&4&1 \\
\end{array}\space \Bigg\\}
$$


# Trigonometric functions

| Syntax     | Result    |
| ---------- | --------- |
| `$sin$`    | $\sin$    |
| `$cos$`    | $\cos$    |
| `$tan$`    | $\tan$    |
| `$csc$`    | $\csc$    |
| `$sec$`    | $\sec$    |
| `$cot$`    | $\cot$    |
| `$arcsin$` | $\arcsin$ |
| `$arccos$` | $\arccos$ |
| `$arctan$` | $\arctan$ |
