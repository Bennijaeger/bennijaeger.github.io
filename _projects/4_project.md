---
layout: page
title: projects.titles.project4
description: projects.descriptions.project4
importance: 4
related_publications: true
---

*with G. Aarts, F. Attanasio, F. Ziegler and P. de Forcrand, 2014–2022*

At non-zero baryon chemical potential, the fermion determinant is complex, and importance sampling cannot be applied (the sign problem). Complex Langevin simulations avoid this by complexifying the field variables. However, they can converge to incorrect results if the distribution extends too far into the complexified manifold.

We first mapped the phase diagram of QCD in the limit of heavy quarks {% cite Aarts:2016qrv %}. Together with F. Attanasio, I developed dynamical stabilisation, an additional force term which keeps the simulation close to SU(3) and vanishes in the continuum limit {% cite Attanasio:2018rtq %}. This allowed us to simulate QCD with dynamical quarks and to determine the equation of state at non-zero density {% cite Attanasio:2020spv Attanasio:2022mjd %}.

Note that dynamical stabilisation modifies the dynamics at non-zero lattice spacing. Whether the results approach the correct limit therefore has to be checked numerically, for instance by comparison with Taylor expansions at small μ/T. At ETH Zürich, with P. de Forcrand, I worked on alternative approaches to the Taylor expansion in the chemical potential, based on the Cauchy residue theorem {% cite deForcrand:2018zll deForcrand:2017cja %}.

**Contribution.** Development of dynamical stabilisation (two-author paper with F. Attanasio), simulation code and the equation-of-state analysis.
