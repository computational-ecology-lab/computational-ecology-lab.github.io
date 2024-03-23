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

Note that this equation doesn't explicitly involve $t$, which can be taken as an external parameterisation. We can then interpret $x$ and $\dot{x}$ as 1D vectors with the operator $f$ as a geometrical shift from $x$ to $\dot{x}$, independently of $t$.

If we are interested in the behaviour around an equilibrium point $x_0$, we can linearise $\dot{x}$ as a function of $x$ around that point. This is the same as the curved surface of Earth being 'linearised' around us in the very small region delimited by our line of sight. For this, we consider the Taylor series expansion of the operator around the equilibrium $x_0$:

$$\dot{x}=f(x)=f(x_0)+\frac{df}{dx}(x_0)[x-x_0]+\frac{1}{2}\frac{d^f}{dx^2}(x_0)[x-x_0]^2+...=\sum_n\frac{d^nf}{dx^n}(x_0)\frac{[x-x_0]^n}{n!}.$$

All derivatives are evaluated at equilibrium, so they are numbers, constant coefficients. Therefore, this expansion is a mapping from $f$ to an infinite polynomial, which is a recipe allowing us to write a function as a polynomial. At equilibrium, we have $\dot{x}(x_0)=f(x_0)=0$. Then, since we are very close to the equilibrium, the distance $[x-x_0]$ is very close to zero. The process of linearisation is to approximate to zero all higher orders $[x-x_0]^n$ for $n>1$. Thus, the linearized system, which is valid only if we are close to equilibrium, becomes:


$$\dot{x}=f(x)=\frac{df}{dx}(x_0)[x-x_0]=\lambda[x-x_0].$$

We write $$\frac{df}{dx}(x_0)=\lambda$$ because it is a constant coefficient anyway. Then, we can define $z=[x-x_0]$ (with $\dot{z}=\dot{x}$, because $x_0$ is a constant) as the displacement from the equilibrium. Then, we solve this system for $z(t)$, which is a simple exponential solution:

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

**2D Dynamical system**

Now, we do the same for a 2D system. Consider the vector

$$
\begin{align}
    v &= \begin{bmatrix}
           x \\
           y \\
         \end{bmatrix}.
\end{align}
$$

A dynamical law connects $v$ with its derivative $\dot{v}$:

$$\begin{align}
    \dot{v} &= \begin{bmatrix}
           f(x,y) \\
           g(x,y) \\
         \end{bmatrix}.
\end{align}$$

We can use the same expansion on both entries to linearise the system around the equilibrium $(x_0,y_0)$. But now the maps $f$ and $g$ are functions of two variables. Therefore, they can change by varying both $x$ and $y$.

Now we have to introduce partial derivatives. Suppose we want to produce a variation $df$. For that, we cause a variation $dx$ and a variation $dy$, giving for $f$ two independent sources of variation. The partial derivatives are the coefficient of each source, geometrically meaning the tangents of the shadows of $f$ projected on $f-x$ and $f-y$ planes. Thus,

$$df = \frac{\partial f}{\partial x}dx + \frac{\partial f}{\partial y}dy.$$

This means that the polynomial expansion for two variables will consider both partial derivatives, computing perturbations away from equilibrium for both dimensions:

$$\begin{align}
    \dot{v} &= \begin{bmatrix}
           f(x_0,y_0)+\frac{\partial f}{\partial x}(x_0,y_0)[x-x_0]+\frac{\partial f}{\partial y}(x_0,y_0)[y-y_0]+... \\
           g(x_0,y_0)+\frac{\partial g}{\partial x}(x_0,y_0)[x-x_0]+\frac{\partial g}{\partial y}(x_0,y_0)[y-y_0]+... \\
         \end{bmatrix}.
\end{align}$$

Now we impose that $\dot{v}$ is zero at equilibrium, so $f(x_0,y_0)=g(x_0,y_0)=0$, then we define the vector of displacement from equilibrium

