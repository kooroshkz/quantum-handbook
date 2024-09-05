---
title: Coordinate systems
---
# 2. Coordinate systems

The lecture on coordinate systems consists of 3 parts, each with their own video:

- [2.1. Introduction to coordinate systems: Cartesian and polar](#21-introduction-to-coordinate-systems-cartesian-and-polar)
- [2.2. Converting derivatives between coordinate systems](#22-converting-derivatives-between-coordinate-systems)
- [2.3. Coordinate systems in 3D](#23-coordinate-systems-in-3d)

**Total video length: 35 minutes and 13 seconds**

## 2.1. Introduction to coordinate systems: Cartesian and polar

<iframe width="100%" height=315 src="https://www.youtube-nocookie.com/embed/CPMrsQlNxS8?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Cartesian coordinates

The most common coordinates are *Cartesian coordinates*, where we use a
number $n$ of perpendicular axes. The coordinates corresponding to these
axes are $x_j$ where $j=1, \ldots, n$.

Cartesian coordinates are simple to describe and operate on. The coordinate axes are 
straight lines perpendicular to each other. It is therefore
very easy to do calculations in Cartesian coordinates. For example,
the distance $\Delta s$ between two points $(x_1, x_2, \ldots, x_n)$
and $(x'_1, x'_2, \ldots, x'_n)$ can be quickly computed using a general formula for n-dimensions:

$$\Delta s^2 = (x'_1 - x_1)^2 + (x'_2 - x_2)^2 + \ldots + (x'_n - x_n)^2.$$

(A space with such a distance definition is called an *Euclidean
space*.)

In mathematics, we are often dealing with so-called *infinitesimally* small
distances, for example in the definition of derivatives and integrals.
In Cartesian coordinates, the expressions for infinitesimal distances $ds$ and
infinitesimal volumes $dV$ are given as:

!!! info "Infinitesimal segment and volume elements in n-dimensional Cartesian coordinates"
    $$ds = \sqrt{dx_1^2 + dx_2^2 + \ldots + dx_n^2}$$
    $$dV = dx_1 dx_2 \ldots dx_N.$$

The formula for $dV$ also indicates that in Cartesian coordinates, the integral
over a volume can be expressed as individual integrals over all coordinate directions:
$$\int dV = \idotsint dx_1 dx_2 \ldots dx_N.$$

Cartesian coordinates are used a lot and they are particularly suitable for
infinite spaces or for rectangular volumes.

<figure markdown>
  ![image](figures/Coordinates_5_1.svg)
  <figcaption>An example of a vector drawn in a 2D Cartesian plane</figcaption>
</figure>

### Polar coordinates

#### Definition

It often turns out that a change to a different type of coordinate
system makes mathematics easier. For example, if you want to describe vibrations of a
circular drum, polar coordinates become very convenient. These are
defined for a two-dimensional space (a plane). The position on this plane is characterised by two
coordinates: the *distance* $r$ between the point and the origin, and by the
angle ($\varphi$) between the line connecting the point to the origin and the $x$-axis. The radius is therefore always a non-negative number $r \geq 0$, and the range for the polar angle is $\varphi \in \left< 0,2\pi \right)$

Note that each Cartesian coordinate has a *dimension* of length. 
In polar coordinates, the radius $r$ has a dimension of *length*, but
the angular coordinate $\varphi$ is dimensionless.

<figure markdown>
  ![polarplot](figures/Coordinates_7_0.svg)
  <figcaption>In this example of a polar plot, you can distinguish the radial coordinate $( 0.2, 0.4, \text{ etc.. })$ from the angular one expressed in degrees $( 0^\circ, 45^\circ, \text{ etc..} )$</figcaption>
</figure>


The plot below shows a point on a curve with the polar coordinates
$(r,\varphi)$ indicated. From this, we can see that the *Cartesian*
coordinates $(x,y)$ of the point are related to the polar ones as
follows:

$$\begin{equation} x = r \cos\varphi; \end{equation}$$
$$\begin{equation} y = r \sin \varphi.\end{equation}$$

<figure markdown>
  ![image](figures/Coordinates_9_0.svg)
  <figcaption></figcaption>
</figure>

#### The inverse relation

!!! info "Inverse relation between polar and Cartesian coordinate systems"
    \begin{equation} r=\sqrt{x^2 + y^2}; \label{rxy}\end{equation}
    \begin{equation} \varphi=\begin{cases}
    \arctan(y/x) & \text{$x>0$,}\\
    \pi + \arctan(y/x) & \text{$x<0$ and $y>0$,}\\
    -\pi + \arctan(y/x) & \text{$x<0$ and $y<0$.}
    \end{cases} \label{phixy}\end{equation}

The last formula for $\varphi$ warrants a closer explanation: It is easy
to see that $\tan(\varphi)=y/x$, but this is not a unique relation, due to
the fact that the $\tan$ has different branches. Convince yourself that
the expression above is correct for all the four sectors!

#### Distances and areas

Now suppose we want to calculate the distance between two points, one
with polar coordinates $(r_1, \varphi_1)$, and the other with
$(r_2, \varphi_2)$. This looks like a difficult exercise. One possible
way to perform this is by translating the polar coordinates into
Cartesian coordinates and using the expression given above for this
distance: $$\Delta s^2 = (x_1 - x_2)^2 + (y_1 - y_2)^2,$$ so
$$\Delta s^2 = (r_1\cos\varphi_1 - r_2 \cos \varphi_2)^2 + (r_1\sin\varphi_1 - r_2 \sin \varphi_2)^2$$
which is not a very convenient expression.

If we consider two points which are *very close*, the analysis
simplifies however. We can use the geometry of the problem to find the
distance (see the figure below).

<figure markdown>
  ![image](figures/Coordinates_11_0.svg)
  <figcaption></figcaption>
</figure>

When going from point 1 to point 2, we first traverse a small circular
arc of radius $r_1$ and then we move a small distance radially outward
from $r_1$ to $r_2$. Provided the difference between the angles
$\varphi_1$ and $\varphi_2$ is (very) small, these paths are
approximately perpendicular and we can use Pythagoras’ theorem to find
the distance $d s$. Note that the arc is approximately straight –
it has a length $r_1 d \varphi$, where
$d \varphi = \varphi_2-\varphi_1$. So we have:
$$d s^2 = (d r)^2 + (arc~length)^2   = (d r)^2 + r_1^2 (d \varphi)^2 .$$

We can use the same arguments also for the area: since the different
segments are approximately perpendicular, we find the area by simply
multiplying them:

!!! info "Infinitesimal surface element in polar coordinates"
    	$$dA = r dr d\varphi.$$

This is an important formula to remember for integrating in polar
coordinates!  The extra $r$ that appears here can be intuitively
understood: the area swept by an angle difference $d\varphi$
*increases* as we move further away from the origin.

!!! check "Example: Integrating over a circular area"
    To check the area element we just derived, let us compute a simple
    integral. We compute the integral over a circle with radius $r_0$
    with a very simple function that equals to $1$. In this case,
    we expect to get as a result the are of the region we integrate over.

    We find:

    $$
    \int_0^{2\pi} d\varphi \int_0^{r_0} r dr =\\
    2\pi \int_0^{r_0} r dr = 2 \pi \frac{1}{2} r_0^2 = \pi r_0^2,
    $$

    which is indeed the area of a circle with radius $r_0$.

## 2.2. Converting derivatives between coordinate systems

<iframe width="100%" height=315 src="https://www.youtube-nocookie.com/embed/NGQWGx71w98?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


Important equations in physics often involve derivatives given in terms
of Cartesian coordinates. One prominent example are equations of the form
$$\left(\frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2}\right)
f(x, y) = \ldots.$$
The derivative operator $\left(\frac{\partial^2}{\partial x^2} +
\frac{\partial^2}{\partial y^2}\right)$ is so common it has its own name:
the Laplacian (here for two-dimensional space).

This equation is universal, but for particular situations it might be
advantageous to use a different coordinate system, such as polar coordinates
for a system with rotational symmetry. The question then is: How does the
corresponding equation look like in a different coordinate system?

There are different ways to find the answer. Here, we will focus on
directly deriving the transformed equation through an explicit calculation
involving the chain rule for a function of several variables.

!!! info "Chain rule for a multi-variable function"
    Let $f$ be a function of $n$ variables: $f(y_1, y_2, \ldots, y_n)$,
    as well as $g_i(x_1, x_2, \ldots, x_n)$ for $i=1,2,\ldots, n$. Then

    $$\frac{\partial}{\partial x_i} = \sum_{j=1}^n
    \frac{\partial f}{\partial y_j} \frac{\partial g_j}{\partial x_i}$$

We start by replacing the function $f(x, y)$ by a function in polar coordinates
$f(r, \varphi)$, and ask what is $\frac{\partial}{\partial x} f(r, \varphi)$. When
we look at this expression, we need to understand what it *means* to take the derivative
of a function of $r, \varphi$ in terms of $x$?

For this, we need to realize that there are relations between the coordinate systems.
In particular, $r = r(x,y)$ and $\varphi = \varphi(x, y)$ as defined in equations
of [the inverse relations](#the-inverse-relation). In fact, we have been rather sloppy in our notation above,
as the functions $f(x,y)$ and $f(r, \varphi)$ do not mean that I substitute $x=r$
and $y=\varphi$! It is more precise to state that there are two diferent
functions $f_\text{cart}(x,y)$ and $f_\text{polar}(r, \varphi)$ that are equivalent,
in the sense that

$$f_\text{cart}(x, y) = f_\text{polar}(r(x,y), \varphi(x,y))$$

In physics, we usually never write this down explicitly, but we are aware that these
are two different functions from the fact that they use different coordinates.

With this information, we can now apply the chain rule:

$$ \frac{\partial}{\partial x} f(r, \varphi) =
\frac{\partial f}{\partial r} \frac{\partial r(x, y)}{\partial x} +
\frac{\partial f}{\partial \varphi} \frac{\partial \varphi(x,y)}{\partial x}
$$

and it is now a matter of (tedious) calculus to arrive at the right result.
This is the task of exercises 3 and 4, which lead you to compute the Laplacian
in polar coordinates.

!!! warning "Inverse function theorem"
    In this calculation, one might be tempted to use the inverse
    function theorem to compute derivatives like
    $\frac{\partial \varphi}{\partial x}$ from the much simpler
    $\frac{\partial x}{\partial \varphi}$. However, note that here we
    are dealing with functions depending on several variables, so an appropriate
    *Jacobian* has to be used (see [Wikipedia](https://en.wikipedia.org/wiki/Inverse_function_theorem)). A direct calculation is in this particular case considerably easier.

Note that this procedure also applies to transformations to other coordinate systems,
although the calculations can become quite tedious. In conventional cases,
it is usually advised to look up the correct form.

## 2.3. Coordinate systems in 3D

<iframe width="100%" height=315 src="https://www.youtube-nocookie.com/embed/VjUbnZN1BvA?rel=0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### Cylindrical coordinates

Three dimensional systems may have axial symmetry. An example is an
electrically charged wire of which we would like to calculate the
electric field, or a current-carrying wire for which we would like to
calculate the magnetic field. For such problems, the most convenient
coordinates are *cylindrical coordinates*. For a further convenience, we choose
the symmetry-axis as the $z$-axis. Note that this allowed, because we may
choose the coordinate system ourselves - it is not imposed by the
problem.

Cylindrical coordinates are defined straightforwardly: we use polar
coordinates $r$ and $\varphi$ in the $xy$ plane, and the distance $z$
along the symmetry-axis as the third coordinate. The radius is therefore again always defined as a non-negative number $r \in \left<0, \infty \right)$, and the range for the azimuthal angle is analogically $\varphi \in \left< 0,2\pi \right)$. The *height* $z$ along the cylinder axis can take any real value, hence $z \in \mathbb{R}$ . If the axis system is
chosen in physical space, we have two coordinates which have the
dimension of a distance: $r$ and $z$. The other coordinate,
$\varphi$ is of course dimensionless.

What is the distance traveled along a path when we express this in
cylindrical coordinates? Let’s consider an example shown in the figure below.

<figure markdown>
  ![image](figures/Coordinates_13_0.svg)
  <figcaption></figcaption>
</figure>

We want to find the length of the (small) red segment $d s$. By
inspecting the figure, we see that the horizontal (i.e. parallel to the
$xy$-plane) segment $d l$ is perpendicular to the vertical segment
$dz$. Using for $d l$ the length we obtained before for a line
segment in the $xy$ plane expressed in polar coordinates, we
immediately find:
$$d s^2 = d l^2 + d z^2 = d r^2 + r^2 d \varphi^2 + d z^2.$$
The volume element is consequently given as:

!!! info "Infinitesimal volume element in cylindrical coordinates"
    $$dV = r dr d\varphi dz.$$

### Spherical coordinates

For problems with spherical symmetry, we use *spherical coordinates*.
These work as follows. For a point $\bf r$ in 3D space, we can specify
the position of that point by specifying its (1) distance to the origin
and (2) the direction of the line connecting the origin to our point.
The specification of this direction can be identified with a point on a
sphere which is centered at the origin:

<figure markdown>
  ![image](figures/Coordinates_15_0.svg)
  <figcaption>The position of a point on the sphere is specified using the radius $r$ and two angles (azimuthal)
$\varphi$ and (polar) $\theta$ in the given order </figcaption>
</figure>

!!! warning "Parameter ranges in spherical coordinates"
    - The radius ($r$) is defined for $r \in \left<0, \infty \right)$ </br>
    - The azimuthal angle ($\varphi$) has the range of $\varphi \in \left< 0, 2\pi \right)$  </br>
    - The polar angle ($\theta$) has the range $\theta \in \left<0, \pi \right>$ 

!!! warning
    In mathematics, the angles are often labeled the other way
    around: there, $\varphi$ is used for the angle between a line running from
    the origin to the point of interest and the $z$-axis, and $\theta$ for
    the angle of the projection of that line with the $x$-axis. The
    convention used here is customary in physics. 

The relation between Cartesian and spherical coordinates is defined by:
!!! info "The relation between Cartesian and spherical coordinates"
    $$x = r \cos \varphi \sin \theta$$
    $$y = r \sin\varphi \sin \theta$$ $$z = r \cos\theta$$ 

The inverse transformation is easy to find: 
!!! info "The inverse relation between Cartesian and spherical coordinates"
    $$r = \sqrt{x^2+y^2+z^2}, \qquad r \in \left<0, \infty \right)$$
    $$\varphi = \begin{cases} \arctan(y/x) &{\rm for ~} x>0; \\
    \pi + \arctan(y/x) & {\rm for ~} x<0 {\rm ~ and ~} y>0;\\
    -\pi + \arctan(y/x) &{\rm for ~} x<0 {\rm ~ and ~} y<0.
    \end{cases}, \qquad \varphi \in \left< 0,2\pi \right)$$ 
    $$\theta = \arccos(z/\sqrt{x^2+y^2+z^2}), \qquad \theta \in \left< 0,\pi \right> $$
    
