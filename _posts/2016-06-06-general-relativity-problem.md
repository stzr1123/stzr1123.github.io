---
layout: post
title: How general relativity problems can get tricky
category : physics
comments: true
---

## What will you get out of this post?

This post is great for you if you are currently taking an intro course in general relativity and would like to see an explicit and clean computation of Christoffel symbols. Otherwise you are just really interested in reading about a problem in gravitational waves.

This is also a great example of what it means to do "real" general relativity.

## The problem

As part of a homework assignment for an intro general relativity course I took, we were asked to solve the following "challenging" computational problem from Hartle's book *Gravity*,

>*__16.4__ Calculate the displacement $$\delta x^i_{(l)} (\lambda)$$ in the path of a light ray between two test masses from that of a flat-space straight line. Assume a gravitational wave of the form (16.2) having a definite frequency $$\omega$$.*

Here (16.2) refers to a gravitational wave of the form $$f(t-z)$$ such that $$\mid f(t-z) \mid << 1$$ traveling in the $$z$$ direction. We can use $$f(t-z)=a\sin{[\omega(t-z)]}$$ where $$0 < a << 1$$.

In this post I will work through my solutions to the problem which did not match the solutions we were given in the course. Discussing the problem with both TAs demonstrated that both of them were unsure why my math was correct but didn't lead to the solutions we were given. Further input from the professor helped resolve this conundrum and shed light into how solving for variations in geodesics can be confusing to someone new and someone seasoned in GR alike.

## Working out the problem

The metric can be written as a perturbation to Minkowski flat-space $$\eta_{\alpha\beta}$$,

$$
\begin{align*}
g_{\alpha\beta} &= \eta_{\alpha\beta} + h_{\alpha\beta} \\
&= \left( \begin{array}{cccc}
	-1 & 0 & 0 & 0 \\
	0 & 1 + f(t-z) & 0 & 0 \\
	0 & 0 & 1 - f(t-z) & 0 \\
	0 & 0 & 0 & 1
\end{array} \right)\text{.}
\end{align*}
$$

From the above it can noted that a gravitational wave of this form has transverse effects in the $$x$$ and $$y$$ directions only.

We now set up the problem in the following way. We begin with two test masses $$A$$ and $$B$$ with positions $$x^i_{(A)}=(0,0,0)$$ and $$x^i_{(B)}=(L,0,0)$$ such that there is a separation $$L$$ in the $$x$$ direction between the two. An unperturbed (flat-space) null geodesic $$l$$ (for a light ray) along the $$x$$ direction is given by the world line $$x = t$$ such that,

$$
\begin{align*}
\frac{dx^\alpha_{(l)}}{d \lambda} &= u^\alpha_{(l)} = (1,1,0,0)\text{,}
\end{align*}
$$

where $$\lambda = x$$ is an appropiate affine parameter for $$l$$.

The procedure is then to solve the geodesic equation. For a null geodesic,

$$
\begin{align}
\frac{d^2 x^\alpha_{(l)}}{d \lambda^2} &= -\Gamma^\alpha_{\beta \gamma} \frac{d x^\beta_{(l)}}{d \lambda} \frac{d x^\gamma_{(l)}}{d \lambda} \text{.}
\end{align}
$$

This is evaluated for the perturbed path $$\delta x^i_{(l)} (\lambda)$$ to first-order in the amplitude of the wave[^footnote_one]. Since the Christoffel symbols vanish for unperturbed flat-space, we are left with,

$$
\begin{align}
\frac{d^2 \delta x^i_{(l)}}{d \lambda^2} = \frac{d^2 \delta x^i_{(l)}}{d x^2} &= - \delta \Gamma^i_{\alpha \beta} \frac{d  x^\alpha_{(l)}}{d x} \frac{d x^\beta_{(l)}}{d x} \\
&= -(\delta \Gamma^i_{tt} u^t u^t + \delta \Gamma^i_{tx} u^t u^x + \delta \Gamma^i_{xt} u^x u^t + \delta \Gamma^i_{xx} u^x u^x) \\
&= -(\delta \Gamma^i_{tt} + 2 \delta \Gamma^i_{tx} + \delta \Gamma^i_{xx}) \text{.}
\end{align}
$$

