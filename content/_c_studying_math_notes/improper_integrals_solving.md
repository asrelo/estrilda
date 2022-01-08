---
layout: default
title: Решение несобственных интегралов
tags: integrals improper_integrals math_notes studying
published: false
---

# Несобственные интегралы

## Интегралы с бесконечными пределами

Если функция \\( f\left(x\right) \\) непрерывна при \\( a \leq x < +\infty \\), то по определению

\\[ \label{eq:improper_one_sided_integral_definition} \int\limits_{a}^{+\infty}{f\left(x\right) dx} = \lim\limits_{b \rightarrow +\infty}{\int\limits_{a}^{b}{f\left(x\right) dx}} \tag{1} \\]

Если существует конечный предел в правой части формулы \eqref{eq:improper_one_sided_integral_definition}, то несобственный интеграл называется *сходящимся*, если этот предел не существует, то &mdash; *расходящимся*.

Геометрически несобственный интеграл \eqref{eq:improper_one_sided_integral_definition} в случае \\( f\left(x\right) > 0 \\) есть площадь фигуры, ограниченной графиком функции \\( y = f\left(x\right) \\), прямой \\( x = a \\) и осью \\( O x \\) (асимптотой).

Аналогично определяется интеграл \\( \int\limits_{-\infty}^{b}{f\left(x\right) dx} \\). Далее, по определению

\\[ \label{eq:improper_two_sided_integral_definition} \int\limits_{-\infty}^{+\infty}{f\left(x\right) dx} = \int\limits_{-\infty}^{c}{f\left(x\right) dx} + \int\limits_{c}^{+\infty}{f\left(x\right) dx} \tag{2} \\]

где \\( c \\), \\( -\infty < c < +\infty \\), &mdash; произвольное число, причём интеграл в левой части равенства \eqref{eq:improper_two_sided_integral_definition} считается сходящимся, если сходятся оба интеграла в правой части.

**Признаки сходимости и расходимости** приведём только для интегралов вида \eqref{eq:improper_one_sided_integral_definition}.

1. Пусть \\( F\left(x\right) \\) &mdash; первообразная \\( f\left(x\right) \\). Если \\( \exists \lim\limits_{x \rightarrow +\infty}{F\left(x\right)} = F\left(+\infty\right) \\) &mdash; конечный предел, то интеграл \eqref{eq:improper_one_sided_integral_definition} сходится и равен \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} = F\left(+\infty\right) - F\left(a\right) \\). Если же \\( \nexists \lim\limits_{x \rightarrow +\infty}{F\left(x\right)} \\), то интеграл \eqref{eq:improper_one_sided_integral_definition} расходится.

2. (**признак сравнения**)

   1. Если при \\( a \leq x < +\infty \\) \\( 0 \leq f\left(x\right) \leq g\left(x\right) \\) и \\( \int\limits_{a}^{+\infty}{g\left(x\right) dx} \\) сходится, то сходится и \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} \\). При этом \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} < \int\limits_{a}^{+\infty}{g\left(x\right) dx} \\). 

   2. Если при \\( a \leq x < +\infty \\) \\( 0 \leq f\left(x\right) \leq g\left(x\right) \\) и \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} \\) расходится, то расходится и \\( \int\limits_{a}^{+\infty}{g\left(x\right) dx} \\).

3. (**предельный признак сравнения**) Если при \\( a \leq x < +\infty \\) \\( f\left(x\right) > 0 \wedge g\left(x\right) \\) и \\( \exists \lim\limits_{x \rightarrow +\infty}{\frac{f\left(x\right)}{g\left(x\right)} \neq 0} \\) &mdash; конечный предел, то \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} \\) и \\( \int\limits_{a}^{+\infty}{g\left(x\right) dx} \\) оба вместе либо сходятся, либо расходятся.

4. Если сходится \\( \int\limits_{a}^{+\infty}{\left\|f\left(x\right)\right\| dx} \\), то сходится и \\( \int\limits_{a}^{+\infty}{f\left(x\right) dx} \\) (интеграл без модуля тогда называется *абсолютно сходящимся*).

**Пример 1**. Вычислить \\( \int\limits_{0}^{+\infty}{e^{-3 x} dx} \\).

\\[ \int\limits_{0}^{+\infty}{e^{-3 x} dx} = \lim\limits_{b \rightarrow +\infty}{\int\limits_{0}^{b}{e^{-3 x} dx}} = \lim\limits_{b \rightarrow +\infty}{\left( {\left. -\frac{1}{3} e^{-3 x} \right\|}\_{0}^{b} \right)} = \frac{1}{3} \lim\limits_{b \rightarrow +\infty}{\left( 1 - e^{-3 b} \right)} = \frac{1}{3} \\]

На практике в качестве интеграла, с которым производится сравнение, обычно используются интегралы вида \\( \int\limits_{c}^{+\infty}{\frac{1}{x^a} dx} \\), \\( c > 0 \\), \\( a > 0 \\).

**Пример 2**. Исследовать на сходимость интеграл \\( \int\limits_{1}^{+\infty}{\frac{x + 1}{\sqrt{x^3}} dx} \\).

При \\( x \rightarrow +\infty \\) \\( \frac{x + 1}{\sqrt{x^3}} = \frac{x \left(1 + \frac{1}{x} \right)}{x^{3/2}} \sim \frac{1}{x^{1/2}} \\).

Так как \\( \int\limits_{1}^{+\infty}{\frac{dx}{x^{1/2}}} \\) расходится (\\( a = 1/2 < 1 \\)), то и заданный интеграл тоже расходится.