These relations can be derived from the following figure:

<figure markdown>
  ![image](figures/Coordinates_17_0.svg)
  <figcaption></figcaption>
</figure>

The distance related to a change in the spherical coordinates is
calculated using Pythagoras’ theorem. The length $ds$ of a short segment
on the sphere with radius $r$ corresponding to the changes in the polar
angles of $d\theta$ and $d\varphi$ is given as
$$dl^2 = r^2 \left(\sin^2 \theta d\varphi^2 + d\theta^2\right).$$
In order to verify this, it is important to realize that all points with
*the same* coordinate $\theta$ span a circle in a horizontal plane
with a radius $r\sin\theta$ as shown in the figure below.

From this, we can also infer that for a segment with a radial component
$dr$ in addition to the displacement on the surface of the sphere, the combined displacement is:
$$ds^2 = r^2 \left(\sin^2 \theta d\varphi^2 + d\theta^2\right) + dr^2.$$

The picture below shows the geometry behind the calculation of this
displacement.

<figure markdown>
  ![image](figures/Coordinates_19_0.svg)
  <figcaption></figcaption>
</figure>


From these arguments we can again also find the volume element, it is
here given as

!!! info "Infinitesimal volume element in spherical coordinates"
    $$dV = r^2 \sin\theta dr d\theta d\varphi.$$