In the last step we used the fact that $$u^t = u^x = 1$$ and $$\Gamma^i_{tx} = \Gamma^i_{xt}$$.

### Computing the Christoffel symbols

To compute the Christoffel symbols from the metric we use the general formula[^footnote_two],

$$
\begin{align}
\Gamma^\delta_{\beta \gamma} &= \frac{1}{2} g^{\alpha \delta} \left( \frac{\partial g_{\alpha \beta}}{\partial x^\gamma} + \frac{\partial g_{\alpha \gamma}}{\partial x^\beta} - \frac{\partial g_{\beta \gamma}}{\partial x^\alpha} \right)
\end{align} \text{.}
$$

But since we are interested in first-order changes in $$\Gamma$$ then,

$$
\begin{align}
\delta \Gamma^\delta_{\beta \gamma} &= \frac{1}{2} \eta^{\alpha \delta} \left( \frac{\partial h_{\alpha \beta}}{\partial x^\gamma} + \frac{\partial h_{\alpha \gamma}}{\partial x^\beta} - \frac{\partial h_{\beta \gamma}}{\partial x^\alpha} \right) \text{.}
\end{align}
$$

And so we compute,

$$
\begin{align}
\text{(i) } \delta \Gamma^i_{tt} &= \frac{1}{2} \eta^{\alpha i} \left( \frac{\partial h_{\alpha t}}{\partial x^t} + \frac{\partial h_{\alpha t}}{\partial x^t} - \frac{\partial h_{tt}}{\partial x^\alpha} \right) \\
&= 0 \text{ for } i = \left\{x,y,z \right\} \\
\text{(ii) } \delta \Gamma^i_{tx} &= \frac{1}{2} \eta^{\alpha i} \left( \frac{\partial h_{\alpha t}}{\partial x^x} + \frac{\partial h_{\alpha x}}{\partial x^t} - \frac{\partial h_{xt}}{\partial x^\alpha} \right) \\
&= 0 \text{ for } i = \left\{y,z \right\} \\
&= \frac{1}{2} \eta^{xx} \frac{\partial h_{xx}}{\partial x^t} = \frac{1}{2} \frac{\partial h_{xx}}{\partial x^t} = \frac{a\omega}{2} \cos{[\omega(t-z)]} \text{ for } i=x \\
\text{(iii) } \delta \Gamma^i_{xx} &= \frac{1}{2} \eta^{\alpha i} \left( \frac{\partial h_{\alpha x}}{\partial x^x} + \frac{\partial h_{\alpha x}}{\partial x^x} - \frac{\partial h_{xx}}{\partial x^\alpha} \right) \\
&= 0 \text{ for } i = y \\
&= -\frac{1}{2} \frac{\partial h_{xx}}{\partial x^z} = \frac{a\omega}{2} \cos{[\omega(t-z)]} \text{ for } i = z \\
&= \frac{1}{2} \frac{\partial h_{xx}}{\partial x^x} = ? \text{ for } i = x \text{.}\\
\end{align}
$$

I'd like to bring our attention to $$\delta \Gamma^x_{xx}$$. How should we compute this? There are two choices as far as I know,

#### [C.1] Choice One

This is the one that jumps straight to mind. Since the path $$l$$ is given by $$x = t$$ then,

$$
\begin{align}
\delta \Gamma^x_{xx} &= \frac{1}{2} \frac{\partial h_{xx}}{\partial x^x} = \frac{1}{2} \frac{\partial}{\partial x^x} a \sin{[\omega(x-z)]} \\
&= \frac{a\omega}{2} \cos{[\omega(x-z)]} \text{.}
\end{align}
$$

#### [C.2] Choice Two

This alternative was suggested by my professor. He said that the unperturbed path is given by $$x = t$$ but since we are expanding about this path the derivatives are explicitly evaluated at $$x = t$$. That is precisely what we did above for C.1. However, he argues that since $$f(t-z)$$ is no longer parametrized by $$t$$ along the unperturbed path of the null geodesic[^footnote_three], then you really have $$f(z) = a \sin{[\omega(t-z)]}$$. In this way, only derivatives of the form $$\frac{\partial h_{xx}}{\partial z}$$ will not vanish. Thus,

