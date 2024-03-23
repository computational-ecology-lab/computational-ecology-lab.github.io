---
published: True
title: "Modelling Coffee: A quick introduction to Linear Stability Analysis"
author: Gui Araujo
layout: post
group: news
tags: 
---

In this tutorial, Gui explains how to perform Linear Stability Analysis in the way that many classical theoretical papers in ecology deal with this type of stability in the context of food webs.

**Aims**

Our main goal is to understand the elements of the linear stability analysis of a multidimensional dynamical system. This requires an intuition of elements such as the Jacobian and the eigenvalues of a matrix. Our task is divided in 3 steps:

1. Understanding the reasoning of the procedure by looking at the 1D system.

2. Developing the 2D form analogously to the 1D form.

3. Calculating the eigenvalues, which will allow us to perform the stability analysis in 2D.

**1D Dynamical system**

Our variable of interest is $x(t)$, which is a curve parameterised by the temporal variable $t$. The time-derivative of $x$, $\dot{x}=\frac{dx}{dt}$, is another curve parameterised by $t$. In a dynamical system, we interpret $x$ and $\dot{x}$ as two different functions of $t$ inhabiting the same space. The usual dynamical law to determine $x$ is to define an operation that transforms $x$ into $\dot{x}$:

$$f:x\to\dot{x}$$

such that

$$\dot{x}=f(x).$$

Note that this equation doesn't explicitly involve $t$, which can be taken as an external parameterisation. We can then interpret $x$ and $\Dot{x}$ as 1D vectors with the operator $f$ as a geometrical shift from $x$ to $\Dot{x}$, independently of $t$.

If we are interested in the behaviour around an equilibrium point $x_0$, we can linearise $\Dot{x}$ as a function of $x$ around that point. This is the same as the curved surface of Earth being 'linearised' around us in the very small region delimited by our line of sight. For this, we consider the Taylor series expansion of the operator around the equilibrium $x_0$:

$$\dot{x}=f(x)=f(x_0)+\frac{df}{dx}(x_0)[x-x_0]+\frac{1}{2}\frac{d^f}{dx^2}(x_0)[x-x_0]^2+...=\sum_n\frac{d^nf}{dx^n}(x_0)\frac{[x-x_0]^n}{n!}.$$

All derivatives are evaluated at equilibrium, so they are numbers, constant coefficients. Therefore, this expansion is a mapping from $f$ to an infinite polynomial, which is a recipe allowing us to write a function as a polynomial. At equilibrium, we have $\Dot{x}(x_0)=f(x_0)=0$. Then, since we are very close to the equilibrium, the distance $[x-x_0]$ is very close to zero. The process of linearisation is to approximate to zero all higher orders $[x-x_0]^n$ for $n>1$. Thus, the linearized system, which is valid only if we are close to equilibrium, becomes:


$$\dot{x}=f(x)=\frac{df}{dx}(x_0)[x-x_0]=\lambda[x-x_0].$$

We write $$\frac{df}{dx}(x_0)=\lambda$$ because it is a constant coefficient anyway. Then, we can define $z=[x-x_0]$ (with $\Dot{z}=\Dot{x}$, because $x_0$ is a constant) as the displacement from the equilibrium. Then, we solve this system for $z(t)$, which is a simple exponential solution:

$$\frac{dz}{dt}=\lambda z$$

$$z(t)=z(0)e^{\lambda t}.$$

Then, if we perturb the equilibrium with a displacement $z(0)$, will the system return to equilibrium or will it diverge away from it? It all depends on the derivative $\lambda$. If $\lambda<0$, then the equilibrium will be restored, making this equilibrium stable (what happens if $\lambda=0$?). Therefore, we have the condition for stability of the equilibrium $x_0$:

$$\frac{df}{dx}(x_0)<0,$$

which means that the derivative of the curve defining $\dot{x}$ as a function of $x$, when evaluated at the equilibrium, determines its stability.

As an example, consider the logistic growth:

$$\dot{x}=rx(1-\frac{x}{K}).$$

It has an equilibrium $x_0=K$. The linearised system around this equilibrium is

$$\dot{x}=-r[x-K].$$

Then, if $-r<0$, this equilibrium is stable. That is $r>0$.

$$ACF(\tau) = \frac{\langle (M(t) - \langle M(t) \rangle ) (M(t+\tau)- \langle M(t) \rangle) \rangle}{\langle (M(t) - \langle M(t) \rangle)^{2} \rangle }$$


When I see an equation my first though is “how do I calculate that?”. In my opinion Tidyverse has some cool operations which can be used to translate the equation into a specific value. For example, the averages in the ACF are calculated over different things, which can be captured by grouping. 


The last part is to find t