## 2.4. Summary

We have discussed four different coordinate systems:

1.  !!! tip "Cartesian coordinates" 
    $${\bf r} = (x_1, \ldots, x_n)$$
    $$ x_{n} \in \mathbb{R}$$
    This systems can be used for any dimension $n$. It is particularly convenient for: infinite spaces, systems
    with rectangular symmetry.
    Distance between two points ${\bf r} = (x_1, \ldots, x_n)$ and
    ${\bf r}' = (x'_1, \ldots, x'_n)$:
    $$\Delta s^2 = (x'_1 - x_1)^2 + (x'_2 - x_2)^2 + \ldots + (x'_n - x_n)^2.$$

2.  !!! tip "Polar coordinates" 
    $${\bf r} = (r, \varphi)$$
    $$ r \in \left<0, \infty \right), \quad \varphi \in \left< 0,2\pi \right) $$
    This system can be used in two dimensions. It is particularly suitable for systems with circular symmetry or functions
    given in terms of these coordinates. <br/>
    Infinitesimal distance: $$ds^2 = dr^2 + r^2 d\varphi^2.$$
    Infinitesimal area: $$dA = r dr d\varphi.$$

3.  !!! tip "Cylindrical coordinates" 
    $${\bf r} = (r, \varphi, z)$$
    $$ r \in \left<0, \infty \right), \quad \varphi \in \left< 0,2\pi \right), \quad z \in \mathbb{R} $$ 
    This system can be used in three dimensions. It is particularly suitable for systems with axial symmetry
    or functions given in terms of these coordinates. <br/>
    Infinitesimal distance: $$ds^2 = dr^2 + r^2 d\varphi^2 + dz^2.$$
    Infinitesimal volume: $$dV = r dr d\varphi dz.$$