$$\begin{align}
    z &= \begin{bmatrix}
           [x-x_0] \\
           [y-y_0] \\
         \end{bmatrix}.
\end{align}$$

Then, the linearised system becomes

$$\begin{align}
    \dot{z} &= \begin{bmatrix}
           \frac{\partial f}{\partial x}(x_0,y_0)[x-x_0]+\frac{\partial f}{\partial y}(x_0,y_0)[y-y_0] \\
           \frac{\partial g}{\partial x}(x_0,y_0)[x-x_0]+\frac{\partial g}{\partial y}(x_0,y_0)[y-y_0] \\
         \end{bmatrix}=Jz,
\end{align}$$

where we define the Jacobian matrix of the system at this point as

$$\begin{align}
    J &= \begin{bmatrix}
           \frac{\partial f}{\partial x}(x_0,y_0)\quad \frac{\partial f}{\partial y}(x_0,y_0)  \\
           \frac{\partial g}{\partial x}(x_0,y_0)\quad \frac{\partial g}{\partial y}(x_0,y_0) \\
         \end{bmatrix}.
\end{align}$$

The Jacobian is the generalisation of the derivative for multidimensional systems. Instead of a single number, it is a matrix comprising all partial derivatives of the system. Here, we present the Jacobian evaluated at the equilibrium point, which is also called the community matrix, in the context of community ecology. Note that the Jacobian itself is a function of $(x,y)$, but when evaluated at the equilibrium it becomes a simple constant matrix.

Now, in the same way as the 1D system, we can expect the solution of the linearised system $\dot{z}=Jz$ to be an exponential:

$$z(t) = ce^{\lambda t},$$

where $c$ is a vector of initial conditions and $\lambda$ is a number determining the behaviour of the linearized system around the equilibrium. For this case, how can we know the identities of $c$ and $\lambda$? As we will see, they are not single objects, they are the eigenvectors and eigenvalues of $J$.

**Eigenvalue calculation**

If we derive the exponential solution and identify with the dynamical rule $Jz$, we obtain the following equation:

$$Jc = \lambda c.$$

This equation is telling us that the operator $J$ applied to the vector $c$ does not project it on another direction, but only changes its size by a factor $\lambda$. From this, we can build a projection to zero:

$$(J-\lambda I)c=0,$$

where $I$ is the identity matrix. Since the vector $c$ is not zero, it follows that the matrix operator $(J-\lambda I)$ is doing something special: it's taking $c$ to zero, regardless of what $c$ is, which is like an algebraic black hole. Therefore, this matrix is a singular matrix, it causes an indetermination, promoting 'loss of information' as it brings the entire vector space to zero. The condition for singular matrices is to have a zero determinant, which is the equivalent of a scalar operator being zero in a 1D system.

***Why the determinant?*** We can think of the determinant of a matrix as a type of scalar substitute for it. More precisely, it is the area scaling of the transformation carried out by the matrix, how much the transformation expands and contracts the vector space. We can even derive the determinant formula for a 2D system from the area scaling of a paralelogram defined by two vectors being transformed by the matrix. The determinant for 2D matrices is:

$$\begin{align}
    det[\begin{bmatrix}
           \quad a\quad\quad b\quad  \\
           \quad c\quad\quad d\quad \\
         \end{bmatrix}]=ad-bc.
\end{align}$$

Then, the task of calculating $\lambda$ becomes finding the roots of the following equation:

$$\begin{align}
    det[\begin{bmatrix}
           \quad a-\lambda\quad\quad b\quad  \\
           \quad c\quad\quad d-\lambda\quad \\
         \end{bmatrix}]=\lambda^2-\lambda(a+d)+ad-bc=0,
\end{align}$$

where $\frac{\partial f}{\partial x}(x_0,y_0)=a$, $\frac{\partial f}{\partial y}(x_0,y_0)=b$, $\frac{\partial g}{\partial x}(x_0,y_0)=c$, $\frac{\partial g}{\partial y}(x_0,y_0)=d$. We can rewrite this equation in a way that hints to its generalization to higher dimensions involving the trace and the determinant of $J$:

