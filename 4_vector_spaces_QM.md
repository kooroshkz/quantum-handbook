---
title: Vector spaces in quantum mechanics
---

# 4. Vector spaces in quantum mechanics

The lecture on vector spaces in quantum mechanics consists of the following parts:

- [4.1. Dirac notation and Hilbert spaces](#41-dirac-notation-and-hilbert-spaces)

- [4.2. Inner product of state vectors](#42-inner-product-of-state-vectors)

- [4.3. Matrix representation of ket and bra vectors](#43-matrix-representation-ket-and-bra-vectors)

- [4.4. A two-dimensional Hilbert space](#44-a-two-dimensional-hilbert-space)

and at the end of the lecture there is a set of exercises 

- [4.5. Problems](#45-problems)

---

The contents of this lecture are summarised in the following **videos**:

- [1. Dirac notation and properties of Hilbert spaces](https://www.dropbox.com/s/mnccmpff33pre9r/linear_algebra_04.mov?dl=0)

- [2. Algebra with Dirac notation - bras and kets](https://www.dropbox.com/s/709bh9j083y7d0s/linear_algebra-06.mov?dl=0)

- [3. Finding expansion coefficients for Dirac notation](https://www.dropbox.com/s/k9plspkonnk3nc0/linear_algebra-07.mov?dl=0)

**Total length of the videos: ~14 minutes**

---

## 4.1. Dirac notation and Hilbert spaces

In the previous lecture, we reviewed the basic properties of linear vector spaces. Next, we will discuss how the same formalism
can be applied to describe physical states in quantum mechanics.

The state of a physical system in quantum mechanics is represented by a vector belonging to a *complex vector space*.
This vector space is known as the *state space* of the system.

### Ket

!!! info "Ket"
     A physical state of a quantum system is represented by a symbol $$|~~\rangle$$ known as a **ket**. 
     This notation is known as the *Dirac notation*, and it is very prominent in the description of quantum mechanics. 
     Note that a *ket* is also referred to as a state vector, *ket* vector, or just a state. 

### Hilbert space

The set of all possible state vectors describing a given physical system forms a complex vector space $\mathcal{H}$, which is known as the *Hilbert space* of the system. You can think of the Hilbert space as the space populated by all possible states that a quantum system can be found on. Hilbert spaces inherit a number of the important properties of general vector spaces:
    
!!! info "Superposition" 
     A linear combination (or superposition) of two or more state vectors $|{\psi_1}\rangle, |{\psi_2}\rangle, |{\psi_3}\rangle,... |{\psi_n}\rangle$, is also a state of the quantum system. Therefore, a linear combination $|{\Psi}\rangle$ of the form $$|{\Psi}\rangle=c_1|{\psi_1}\rangle+c_2|{\psi_1}\rangle+c_3|{\psi_3}\rangle+...+c_n|{\psi_n}\rangle = \sum_{i=1}^n c_i|{\psi_i}\rangle$$ 
     where $c_1, c_2, c_3, ...$ are general complex numbers will also be a physically allowed state vector of the quantum system.
     
!!! info "Normalisation"
     If a physical state of the system is given by a vector $|{\Psi}\rangle$, then the same physical state can also be represented by the vector $c|{\Psi}\rangle$ where $c$ is a non-zero complex number. The reason for this is that the overall normalisation of the state vector *does not change the physics* of the system (or in other words, does not modify the *information content* of the state vector). As we will discuss below, in quantum mechanics it is advantageous to work with  *normalised vectors*, that is, whose *length* is one. 
     We will define in a while what do we mean by length.

!!! info "Completeness"
     A set of vectors $|{\psi_1}\rangle, |{\psi_2}\rangle, |{\psi_3}\rangle,... |{\psi_n}\rangle$ is said to be  *complete* if every state 
     of the quantum system can be represented as a linear combination of them.
     In such a case, it becomes possible to express  *any* state vector $|{\Psi}\rangle$ of the system's Hilbert space as a superposition of these $n$ vectors,
     $$ |{\Psi}\rangle=\sum_{i=1}^n c_i|{\psi_i}\rangle$$
     for some specific choice of coefficients $c_i$. The set of vector \{$|{\psi_i}\rangle$\} are then said to *span* the Hilbert space of the quantum system.
    
!!! info "Basis"
     A set of vectors \{$|{\psi_i}\rangle$\} is said to form a basis for the state space if the set of vectors is *complete* and if in addition they are  *linearly independent*. The latter condition means essentially that one cannot express a given basis vector as a linear combination of the rest of basis vectors.
     Linear independence can also be expressed as the requirement that if one has that
     $$\sum_{i=1}^n c_i |{\psi_i}\rangle=0\;\text{then}\; c_i=0\;\text{for all}\; i$$

!!! info "Dimensionality"
     The minimum number of vectors needed to form a complete set of basis states is known as the *dimensionality* of the state space. In quantum mechanics you will encounter systems whose Hilbert spaces have very different dimensionality, from the spin-1/2 particle (a $n=2$ vector space) to the free particle (whose state vectors live in an infinite vector space).

### Bra vectors

We need now to extend the Dirac notation to describe other elements of this vector space. We need to introduce a quantity $\langle{\Psi}|$, known as a  *bra vector*, which represents the  *complex conjugates* of the corresponding ket vector. Bra vectors are elements of the vector space $\mathcal{H}^{*}$, called the *dual space* of the original Hilbert space $\mathcal{H}$.

!!! info "Bra vector"
     If a ket vector is given by $$| \Psi\rangle= c_1 |\psi_1\rangle+c_2|\psi_2\rangle \, ,$$ 
     then the corresponding bra vector will be given by 
     $$\langle{\Psi}|= c_1^*\langle{\psi_1}|+c_2^*\langle{\psi_2}| \, .$$

As mentioned above, the vector space spanned by all bra vectors $\langle{\Psi}|$ is referred to as the dual space and is represented by $\mathcal{H}^*$. For each ket vector belonging to $\mathcal{H}$, there will exist an associated bra vector belonging to the dual space $\mathcal{H}^*$.

Below, we will further discuss the concept of bra vectors when presenting the matrix representation of elements of the Hilbert space.
      
## 4.2. Inner product of state vectors

Assume that $|{\psi}\rangle$ and $|{\phi}\rangle$ are any two state vectors belonging to the
state (Hilbert) space $\mathcal{H}$, then we can define the  *inner product*
between them, $\langle{\psi}|{\phi}\rangle$, as follows. 

The inner product in quantum mechanics is the analog of the usual scalar product that one encounters in vector spaces, and which we reviewed in the previous lecture. As in usual vector spaces, the inner product of two state vectors is a  *scalar* and in this case a complex number in general. 

!!! tip "Interpretation of the inner product in quantum mechanics"
     1.   The value of the inner product $\langle{\psi}|{\phi}\rangle$ indicates the **probability amplitude** (not the probability) of measuring a system, which characterised by the state $|{\phi}\rangle$, to be in the state $|{\psi}\rangle$. 
     2.   This inner product can also be understood as measuring the **overlap** between the state vectors $|{\psi}\rangle$ and $|{\phi}\rangle$. 
     3.   Then the  **probability of observing the system to be in the state $|\psi\rangle$** given that it is in the state $|\phi\rangle$ will be given by $$|\langle \psi | \phi \rangle|^2 \, .$$ Since the latter quantity is a probability, we know that it should satisfy the condition that 
     $$0 \le |\langle \psi | \phi \rangle|^2 \le 1 \, .$$

### Properties of the inner product

The inner product (probability amplitude) $\langle \psi | \phi \rangle$ exhibits the following properties:
      
!!! info "Properties of the inner product"
     1. **Complex conjugate:** $\langle \psi | \phi \rangle=\langle \phi | \psi \rangle^*$
     2. **Distributivity and associativity:** $\langle \psi |\{c_1 |\phi_1\rangle+c_2 |\phi_2 \rangle\}=c_1\langle \psi | \phi_1\rangle+c_2\langle \psi | \phi_2\rangle$
     3. **Positivity:** $\langle \psi | \psi \rangle\geq0 \, .$
          If $\langle \psi | \psi \rangle = 0$ then, this implies that the state vector $|\psi\rangle=0$ is the null element of the Hilbert space.
     4. **Orthogonality:** Two states $|\psi \rangle$ and $|\phi \rangle$ are said to be *orthogonal* if $\langle \psi | \phi\rangle=0 \, .$
          By analogy with regular vector spaces, we can think of these two state vectors $|\psi \rangle$ and $|\phi \rangle$ as being *perpendicular* to each other. Note that for a quantum system occupying a certain state, there is a vanishing probability of it being observed in a state orthogonal to it.
     5. **Norm:** The quantity $\sqrt{\langle \psi | \psi \rangle}$ is known as the  *length* or the *norm* of the state vector $|\psi\rangle$. 
          You can see from the properties of complex algebra that this length must be a real number. A physically valid state $|\psi \rangle$ must be normalized to unity, that is $\langle \psi | \psi \rangle=1$. Note that a state that cannot be normalized to unity does not represent a physically acceptable state.
     6. **Orthonormality:** A set of orthonormal basis vectors $\{|\psi_i\rangle\text{;}\; i=1,2,3,...,n\}$ will have the property $\langle \psi_i |\psi_j \rangle=\delta_{ij}$ where $\delta_{ij}$ is a mathematical symbol known as the *Kronecker delta*, which equals unity if $i=j$ and zero if $i\neq j$.
   
From all the above conditions, we see that a Hilbert space is a so-called *complex inner product space*, which is nothing else but a complex vector space equipped with a inner product. All the vectors belonging to a Hilbert space $\mathcal{H}$ have a finite norm, which means that they can be normalized to unity. This normalisation condition is essential is we are to apply the probabilistic interpretation of the state vectors described above.

## 4.3. Matrix representation of ket and bra vectors
 
As we have discussed, in quantum mechanics a general state vector $|\psi\rangle$ can be represented in terms of the basis vectors, $\{|\phi_i\rangle;i=1,2,...,n\}$, as 
$$ |\psi\rangle=\sum_{i=1}^n c_i |\phi_i\rangle $$
for some values of the complex coefficients $\{ c_i\}$. To determine the values of these coefficients, we can take the inner product between the bra basis vector $\langle \phi_j|$ and the ket state vector $|\psi\rangle$ and use the orthogonality properties of the basis vectors:
$$ \langle \phi_j|\psi\rangle = \langle \phi_j|\sum_{i=1}^n c_i |\phi_i\rangle = \sum_{i=1}^n c_i\langle \phi_j|\phi_i\rangle = \sum_{i=1}^n c_i\delta_{ij} = c_j \, .$$
Therefore, if we now denote the coefficients $\{ c_i\}$ of the state vector $|\psi\rangle$ by $\{ \psi_i\}$, we have the expansion
$$ |\psi\rangle=\sum_{i=1}^n c_i |\phi_i\rangle= \sum_{i=1}^n \left( \langle \phi_i|\psi\rangle \right) |\phi_i\rangle \, .$$
By analogy with the Euclidean case, we can understand the coefficients $\psi_i$ as the *components* of the state vector $ |\psi\rangle$ along the $n$ directions spanned by the basis vectors. Here, note also that in this notation $\psi_i$ is an *scalar* (just a number) and not a vector. Furthermore, note that, as opposed to the Euclidean space, the coefficients $\psi_i$ will generally be complex numbers.

This analogy with the case of ordinary vectors allows us to write the state $|\psi\rangle$ as a *column vector* with respect to the set of basis vectors $\{|\phi_i\rangle;i=1,2,...,n\}$, which are kept implicit: 
$$ |\psi\rangle= \begin{pmatrix} \psi_1\\\psi_2\\\psi_3\\\vdots\\\psi_n\end{pmatrix} \, . $$

We can also express the basis vectors in this manner. Given that the basis vectors are *orthonormal* among themselves,
the basis state $|\phi_i\rangle$ will have as component in the $j$ direction
$$ (\phi_i)_j=\langle \phi_j|\phi_i\rangle=\delta_{ji} \, ,$$ 
and thus the vector column expression of the basis vectors will be very simple
$$ |\phi_1\rangle= \begin{pmatrix} 1\\0\\0 \\\vdots\end{pmatrix} \;, \quad |\phi_2\rangle= \begin{pmatrix} 0\\1\\0 \\\vdots\end{pmatrix} \;, \ldots $$

!!! note "Evaluating the inner product"
     Let us show how we can use the matrix representation to evaluate the inner product (bracket) between two state vectors when expanded in terms of their components in the same basis:
     $$ |\psi\rangle=\sum_{i=1}^n \psi_i |\phi_i\rangle \,, \qquad |\chi\rangle=\sum_{i=1}^n \chi_i |\phi_i\rangle\, .$$
     First of all, we note that we can write the above expansions in the following way
     $$
     |\psi\rangle=\sum_{i=1}^n |\phi_i \rangle \langle \phi_i | \psi \rangle \, ,
     $$
     and thus we see that the basis vectors provide a very useful representation of the *identity operator*:
     $$
     \hat{I} = \sum_i |\phi_i\rangle \langle\phi_i| \, ,
     $$
     We can insert this  identify operator within the bracket to evaluate the inner
     product $\langle \chi|\psi\rangle$ between the two state vectors to evaluate the inner product $\langle \chi|\psi\rangle$:
     $$
     \langle \chi|\psi\rangle=
     \langle\chi|\hat{I} |\psi\rangle=\sum_{i=1}^n \langle\chi| \phi_i \rangle \langle\phi_i|\psi\rangle \, .
     $$
     Next, using that $\chi_i = \langle \phi_i|\chi \rangle$ are the components of the
     state vector $|\chi\rangle$ and that  $\langle \chi| \phi_n \rangle=(\langle\phi_i|\chi\rangle)^*$,
     we have that $\langle \chi |\phi_i\rangle =\chi_i^*$
     and therefore the inner product of the two state vectors $|\psi\rangle$
     and  $|\chi\rangle$ can be expressed in terms of their components
     as follows
     $$\langle\chi|\psi\rangle=\sum_{i=1}^n\chi_i^*\psi_i.$$
     which in the matrix representation of state vectors can also be written as
     $$\langle \chi|\psi\rangle=\begin{pmatrix} \chi^*_1 , \chi^*_2 &,\ldots \end{pmatrix}\begin{pmatrix} \psi_1 \\ \psi_2 \\ \vdots \end{pmatrix} \, .$$ Therefore, we can present  bra vector $\langle \chi|$ as row vectors and ket vectors as column vector. 
     The row vector can thus be treated as the *complex conjugate* of the corresponding column vector.

## 4.4. A two-dimensional Hilbert space

As a practical example to illustrate the basic ideas of vector spaces applied to quantum physics presented above, we will consider a quantum system which is fundamental for quantum mechanics and its applications. This system corresponds to the possible states that the intrinsic angular momentum of an electron, known as *spin*, can occupy. As you will see in following courses, the Hilbert space for the electron spin has dimension $n=2$, meaning that we can find an electron spin *pointing* either in the up direction, denoted by $|+\rangle$, or the down direction, denoted by $|-\rangle$.

The general state vector of this system will be expressed as a linear superposition of the *up* and *down* states,
$$
|\Psi\rangle = c_+ | + \rangle + c_- | - \rangle \, , \quad c_+ = \langle +|\Psi \rangle
\, , \quad c_- = \langle -|\Psi \rangle \, .
$$  
In terms of the matrix representation, if we take $| + \rangle$
and  $| - \rangle$ as the *basis* for this vector space, we can express $|\Psi\rangle$
as a column vector
$$
|\Psi\rangle = \left( \begin{array}{c} c_+ \\ c_- \end{array}\right) \, ,
$$
and similarly for the basis vectors
$$
| + \rangle = \left( \begin{array}{c} 1 \\ 0 \end{array}\right) \, ,\quad
| - \rangle = \left( \begin{array}{c} 0 \\ 1 \end{array}\right) \, .
$$

We can likewise express the inner product between  $ |\Psi\rangle$ and some other state vector
$$
|\Psi'\rangle = c_+' | + \rangle + c_-' | - \rangle \, , \quad c_+ '= \langle +|\Psi' \rangle
\, , \quad c_-' = \langle -|\Psi' \rangle \, . $$
as a multiplication of a row vector and a column vector,
$$
\langle \Psi'|\Psi\rangle = \left(  (c'_+)^{*} , (c'_-)^{*} \right)\left( \begin{array}{c} c_+ \\ c_- \end{array}\right) =  (c'_+)^{*}c_+  + (c'_-)^{*} c_- \, .
$$ 
Note that one needs to take the complex conjugate of the components when expressing a state vector as a bra vector.

Examples of elements of this Hilbert space are the following:
$$
\left( \begin{array}{c}3 \\ -2i \end{array} \right) \, ,\quad
\left( \begin{array}{c}i \\ -4 \end{array} \right) \, ,\quad
\left( \begin{array}{c}2 \\ 5 \end{array} \right) \, .
$$
The values of the coefficients $c_+$ and $c_-$ for these examples above are, respectively,
$$
(c_+,c_-) = (3,-2i) \, ,\qquad
(c_+,c_-) = (i,-4) \, ,\qquad
(c_+,c_-) = (2,5) \, .\qquad 
$$
!!! warning ""
     Note however that many other bases are possible, and that the physics of a quantum system do not depend on the basis that we choose.

The bra vectors associated to these ket vectors will be given by
$$ |{\Psi}\rangle=   \left( \begin{array}{c}3 \\ -2i \end{array} \right) \, , \qquad
\langle{\Psi}|=\left( 3, 2i \right) \, ,$$
$$ |{\Psi}\rangle = \left( \begin{array}{c}i \\ -4 \end{array} \right) \, , \qquad
\langle{\Psi}|=\left(  -i , -4  \right)\, , $$
$$|{\Psi}\rangle=  \left( \begin{array}{c}2 \\ 5 \end{array} \right) \, , \qquad
\langle{\Psi}|=  \left( 2 , 5  \right) \, .$$
Note however that the above vectors are not normalised (the inner product with themselves is different from unity), and thus
cannot represent physical states. We show below an explicit example of a normalised state vector belonging to this Hilbert space.

!!! done "Example: Evaluating the inner product"
     We also know how we can evaluate the inner product between any two state vectors belonging to this Hilbert space. If we have two state vectors given by
     $$
     |\psi\rangle = \frac{1}{\sqrt{2}} \left( \begin{array}{c}1 \\ -i \end{array} \right) \, \quad
     |\phi \rangle = \left( \begin{array}{c}0 \\1 \end{array} \right)
     $$
     then their inner product is
     $$
     \langle \psi | \phi \rangle =
     \frac{1}{\sqrt{2}} \left( 1 , i  \right) \left( \begin{array}{c}0 \\1 \end{array} \right) =
     \frac{i}{\sqrt{2}} 
     $$
     and the associated probability will be given by
     $$
     |\langle \psi|\phi\rangle|^2 = \frac{1}{2}
     $$
     meaning that if I measure the state $| \phi \rangle $, I will have a 50% probability
     of finding it in the state $| \psi \rangle$. Recall that probabilities must always be smaller than 1 to make physical sense. Note also that I am using normalised vectors, you can check yourselves that
     $$
     \langle \psi |\psi \rangle =  \langle \phi | \phi\rangle = 1 \, ,
     $$
     as required to ensure the probabilistic description of the state vector.

## 4.5. Problems

**1)** [:grinning:] *The inner product*

Two vectors in a three-dimensional complex vector space are defined by:
$$
|A\rangle =\begin{pmatrix}2\\-7i\\1\end{pmatrix},~~|B\rangle=\begin{pmatrix}1+3i\\4\\8\end{pmatrix}
$$
Let $a=6+5i$ and answer the following questions:

*(a)*. Calculate $a|A\rangle$, $a |B\rangle$, and $a( |A\rangle+|B\rangle)$. Show that $a(|A\rangle+|B\rangle)=a|A\rangle+a|B\rangle$.

*(b)*. Find the inner products $\langle A | B\rangle$ and $\langle B | A\rangle $. What is the relationship between them?

*(c)* Find the norm of each vector.

***
  
**2)**  [:grinning:] *A normalised vector*

*(a)* Show that the two state vectors 
$$
|\Psi\rangle=\begin{pmatrix} 1/\sqrt{2}\\ 1/\sqrt{2}\end{pmatrix},~~|\Phi\rangle=\begin{pmatrix} 1/\sqrt{2}\\ -1/\sqrt{2}\end{pmatrix}
$$
are orthogonal to each other. Is the state vector $ |\Psi \rangle$ normalised?

*(b)* Assume a vector
$$
|u \rangle =\begin{pmatrix} x\\ 3x\\-2x\end{pmatrix}
$$
where $x$ represents an unknown real number. Find the value of $x$ such that the state vector $|u\rangle$ is normalised.

***
    
**3)** [:sweat:]  The *Cauchy-Schwartz inequality* states that
$$
\mid{\langle \Phi|\Psi\rangle}\mid^2 \leq \langle\Psi|\Psi\rangle \langle \Phi | \Phi\rangle
$$
Demonstrate this result using the properties of the inner product that we have covered in this lecture.

***

**4)** [:grinning:] *Basis vectors*

*(a)* Show that the following vectors are linearly dependent:

$$
|a\rangle=\begin{pmatrix} 1\\ 2\\1\end{pmatrix},~~|b\rangle=\begin{pmatrix} 0\\ 1\\0\end{pmatrix},~~|c\rangle=\begin{pmatrix} -1\\ 0\\-1\end{pmatrix}
$$

*(b)* Is the following set of vectors linearly independent?

$$
|a\rangle=\begin{pmatrix} 2\\ 0\\0\end{pmatrix},~~|b\rangle=\begin{pmatrix} 0\\ -1\\0\end{pmatrix},~~|c\rangle=\begin{pmatrix} 0\\ 0\\-1\end{pmatrix}
$$

***

**5)** [:grinning:] *Dirac algebra with bras and kets*

Suppose that $|a\rangle $, $|b\rangle$, $|c\rangle$ is an orthonormal basis. In this basis let us define the following two state vectors:
$$
|\Psi\rangle=2i |a\rangle-3|b\rangle+i|c\rangle
$$
$$
|\Phi\rangle=3|a\rangle-2|b\rangle+4|c\rangle
$$

*(a)* Find $\langle \Psi|$ and $\langle \Phi|$.

*(b)* Compute the inner product $\langle \Phi | \Psi \rangle$.

*(c)* Show that $\langle \Phi | \Psi\rangle=\langle \Psi|\Phi\rangle^*$.

*(d)* Write the column vector representing the vector $|\Psi\rangle$ in the given basis. Then write down the row vector that represents $\langle \Psi|$ in the given basis as well.

***

**6)** [:sweat:] *The state vector for a spin half particle*

The state vector for a spin half particle that passes through a magnetic field oriented in the direction $\hat{n}$ and exists with its spin component in the direction of the magnetic field, i.e. $S=\vec{S}\cdot\hat{n}=\frac{1}{2}\hbar$ is given by
$$
|S\rangle =\cos(\theta/2) |+\rangle +\sin(\theta/2) \, e^{i\phi} |-\rangle
$$
where $\hat{n}=\sin\theta \,\cos\phi \, \hat{i} +\sin\theta \, \sin\phi \,\hat{j}+\cos\theta \, \hat{k}$. 

*(a)* What is the corresponding bra vector?

*(b)* Show that this state is normalized to unity.

*(c)* Identify the state $|S\rangle $ if $\hat{n}=\hat{i}, \hat{j},$ and $\hat{k}$.

*(d)* Express $|S\rangle $ in terms of the basis states $|-\rangle ,\,|+\rangle $ in each case.

***

**7)** [:sweat:] *A particle in an infinite well*

A particle of mass $m$ confined to move in an infinite well of width $L$ can have the energies $E_n=\pi^2\hbar^2n^2/2mL^2$ where $n=1,2,...$ We can specify the states of the particle in the well by the kets $| 1\rangle $, $|2\rangle $, $|3\rangle $, ... where $|n\rangle $ is the ket corresponding to the particle having the energy $E_n$. These states form a complete orthonormal set of basis states for the particle in the well.

*(a)* What is the dimension of the state space for the particle?

*(b)* State the orthonormality conditions for the kets $\{| 1\rangle,|2\rangle,|3\rangle,...\}$

*(c)* A particle is prepared in the state
$$
|\psi\rangle=\frac{1}{3}|1\rangle+\frac{1}{3}(2+i)|2\rangle+\alpha|3\rangle.
$$
This state is normalized to unity. If the experiment is repeated 500 times under identical conditions, and the energy of the particle in the well is measured, roughly how many times will the particle be observed to have the energy $E_3$?
  