4.  !!! tip "Spherical coordinates" 
    $${\bf r} = (r, \varphi, \theta)$$
    $$ r \in \left<0, \infty \right), \quad \varphi \in \left< 0,2\pi \right), \quad \theta \in \left< 0,\pi \right> $$
    This system can be used in three dimensions. It is particularly suitable for systems with spherical
    symmetry or functions given in terms of these coordinates. <br/>
    Infinitesimal distance: 
    $$ds^2 =r^2 (\sin^2 \theta d\varphi^2 + d\theta^2) +  dr^2 .$$
    Infinitesimal volume:
    $$dV = r^2 \sin(\theta) dr d\varphi d\theta.$$ 

## 2.5. Problems

1.  [:grinning:] *Warm-up*

    1.  Find the polar coordinates of the point with Cartesian
        coordinates $${\bf r} = \sqrt{2} (1,1).$$

    2.  Find the cylindrical coordinates of the point with Cartesian
        coordinates $${\bf r} = \frac{3}{2} (\sqrt{3}, 1, 1).$$

    3.  Find the spherical coordinates of the points
        $${\bf r} = (3/2, \sqrt{3}/2, 1).$$

2.  [:grinning:] *Geometry and different coordinate systems*

    What geometric objects do the following boundary conditions describe?
   
    1. $r<1$ in cylindrical coordinates,
    2. $\varphi=0$ in cylindrical coordinates,
    3. $r=1$ in spherical coordinates,
    4. $\theta = \pi/4$ in spherical coordinates,
    5. $r=1$ and $\theta=\pi/4$ in spherical coordinates,
    6. $\varphi=\pi/2$ and $\theta=\pi/2$ in spherical coordinates.

