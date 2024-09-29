---
title: "A Brief Introduction to DG schemes"
collection: talks-archive
type: "Talk-archive"
permalink: /talks/dgschemes
venue: "Southern Methodist University, Department of Mathematics"
date: 2023-10-10
location: "Dallas, Texas"
output:
    includes:
        in_header: preamble.tex
---

## Advection
$\global\def\qh{\sum_{i=0}^{N_p}\hat{q}(x_i,\;t)\;\ell_i(x)}$
$\global\def\pd#1#2{\frac{\partial#1}{\partial#2}}$

$$q+\nabla q \cdot \vec{v} = 0,\;\; x\in\Omega$$
$$\int_{\Omega_k} \psi_k\pd{q}{t} + \psi_k\nabla q_h \cdot \vec{v}\; dx = 0$$
$$\int_{\Omega_k} \psi_k\pd{q}{t} \;dx - \int_{\Omega_k}q \nabla\cdot(\psi_k \hat{v}) dx=-\int_{\partial\Omega_k}q^* \psi_k\vec{v}\cdot \hat{n}\;ds\tag{Weak form}$$
$$\int_{\Omega_k} \psi_k\pd{q}{t} \;dx + \int_{\Omega_k}\psi_k\nabla q_h \cdot \vec{v}\; dx=\int_{\partial\Omega_k}\psi_k  q\vec{v}\cdot\hat{n}\;ds-\int_{\partial\Omega_k}\psi_k q^* \vec{v}\cdot \hat{n}\;ds$$
$$\int_{\Omega_k} \psi_k\pd{q}{t} \;dx + \int_{\Omega_k}\psi_k\nabla q_h \cdot \vec{v}\; dx=\int_{\partial\Omega_k}\psi_k  (q\vec{v}-q^* \vec{v}) \cdot \hat{n}\;ds\tag{Strong form}$$
$$\int_{\Omega_k}\left(\pd{q}{t} + \nabla q_h \cdot \vec{v}\right)\psi_k\; dx=\int_{\partial\Omega_k}\psi_k  (q\vec{v}-q^* \vec{v}) \cdot \hat{n}\;ds$$
$q_h(x,t) = \qh$ and $\psi_k = \ell_k(x)$

Lets inspect the first integral
$$
\begin{align*}
\int_{\Omega_k} \psi_k\pd{q}{t} \;dx &= \int_{\Omega_k} \ell_k(x)\pd{}{t}\qh dx\\
&=\sum_{i=0}^{N_p}\pd{\hat{p}}{t}(x_i,t)\int_{\Omega_k} \ell_k(x)\ell_i(x) dx\\
&=\sum_{i=0}^{N_p}\pd{\hat{p}}{t}(x_i,t)J^k\int_{I^k}\ell_k(r)\ell_i(r) dr\\
&=J^kM\pd{\hat{p}}{t}\\
\end{align*}
$$

$$
\begin{align*}
\int_{\Omega_k}\psi_k\nabla q_h \cdot \vec{v}\; dx &= \int_{\Omega_k}\psi_k\left(v_x \pd{q_h}{x}+ v_y\pd{q_h}{y}\right)dx\\
&= J^k\int_{I_k}\psi_k\left(r_x\pd{q_h}{r}+s_x\pd{q_h}{s}+r_y\pd{q_h}{r}+s_y\pd{q_h}{s}\right)d\vec{r}\\
&= J^k\int_{I_k}\psi_k\left(\begin{bmatrix}\partial_r&\partial_s\end{bmatrix}\begin{bmatrix}r_x&s_x\\ r_y & s_y\end{bmatrix}\begin{bmatrix}q_h v_x\\q_hv_y\end{bmatrix}\right)d\vec{r}\\
&= J^k\int_{I_k}\psi_k(\partial_r(r_xq_hv_x+s_xq_hv_y))d\vec{r}+J^k\int_{I_k}\psi_k(\partial_s (r_yr_hv_x+s_yq_hv_y))d\vec{r}\\
&=J^kS_r(r_xv_x\hat{q}_h+s_xv_y\hat{q}_h)+J^kS_S(r_yv_x\hat{q}_h+s_yv_y\hat{q}_h)\\
&=S_r(F)+S_S(G)\\
\end{align*}
$$

$$\pd{\hat{p}}{t}=M^{-1}S_r(F)+M^{-1}S_S(G)+M^{-1}\int_{\partial\Omega_k}\psi_k  (q\vec{v}-q^* \vec{v}) \cdot \hat{n}\;ds$$
$$\pd{\hat{p}}{t}=\frac{1}{J_k}D_r(F)+\frac{1}{J_k}D_S(G)+M^{-1}\int_{\partial\Omega_k}\psi_k  (q\vec{v}-q^* \vec{v}) \cdot \hat{n}\;ds$$

## Maxwells Equations
## Euler Equations
## Navier Stokes
## Helmholz