$$\lambda^2-Tr(J)\lambda+det(J)=0$$

Since this is a second-order equation, there are two solutions: $\lambda_1$ and $\lambda_2$. For each of these eigenvalues, there is an associated eigenvector that we calculate from $Jc_1=\lambda_1c_1$ (and the same for $\lambda_2$ and $c_2$), of which only the direction is important, not the magnitude.

Once we have the eigenvalues and eigenvectors, the complete solution for the system of differential equations $\dot{z}=Jz$ is a linear combination of the solutions given by each pair $(\lambda,c)$. You can verify that the linear combination is also a solution by deriving it (or by noting that it has to be, since it's a linear system). Then:

$$z(t) = a_1c_1e^{\lambda_1 t} + a_2c_2e^{\lambda_2 t},$$

where $a_1$ and $a_2$ are constant numbers we determine from the initial state system $z(0)=a_1c_1+a_2c_2$.

Given the final solution, we can assess the stability of the equilibrium. From an initial displacement $z(0)$, if all eigenvalues $(\lambda_1,\lambda_2)$ are negative, the system returns to the equilibrium. If any of the eigenvalues is positive, even if the other components return to the equilibrium value, at least one diverges away. Therefore, the equilibrium is stable if all eigenvalues are negative.

Let's show an example with a simplified version of the classic Lotka-Volterra predator-prey system:

$$\begin{align}
    \dot{v} &= \begin{bmatrix}
           x-\alpha xy \\
           \alpha xy -y \\
         \end{bmatrix}.
\end{align}$$

The Jacobian of the system is

$$\begin{align}
    J(x,y)=\begin{bmatrix}
           \quad 1-\alpha y\quad\quad -\alpha x\quad  \\
           \quad \alpha y\quad\quad 1-\alpha x\quad \\
         \end{bmatrix}.
\end{align}$$

This system has an equilibrium point $x_0=y_0=1/\alpha$. The Jacobian at this point is then

$$\begin{align}
    J=\begin{bmatrix}
           \quad 0\quad\quad -1\quad  \\
           \quad 1\quad\quad 0\quad \\
         \end{bmatrix}.
\end{align}$$

The characteristic equation for the eigenvalues is then

$$\lambda^2+1=0.$$

The solutions are imaginary: $\lambda_1=i$ and $\lambda_2=-i$. What happens if the eigenvalues have imaginary components? They represent oscillations, so it's neither stable nor unstable. The associated eigenvectors are the directions

$$\begin{align}
    c_1=\begin{bmatrix}
           1  \\
           i \\
         \end{bmatrix}, \quad c_2=\begin{bmatrix}
           i  \\
           1 \\
         \end{bmatrix}.
\end{align}$$

Therefore, we can write the solution for linearized displacements from the equilibrium as

$$\begin{align}
    z(t)=a_1\begin{bmatrix}
           1  \\
           i \\
         \end{bmatrix}e^{it} + a_2\begin{bmatrix}
           i  \\
           1 \\
         \end{bmatrix}e^{-it}.
\end{align}$$

***How can the solution be complex if $z(t)$ is real?*** The answer is that the solution is, in fact, real. It can be rewritten in terms of real sines and cosines (using Euler's formula), and this also explains why imaginary parts of eigenvalues translate into oscillations.

Complex eigenvalues can be divided into real and imaginary parts. The real parts will determine the stability, so the criteria actually states that the largest real part of an eigenvalue has to be negative for the equilibrium to be stable. The imaginary parts determine oscillations. That's because, in the end, the real solution features real parts of the eigenvalues leading the exponentials and the imaginary parts transformed into sines and cosines. In the case of the Lotka-Volterra above, the real parts are all zero, so the equilibrium is actually neutral. Thus, the system oscillates around the equilibrium with neutral amplitude (it depends on the size of the perturbation).
