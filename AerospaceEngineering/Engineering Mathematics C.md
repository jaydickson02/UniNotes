---
layout: post
title:  "Engineering Mathematics C"
---

# Integration by Parts

## Formula

$$
\int u {dv \over{dx}} \: dx  = uv - \int {du \over {dx}}v \: dx
$$

Ex. 

$$
∫xe^xdx
$$

 if u = x and ${dv \over dx} = e^xdx$

Then: $v = ∫e^x$ and ${du\over dx} = u'$

## The trick to Pick u and v

*L.I.A.T.E*

L: logs ($\log{x}$, $\log{2x}$, $\log_{10}{x}$)

I: inverse trig ($\arctan{x}$, $\arcsin{2x}$)

A: Algebraic ($x^2$, $(x-1)$, $x^6$, $\sqrt{x}$)

T: Trig Functions ($\sin{x}$, $\cos{3x}$)

E: Exponentials ($ex$, $e − 3x$, $2ex + 4$)

Where u is the first type you come across in the expression, and v is the second.