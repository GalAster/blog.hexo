---
title: Mathematica 级数高级教程
copyright: true
abbrlink: 5f51bc9f
date: 2018-03-04 15:06:12
tags:
  - Mathematica
categories:

---

## 级数反演

Rest[CoefficientList[
   InverseSeries[Series[2*Log[1 + z] - z, {z, 0, max}], z], z]]*
 Range[max]!
Rest@Block[{n = 18}, 
  CoefficientList[InverseSeries[Series[1 + 2 r - E^r, {r, 0, n}], z], 
    z]*Range[0, n]!]
Block[{n = 18}, 
 n! SeriesCoefficient[InverseSeries[Series[1 + 2 f - E^f, {f, 0, n}]],
    n]]


## 双重复合

n = 10; a[x_] = Sum[c[k] k! x^k, {k, 1, n, 2}];

sa = Series[a[x], {x, 0, n}];

coes = CoefficientList[
    ComposeSeries[sa, sa] - Series[ArcTan[x], {x, 0, n}], x] // Rest;

eq = Reduce[((# == 0) & /@ coes)]; 
Table[c[k] k!, {k, 1, n, 2}] /. First[Solve[eq]]