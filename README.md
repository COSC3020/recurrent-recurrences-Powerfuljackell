[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$
$T(n) = T(\frac{n}{13}) + 5 $

$= T(T(\frac{n}{13 \cdot 13}) + 5) + 5)$

$= T(T(T(\frac{n}{13 \cdot 13 \cdot 13}) + 5) + 5) + 5$

$...$

$= T(\frac{n}{13^i}) + 5i$

for $i = \log n$

$T(\frac{n}{13n}) + 5logn$

$T(\frac{1}{13}) + 5logn$

$T(1) + logn \in \Theta(logn)$

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

$T(n) = 13T(\frac{n}{13}) + 5 $

$= 13T(13T(\frac{n}{13 \cdot 13}) + 5) + 5)$

$= 13T(13T(13T(\frac{n}{13 \cdot 13 \cdot 13}) + 5) + 5) + 5$

$...$

$= 13^i \cdot T(\frac{n}{13^i}) + 5i$

for $i = \log n$

$13n \cdot T(\frac{n}{13n}) + 5logn$

$13n \cdot T(\frac{1}{13}) + 5logn$

$n \cdot T(1) + logn \in \Theta(logn)$

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

$T(n) = 13T(\frac{n}{13}) + 2n $

$= 13T(13T(\frac{n}{13 \cdot 13}) + 2(\frac{n}{13})) + 2n)$

$= 13T(13T(13T(\frac{n}{13 \cdot 13 \cdot 13}) + 2(\frac{n}{13 \cdot 13})) + 2(\frac{n}{13})) + 2n$

$= 13T(13T(13T(\frac{n}{13 \cdot 13 \cdot 13}) + 2n(\frac{1}{13 \cdot 13})) + 2n(\frac{1}{13})) + 2n$

$...$

$= 13^i \cdot T(\frac{n}{13^i}) + 2n(\sum_{k=0}^{i} (\frac{1}{13^k}))$

for $i = \log n$

$13n \cdot T(\frac{n}{13n}) + 2n\frac{1}{13^{logn}}$

$13n \cdot T(\frac{n}{13n}) + \frac{2n}{13n}$

$13n \cdot T(\frac{1}{13}) + \frac{2}{13}$

$n \cdot T(1) \in \Theta(n)$