3.  [:smirk:] *Partial derivatives*

    (a) Consider the function $f(r,\varphi,\theta)=\frac{1}{r^2}$ defined
        using spherical coordinates.
        Compute $\frac{\partial}{\partial z} f(r, \varphi, \theta)$.

    (b) Now let us consider a function defined using cylindrical coordinates
        as $f(r, \varphi, z) = \frac{1}{r^2}$ (i.e.~very similar to the previous
        question).
        Compute again $\frac{\partial}{\partial z} f(r, \varphi, z)$.
 
4.  [:smirk:] *Chain rule practice* 

    From the transformation from polar to Cartesian
    coordinates, show that
    $$\frac{\partial}{\partial x} = \cos\varphi \frac{\partial}{\partial r} - \frac{\sin\varphi}{r} \frac{\partial}{\partial \varphi}$$
    and
    $$\frac{\partial}{\partial y} = \sin\varphi \frac{\partial}{\partial r} + \frac{\cos\varphi}{r} \frac{\partial}{\partial \varphi}.$$
    (Use the chain rule for differentiation).

5.  [:sweat:] *Laplace operator in spherical coordinates*

    Using the result of problem 4, show that the Laplace
    operator acting on a function $\psi({\bf r})$ in polar coordinates
    takes the form
    $$\nabla^2 \psi({\bf r}) =\left( \frac{\partial^2}{\partial x^2} + \frac{\partial^2}{\partial y^2}\right) \psi({\bf r}) = \frac{1}{r} \frac{\partial}{\partial r} \left( r \frac{\partial \psi(r,\varphi)}{\partial r} \right) + \frac{1}{r^2} \frac{\partial^2 \psi(r,\varphi)}{\partial \varphi^2}.$$

    In a similar fashion it can be shown that for spherical coordinates,
    the Laplace operator acting on a function $\psi({\bf r})$ becomes:
    $$\begin{align} \nabla^2 \psi (r,\varphi, \theta) &= 
    \frac{1}{r^2} \frac{\partial}{\partial r^2} \left( r^2 \frac{\partial \psi(r,\varphi,\theta)}{\partial r} \right) \\ &+ \frac{1}{r^2\sin^2\theta} \frac{\partial^2 \psi(r,\varphi, \theta)}{\partial \varphi^2} \\ &+ \frac{1}{r^2\sin\theta} 
    \frac{\partial}{\partial \theta}\left( \sin\theta \frac{\partial\psi(r,\varphi, \theta)}{\partial \theta}\right).
    \end{align}$$
    This is however even more tedious (you do not have to show this).

6.  [:grinning:] *Integration and coordinates I*

    We define $f(r, \varphi) = \frac{1}{r}$ in polar coordinates. Explain how
    a circular region, centered at the origin and with radius $r_0$, can be described
    using polar coordinates. Then compute the integral of $f(r,\varphi)$ over
    this region.

7.  [:grinning:] *Integration and coordinates II*

    Compute the area of the spherical cap defined by $r=r_0$ and $\theta <\theta_0$. 

8.  [:smirk:] *Integration and coordinates III*

    In 2D, we can define a shape by specifying a function $r(\varphi)$:

    ![image](figures/shape_polar.svg)
    
    (Of course, here we need to have $r(0) = r(2\pi)$.)

    Show that the area of this shape is given by
    $$
    \int_0^{2\pi} \frac{1}{2}\left[r(\varphi)\right]^2 d\varphi
    $$