$$
\begin{align}
\delta \Gamma^x_{xx} &= \frac{1}{2} \frac{\partial h_{xx}}{\partial x^x} \\
&= 0 \text{.}
\end{align}
$$

By the same token we should re-compute and find that $$\delta \Gamma^x_{tx} = 0$$.

### Solving the geodesic equation

Having computed the first-order changes for the Christoffel symbols, we can now return to setting up the geodesic equation from,

$$
\begin{align}
\frac{d^2 \delta x^i_{(l)}}{d x^2} &= -(\delta \Gamma^i_{tt} + 2 \delta \Gamma^i_{tx} + \delta \Gamma^i_{xx}) \text{.}
\end{align}
$$

For $$i = \{ y,z\}$$ this reads,

$$
\begin{align}
\text{(i) }\frac{d^2 \delta x^y}{d x^2} &= - \left( \delta \Gamma^y_{tt} + 2 \delta \Gamma^y_{tx} + \delta \Gamma^y_{xx} \right) \\
&= 0 \\
\text{(ii) }\frac{d^2 \delta x^z}{d x^2} &= - \left( \delta \Gamma^z_{tt} + 2 \delta \Gamma^z_{tx} + \delta \Gamma^z_{xx} \right) \\
&= -\frac{a\omega}{2} \cos{[\omega(t-z)]}
\end{align}
$$

For $$i = x$$ we can apply [C.1] and [C.2] respectively,

$$
\begin{align}
\text{(iii) } \frac{d^2 \delta x^x}{d x^2} &= - \left( \delta \Gamma^x_{tt} + 2 \delta \Gamma^x_{tx} + \delta \Gamma^x_{xx} \right) \\
\text{[C.1] } &= \frac{3a\omega}{2} \cos{[\omega(t-z)]} \\
\text{[C.2] } &= 0
\end{align}
$$

>NB: In my discussion with the TA we found justification in the results of [C.1]. A light ray emitted along the $$x$$ axis should experience a change in its trajectory under the gravitational wave. The rest masses do not move.

All that is left is to solve the differential equations (i), (ii) and (iii) using an appropriate choice of boundary conditions and we'd have an equation of motion for our displacement. Ultimately, solving for [C.1] will add an additional displacement which is unwarranted. Solving for [C.2] provides the right answer for that displacement in the $$x$$ direction.

I won't actually solve the equations here... Setting up the problem with the above steps is definitely the hardest part computationally and conceptually. The last step is left to you.

## Conclusions

This problem is flagged as "challenging" in *Gravity* and it certainly is so. It brings to light that problems in GR can get tricky if you don't have a solid understanding of what your variables represent. In this case, it revolved around how to interpret and computationally implement the $$x=t$$ path under a perturbation.

A decision based on an incredible subtle conceptual difference (which is hard even now to be fully convinced about), leads to a completely different answer no longer in agreement with the theory of gravitational waves. Student and TA both fell for it.

## Footnotes

[^footnote_one]: I've learned that part of the goal of GR is to linearize toy metrics so that these are solutions to the Einstein equation. First-order expansion is justified in this case since gravitational waves are weak effects and can be studied as perturbations to flat-space (i.e. "Just a wave in special relativity" as my professor would say).

[^footnote_two]: If you are unfamiliar with Christoffel symbols, all you need to know right away to understand the math is that for $$\Gamma^\mu_{\alpha \beta}$$, $$\alpha$$ is the basis vector being differentiated, $$\beta$$ is the coordinate with respect to which $$\alpha$$ is being differentiated and $$\mu$$ is the component of the resulting vector derivative. So, in general, if you have three basis vectors then there are $$3^3$$ Christoffel symbols to compute. Honestly, textbooks should be more straightforward about them.

[^footnote_three]: "if you know $$x$$, you automatically know $$t$$."
