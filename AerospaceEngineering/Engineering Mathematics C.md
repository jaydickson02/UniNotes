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

L: logs (*ln*(*x*), *ln*(*x*2), log10(*x*))

I: inverse trig (*tan* − 1(*x*), *arcsin*(2*x*))

A: Algebraic ($x^2, (x-1), x^6, \sqrt{x}$)

T: Trig Functions (*sin*(*x*), *cos*(*x*3))

E: Exponentials (*ex*, *e* − 3*x*, *ex*2 + 4)

Where u is the first type you come across in the expression, and v is the second.