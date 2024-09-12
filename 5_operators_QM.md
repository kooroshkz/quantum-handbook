---
title: Operators in quantum mechanics
---

# 5. Operators in quantum mechanics

The lecture on operators in quantum mechanics consists of the following parts:

- [5.1. Definition and properties of operators](#51-definition-properties-operators)

- [5.2. Manipulating operators](#52-manipulating-operators)

- [5.3. Projection operators](#53-projection-operators)

- [5.4. The Hermitian adjoint](#54-the-hermitian-adjoint)

- [5.5. Matrix representation of operators](#55-matrix-representation-of-operators)

and at the end of the lecture notes, there is a set the corresponding exercises:

- [5.6. Problems](#56-problems)

*** 

The contents of this lecture are supplemented with the following **videos**:

- [1. Representation of an operator](https://www.dropbox.com/s/cg9s5hb8dtlkydh/linear_algebra-05.mov?dl=0)

- [2. The action of an operator on kets in matrix representation](https://www.dropbox.com/s/74w7bvwq3o8xiam/linear_algebra-08.mov?dl=0)

**The total length of the videos: ~5 minutes**

***

In the previous lecture, we presented the mathematical language to describe the *quantum states* of a physical system. We saw that the state of a quantum system is described by its *vector state* $|\Psi\rangle$, an element of a special complex vector space called the *Hilbert space*. We presented the Dirac notation and discussed that we can assign a *probabilistic interpretation* to vector states and their inner products. We also discussed their matrix representation and how we can express a state vector in terms of its components in a specific basis.

Now, we need to introduce a concept and a mathematical language required to *extract information* about the physical properties of a system from its state vector, which we will denote by *observables*. We emphasize that this distinction between the *state of a quantum system* (given by the wave function) and the *observables*, which we can extract from it, is the novelty of quantum mechanics with respect to classical physics where this notion is absent. With this motivation, in order to represent fundamental physical quantities of a quantum system that we can measure; such as position, momentum, or energy, we need to introduce a special mathematical entity known as an *operator*.

## 5.1. Definition and properties of operators

Operators in quantum mechanics are mathematical entities  used to represent physical processes that result in the *change* of the state vector of the system, such as the evolution of these states with time. These operators can also represent physical properties of a system that can be experimentally measured (for example position, momentum, or energy), the **observables** associated to this quantum system. Note that each quantum system will have in general a different set of physical observables associated to it.

!!! info "Operators in quantum mechanics"
    An operator is a mathematical object that *acts* on the state vector of the system and produces another state vector. To be precise, if we denote an operator by $\hat{A}$ and $|\psi\rangle$ is an element of the Hilbert space of the system, then
    $$\hat{A} |\psi\rangle = |\phi\rangle \, ,$$
    where the state vector $|\phi\rangle$ *also* belongs to the same Hilbert space.

There are many types of important operators in quantum mechanics. In this lecture, we will present some of these, such as the
**unitary operators** that determine the time evolution of a quantum system and the **Hermitian operators** which can be assigned to
physically observable properties of a system, such as momentum or energy. We will also discuss how we can manipulate operators and combine them in various ways.

!!! info "Linear operators"
    In this course, we are interested in the so-called *linear operators*, which are those operators $\hat{A}$ such that for any arbitrary pair of state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ and for any complex numbers $c_1$ and $c_2$ they satisfy *associative* and *distributive* properties, for instance
    $$\hat{A}[c_1|\psi_1\rangle+c_2|\psi_2\rangle]=c_1\hat{A}|\psi_1\rangle+c_2\hat{A}|\psi_2\rangle \, .$$

Linearity of operators has several important consequences. Recall that in the previous lecture we discussed that any state vector $|\psi\rangle$ can be expressed as a linear combination of a complete set of basis states $\{|\phi_i\rangle,i=1,2,3,...,n\}$ associated to this Hilbert space:
$$|\psi\rangle=\sum_{i=1}^nc_i|\phi_i\rangle \, , \quad  c_i = \langle \phi_i | \psi\rangle \, ,$$
where the values of the coefficients $c_i$ can be fixed thanks to the orthogonality properties of the basis, $\langle \phi_i | \phi_j\rangle=\delta_{ij} $.
Then one can see that for linear operators the following applies 
$$ \hat{A}|\psi\rangle=  \hat{A}\sum_{i=1}^nc_i|\phi_i\rangle =  \sum_{i=1}^nc_i ( \hat{A}|\phi_i\rangle ) \, .$$
This result tells us that if we know the effects of the operator $\hat{A}$ for each of the elements of the basis $|\phi_i\rangle$,
we can easily determine its effect on a *general state vector* $|\psi\rangle$ belonging to the same Hilbert space. 
In other words, the action of the operator $\hat{A}$ on the basis vectors $\{\phi_i\rangle \}$ correlates with its action on any other state vector $|\psi\rangle$ to which the operator was applied. 

Some other important properties of the operators can be stated as follows.
!!! info "Properties of the operators"
    1. If two operators $\hat{A}$ and $\hat{B}$ are such that
        $$\hat{A}|\psi\rangle=\hat{B}|\psi\rangle \, , $$
        for all state vectors $|\psi\rangle$ belonging to the Hilbert
        space of the system, then these two operators must be *identical*:
        $$ \hat{A}=\hat{B} \, .$$
        Note that this is true only if the action of two operators
        is identical for all elements of the Hilbert space.
    2. Like in general vector spaces, in Hilbert spaces, we also have the identity (or unit) and zero (or null) operators defined as
        - The **unit (or identity) operator** $\hat{I}$ is the operator that satisfies
            $$\hat{I}|\psi\rangle=|\psi\rangle $$
        - The **zero (or null) operator** $\hat{0}$ is the operator that satisfies
            $$ \hat{0}|\psi\rangle=0$$
        In both cases, these relations hold for all state vectors $|\psi\rangle$ of the Hilbert space $\mathcal{H}$.
    
## 5.2. Manipulating operators 

We can combine and manipulate operators in various ways. In doing so, we should be careful because manipulations
of operators can be quite different compared with manipulations of scalar complex numbers. 
For example, if you have two complex numbers, the result of their multiplication does not depend on the order in which you multiply them, but for operators it does! As we will show, **in general, operators are non-commutative**, meaning that the order in which they are applied will vary the result of the operation. 

As mentioned above, in these lectures, we will be focusing only on linear operators. For this class of operators, following operations are possible:

!!! info "Addition of operators:" 
    The sum of two operators $\hat{A}$ and $\hat{B}$ is defined by
    $$(\hat{A}+\hat{B})|\psi\rangle=\hat{A}|\psi\rangle+\hat{B}|\psi\rangle \, ,$$
    for all state vectors $|\psi\rangle$. The sum of two operators defines another operator, $\hat{C}$:
    $$ 
    \hat{C}|\psi\rangle=(\hat{A}+\hat{B})|\psi\rangle=\hat{A}|\psi\rangle+\hat{B}|\psi\rangle
    $$
    for all states $|\psi\rangle$, and so we can write
    $$
    \hat{C} = \hat{A} + \hat{B} \, .
    $$
    Note that when we express operator relations, such as this one, we are implicitly stating that they hold when these operators are applied to any of the state vectors $| \Psi \rangle$ of the Hilbert space $\mathcal{H}$.
    
!!! info "Multiplication of an operator by a complex number:"
    If we have an operator that acts on a state vector as
    $$\hat{A}|\psi\rangle=|\phi\rangle \, ,$$
    then we can define the operator $\hat{C}=\lambda \hat{A}$, where $\lambda$ is a complex number as follows
    $$\hat{C} |\psi\rangle= (\lambda \hat{A})|\psi\rangle=\lambda(\hat{A}|\psi\rangle)=\lambda |\phi\rangle \, .$$

!!! info "Multiplication of operators"
    Assume that an operator $\hat{A}$ acting on a ket vector $|\psi\rangle$ maps it into another ket vector $|\phi\rangle$ and that the operator $\hat{B}$  acting on $|\phi\rangle$ results in a third ket vector $|\rho\rangle$:
    $$
    \hat{B} \left( \hat{A}|\psi\rangle \right)=\hat{B}|\phi\rangle=|\rho\rangle \, .
    $$
    One can then define the product of the two operators as a new operator, $\hat{C}=\hat{B}\hat{A}$, such that its action on the initial ket vector $|\psi\rangle$ is defined as
    $$ 
    \hat{C}|\psi\rangle=\left( \hat{B}\hat{A} \right) |\psi\rangle = |\rho\rangle \, .
    $$
    Note that in general, multiplication of two operators is *non-commutative*, so the order in which we multiply $\hat{A}$ and $\hat{B}$ is important, and the operator $\hat{C}=\hat{B}\hat{A}$ will be different from $\hat{D}=\hat{A}\hat{B}$.

!!! info "Commutator of two operators" 
    The difference between a product of operators $\hat{B}\hat{A}$ and the product in the opposite order, namely $\hat{B}\hat{A}$, is defined as the *commutator* of these two operators: 
    $$ [\hat{A},\hat{B}]\equiv \hat{A}\hat{B}-\hat{B}\hat{A} \, . $$
    The commutator plays a fundamental role in the physical interpretation of quantum mechanics. 
    In a nutshell, it tells us whether or not two observable properties of a system can be determined simultaneously with arbitrary precision according to the Heisenberg uncertainty relations. 
    
!!! note "Exercise"
    Using the properties of the addition and multiplication of operators that we just discussed, you can check that the commutator satisfies the following properties:

    1. $[\hat{A},\hat{B}]= -[\hat{B},\hat{A}] $

    2. $[\hat{A},\alpha\hat{B}+\beta\hat{C}]=\alpha[\hat{A},\hat{B}]+\beta[\hat{A},\hat{C}] $

    3. $[\hat{A}\hat{B},\hat{C}]=\hat{A}[\hat{B},\hat{C}] +[\hat{A},\hat{C}] \hat{B}$ 

    4. $[\hat{A},[\hat{B},\hat{C}]]+[\hat{C},[\hat{A},\hat{B}]]+[\hat{B},[\hat{C},\hat{A}]]=0$

## 5.3. Projection operators

!!! info "Projection operator:"
    An operator $\hat{A}$ with the property
    $$ \hat{A}^2= \hat{A}\hat{A}= \hat{A} \, ,$$
    which means that acting twice on a given state vector produces the same result as acting just once, is described as a *projection operator*.
    Let us give an explicit example of such operator. Assume that we have an $n$-dimensional Hilbert space with a basis given by $\{|\phi_i\rangle\}$. We can then define the operator $\hat{B}_i$ as 
    $$\hat{B}_i|\phi_j \rangle \equiv \delta_{ij}|\phi_j \rangle \, .$$ 

Recall that as demonstrated above, once we indicate the behaviour of an operator
for the basis vectors, we automatically know how it will act for any general
state vector of the Hilbert space.

!!! check "Example"
    Let's demonstrate that this operator is a projection operator: 
    $$ \left( \hat{B}_i\right)^2|\phi_j \rangle=\hat{B}_i\hat{B}_i|\phi_j \rangle=\delta_{ij}\hat{B}_i|\phi_j \rangle=\delta_{ij}^2|\phi_j \rangle = \delta_{ij}|\phi_j \rangle = \hat{B}_i|\phi_j \rangle  \, .$$
    From this we can conclude that $\hat{B}_i^2=\hat{B}_i$, as expected for a projection operator, and where we have used that the square of the Kronecker delta is the same Kronecker delta itself.

This projection operator has one important property. Let's act with $\hat{B}_i$ on an arbitrary vector $|\psi\rangle$ expanded in terms of the basis vectors $\{|\phi_j \rangle\}$:
$$
\hat{B}_i|\psi\rangle=\hat{B}_i\sum_{j=1}^n|\phi_j \rangle\langle \phi_j | \psi\rangle=\sum_{j=1}^n\left(\hat{B_i}|\phi_j \rangle\right) \langle \phi_j | \psi \rangle
$$
which implies that
$$
\hat{B}_i |\psi\rangle=\sum_{j=1}^n \delta_{ij}|\phi_j \rangle \langle \phi_ | \psi\rangle=|\phi_i\rangle\langle \phi_i | \psi\rangle \, .
$$
In other words, the operator $ \hat{B}_i$ *projects* the state vector $|\psi\rangle$ onto the direction given by the basis vector $|\phi_i\rangle$. We can clearly see in this case why these operators are called *projection operators*; They allow us to single out specific directions in the Hilbert space of our quantum system.

## 5.4. The Hermitian adjoint

When discussing vector spaces in quantum mechanics, we learned that for each vector state ket $|\Psi\rangle$, there exists the corresponding bra vector $\langle \Psi|$ which can be understood as its complex conjugate. When expressing $|\Psi\rangle$ as a column vector in terms of its components, $\langle \Psi|$ was the associated row
 vector expressing the complex conjugate of its components. A similar discussion is required now in the case of operators.

!!! warning "Warning" 
    For an operator $\hat{A}$ such that $$\hat{A}|\psi\rangle=|\phi\rangle$$ holds true, the already familiar complex conjugation is in general not valid
    $$\langle\psi|\hat{A}\neq \langle\phi |$$ 

!!! info "Hermitian adjoint operator"
    We can introduce another operator related to $\hat{A}$ and written as $\hat{A}^\dagger$ which has the following defining property
    $$\hat{A}|\psi\rangle=|\phi\rangle\; \text{then}\; \langle \psi|\hat{A}^\dagger= \langle \phi|$$
    The operator $\hat{A^\dagger}$ is known as the *Hermitian adjoint* of $\hat{A}$. 
    
    What is then the action of this Hermitian adjoint operator on a ket vector? We can consider the following product
    $$
    \langle\rho|\hat{A}|\psi\rangle=\langle \rho|(\hat{A}|\psi\rangle)=\langle\rho|\phi\rangle
    $$
    using that $\hat{A}|\psi\rangle=|\phi\rangle$. The complex conjugate of the previous expression yields:
    $$
    \langle \rho |\hat{A}|\psi\rangle^*=\langle \rho |\phi\rangle^*=\langle \phi |\rho\rangle
    $$
    and if $\langle\psi|\hat{A^\dagger}= \langle \phi|$, then
    $$
    \langle \rho|\hat{A}|\psi\rangle^*=\langle \phi|\rho\rangle=(\langle \psi |\hat{A^\dagger})|\rho\rangle=\langle \psi |\hat{A^\dagger}|\rho\rangle \, .
    $$

!!! warning ""
    As we will see next, in quantum mechanics, we are interested in operators for which $\hat{A}=\hat{A}^\dagger$, that is where the operator coincides with its Hermitian adjoint.

## 5.5. Matrix representation of operators
 
In the previous lecture, we discussed the matrix representation of state vectors, a notation describing the elements of the Hilbert space assigned to a given quantum system. We will now show how one can also construct a matrix representation of *operators*.

The starting point is an operator equation of the form
$$
\hat{A}|\psi\rangle=|\varphi\rangle \, ,
$$
where $|\psi\rangle$ and $|\varphi\rangle $ are state vectors. This equation can be rewritten using the identity operator given by the basis elements 
$$
\hat{I} = \sum_{i=1}^n |\phi_i\rangle\langle \phi_i| \, ,
$$
and rewritten as
$$
|\varphi\rangle=\hat{A}|\psi\rangle=\hat{A}\sum_{i=1}^n |\phi_i\rangle\langle \phi_i|\psi\rangle=
\sum_{i=1}^n \left( \hat{A}|\phi_i\rangle\right) \langle \phi_i|\psi\rangle
$$

We can now evaluate the inner product between the basis vector $| \phi_j\rangle$
and the state vector $ |\varphi \rangle$ to obtain
$$
\langle {\phi_j}|\varphi\rangle=\sum_{i=1}^n \left(\langle \phi_j| \hat{A}|\phi_i\rangle
\right) \langle \phi_i|\psi\rangle \, ,
$$
which can also be expressed as a matrix multiplication equation in terms of its components using
$$
\varphi_j=\sum_{i=1}^n {A}_{ji}\, \psi_i \, ,
$$
where we define
$$
{A}_{ji} \equiv \langle \phi_j| \hat{A}|\phi_i\rangle \, .
$$

!!! info "Matrix representation of operators"
    The derivation above demonstrates that an operation equation of the form $|\varphi\rangle = \hat{A}|\psi\rangle$ can be expressed in terms of a matrix representation
    $$
    \begin{pmatrix} \varphi_1\\\varphi_2\\\varphi_3 \\\vdots\end{pmatrix} = \begin{pmatrix} A_{11} & A_{12} & A_{13} & \ldots \\ A_{21} & A_{22} & A_{23} & \ldots\\A_{31} & A_{32} & A_{33} & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix} \begin{pmatrix} \psi_1\\\psi_2\\\psi_3 \\\vdots\end{pmatrix}
    $$
    where the operator $\hat{A}$ is represented by a (square) matrix
    $$
    \hat{A} = \begin{pmatrix} A_{11} & A_{12} & A_{13} & \ldots \\ A_{21} & A_{22} & A_{23} & \ldots\\A_{31} & A_{32} & A_{33} & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix} 
    $$

Like in the case of regular vector spaces, when we represent state vectors as operators in terms of components (matrix representation), we are implicitly or explicitly assuming a choice of basis. If we change the basis, the values of the components will change too. 
In other words, while the operator equation $|\varphi\rangle = \hat{A}|\psi\rangle$ is identical in any chosen basis, once we express it as
$$
\begin{pmatrix} \varphi_1\\\varphi_2\\\varphi_3 \\\vdots\end{pmatrix} = \begin{pmatrix} A_{11} & A_{12} & A_{13} & \ldots \\ A_{21} & A_{22} & A_{23} & \ldots\\A_{31} & A_{32} & A_{33} & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix} \begin{pmatrix} \psi_1\\\psi_2\\\psi_3 \\\vdots\end{pmatrix}
$$
then the specific values of  *e.g.* $A_{11}, A_{12}, ...$ will be basis-dependent.

Having demonstrated that we can represent state vectors and operators in term of vectors and matrices, we can now highlight some of the most important *properties of the matrix representation*.

!!! info "Properties of matrix representation of operators"
    1. **Equality**: two operators are said to be equal if their corresponding operator matrix elements are equal, for instance $\hat A = \hat B$ if $A_{ij}=B_{ij}$ for all possible values of $i$ and $j$.

    2. **Identity  operator**: the unit (or identity) operator is represented by $\hat1$ and satisfies $\hat1|\psi\rangle=|\psi\rangle$ for all possible state vectors $|\psi\rangle$. The diagonal elements of the  matrix representation of the identity operator $\hat1$ are all unity while the off-diagonal elements vanish:  $1_{ij}=\delta_{ij}$. This means that for a $n$-dimensional Hilbert space the unit operator is the $n$-dimensional identity matrix. Note that the unit operator has the same form in all representations irrespective of the specific choice of basis states.

    3. **Null operator**: the zero operator $\hat0$ is such as $\hat{0}|\psi\rangle=0$ for all $\psi$. Its matrix elements are all zero, $0_{ij}=0$.

    4. **Addition of operators**: given two operators $\hat{A}$ and $\hat{B}$ with matrix elements $A_{ij}$ and $B_{ij}$, then the matrix elements of their sum $\hat{A}+\hat{B}$ are given by
    $$
    C_{ij}=A_{ij}+B_{ij} \, .
    $$
    
    5. **Multiplication by a complex number**: if $\lambda$ is a complex number, then the matrix elements of the operator $\hat{C}=\lambda \hat{A}$ are given by
    $$
    C_{ij}=\lambda A_{ij} \, .
    $$

    6. **Product of operators**: given two operators $\hat{A}$ and $\hat{B}$ with matrix elements $A_{ij}$ and $B_{ij}$, then the matrix elements of their operator product $\hat{P}=\hat{A}\hat{B}$ are given by
    $$
    P_{ij}=\sum_{k=1}^nA_{ik}B_{kj} \, ,
    $$
    which as you might recall is nothing but the standard rule for matrix multiplication. So once we express operators in their matrix representation, we can multiply them by following standard matrix multiplication. 

    7. **Commutator**: in the same way as matrix multiplication is not commutative, also  operator multiplication is *not commutative*:
    $$
    \hat{A}\hat{B}\;\neq\hat{B}\hat{A}
    $$
    As mentioned above, the difference, $\hat{A}\hat{B}-\hat{B}\hat{A}$ is known as the *commutator* of $\hat{A}$ and $\hat{B}$ and is represented by $[\hat{A},\hat{B}]$. In terms of the matrix representation, the  components of the commutator of $\hat{A}$ and $\hat{B}$
    (which is also a matrix itself) will be given by
    $$
    [\hat{A},\hat{B}]_{ij}= \sum_{k=1}^nA_{ik}B_{kj} - \sum_{k=1}^nB_{ik}A_{kj} =
    \sum_{k=1}^n\left( A_{ik}B_{kj} - B_{ik}A_{kj} \right) \, .
    $$  

### Matrix representation of Hermitian operators

As discussed above, Hermitian operators play a central role in the physical interpretation of quantum systems.
We can now provide the explicit expression of the Hermitian operators in the matrix representation. 

!!! info "Matrix representation of Hermitian operators"
    Let us assume that we have an operator $\hat{A}$ in an $n$-dimensional Hilbert space
    with matrix elements $A_{ij}$ defined with respect to a set of orthonormal basis states, $\{ |\phi_i\rangle; i=1,2,\ldots\,n\}$. 
    From its matrix representation one can construct a new operator by taking the transpose and complex conjugate of the original matrix, that is:
    $$
    \begin{pmatrix} A_{11} & A_{12} & A_{13} & \ldots \\ A_{21} & A_{22} & A_{23} & \ldots\\A_{31} & A_{32} & A_{33} & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix}\rightarrow \begin{pmatrix} A_{11}^* & A_{21}^* & A_{31}^* & \ldots \\ A_{12}^* & A_{22}^* & A_{32}^* & \ldots\\A_{13}^* & A_{23}^* & A_{33}^* & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix}
    $$
    This new matrix corresponds to the matrix representation of a new operator that will be denoted by $\hat{A}^\dagger$.
     
    This new operator is called the **Hermitian adjoint** of the operator $\hat{A}$.

!!! warning "Hermitian operators are equal to their adjoint version"
    At the operator level, we can write that Hermitian operators satisfy $\hat{A}=\hat{A}^\dagger$.
    From the matrix representation giving the expression in terms of its components, the condition for a Hermitian operator will therefore read
    $$
    \begin{pmatrix} A_{11} & A_{12} & A_{13} & \ldots \\ A_{21} & A_{22} & A_{23} & \ldots\\A_{31} & A_{32} & A_{33} & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix} = \begin{pmatrix} A_{11}^* & A_{21}^* & A_{31}^* & \ldots \\ A_{12}^* & A_{22}^* & A_{32}^* & \ldots\\A_{13}^* & A_{23}^* & A_{33}^* & \ldots \\\vdots & \vdots & \vdots & \end{pmatrix} \, ,
    $$
    which can be expressed in a more compact way as
    $$
    A_{ij} = A_{ji}^* \, , \quad i,j=1,\ldots,n \, .
    $$
    Any operator which satisfies this condition will be a Hermitian operator. Note that the Hermiticity of an operator is a property which is independent of the specific choice of basis.

***
## 5.6. Problems

1. [:grinning:] *Commutator algebra*

    Prove that $[\hat{A},\hat{B} \hat{C}]=[\hat{A}, \hat{B}] \hat{C}+\hat{B} [\hat{A}, \hat{C}]$.

2. [:grinning:] *The commutator*
    
    Let 
    $$
    \hat{A}=\begin{pmatrix} -1&2i&0\\0&4&0\\1&0&1\end{pmatrix},~~~~\hat{B}=\begin{pmatrix} 0&2&i\\-i&2i&0\\0&1&4\end{pmatrix}
    $$

    Do $\hat{A}$ and $\hat{B}$ commute?

3. [:grinning:] *Linear operators*

    Suppose that in an orthonormal basis given by $\{|a\rangle, |b\rangle, |c \rangle\}$ an operator $\hat{A}$ acts as follows:
    $$\hat{A}|{a}\rangle=2|{a}\rangle\,,\quad \hat{A}|{b}\rangle=3|{a}\rangle-i|{c}\rangle\, , \quad \hat{A}|{c}\rangle=-|{b}\rangle$$
    Determine the matrix representation of the operator $\hat{A}$.

4. [:grinning:] *Calculating expectation values of operators*

    The expectation value of an operator $\hat{A}$ with respect to a state $|{\Psi}\rangle$ is given by 
    $$<\hat{A}>=\langle{\Psi}|\hat{A}|{\Psi}\rangle \, .$$
    A particle is in a state $|{\Psi}\rangle=2i|{a}\rangle-|{b}\rangle+4i|{c}\rangle$
    and an operator $\hat{A}=|{a}\rangle\langle{a}|-2i|{b}\rangle\langle{b}|+|{c}\rangle\langle{c}|$. 
    
    (The basis is orthonormal).   
    
    Find the expectation value $<\hat{A}>$ in this state.

5. [:smirk:] *The Hermitian conjugate of an operator*

    Consider that the matrix representation of the operator $\hat{A}$ is given by:
    $$\hat{A}=\begin{pmatrix}1&0&-3i\\3&5&0\\3i&0&-2 \end{pmatrix}$$
    and the following two state vectors from the same Hilbert space are given by:
    $$|{\Psi}\rangle=\begin{pmatrix}2\\3i\\-1 \end{pmatrix}\, ,\quad |{\Phi}\rangle=\begin{pmatrix}0\\-1\\1 \end{pmatrix}\, .$$

    **(a)** Find the result of $\hat{A}|{\Psi}\rangle$ and $\hat{A}|{\Phi}\rangle$.

    **(b)** Find the Hermitian conjugates $|{\Psi}\rangle^\dagger$ and $|{\Phi}\rangle^\dagger$, and use these to calculate the inner products between the two state vectors $\langle{\Psi}|{\Phi}\rangle$ and $\langle{\Phi}|{\Psi}\rangle$.

6. [:grinning:] *The Hadamard gate*

    An important operator used in quantum computation is the *Hadamard gate*, which is represented by the matrix:
    $$\hat{H}=\frac{1}{\sqrt{2}}\begin{pmatrix}1&1\\1&-1\end{pmatrix}$$. 

    **(a)** Discuss whether or not $\hat{H}$ is Hermitian or unitary.

    **(b)** Evaluate how the Hadamard gate acts upon the *up* and *down* basis states of the system
    $$|+\rangle=\begin{pmatrix}1 \\ 0  \end{pmatrix}\, ,\quad |-\rangle=\begin{pmatrix}0\\1 \end{pmatrix}\, ,$$
    and discuss the interpretation of these results.

7. [:smirk:] *Spin-$1/2$ system*

    Consider two vectors
    $$|a\rangle=\frac{1}{\sqrt 2} \left( |-\rangle-i|+\rangle \right) $$
    $$|b\rangle=\frac{1}{\sqrt 2} \left(|-\rangle +i|+\rangle \right)$$
    where $|\pm \rangle$ are the basis vectors for a spin-half system, and the operator $\hat{A}$ defined by
    $$\hat{A}|\pm\rangle=\pm \frac{1}{2} i \hbar|\mp\rangle$$

    Note: the basis states are $$|+\rangle=\begin{pmatrix}1 \\ 0  \end{pmatrix}\, ,\quad |-\rangle=\begin{pmatrix}0\\1 \end{pmatrix}\, ,$$

    **(a)** Express the state vectors $|a\rangle$ and $|b\rangle$ as column vectors.

    **(b)** Write down the corresponding bra vectors as row vectors.

    **(c)** Calculate the inner products $\langle a|b\rangle$ and $\langle b|a\rangle$.

    **(d)** Write this operator as a matrix in the $\{|+\rangle,|-\rangle\}$ representation.

    **(e)** Calculate $\hat{A}|a\rangle$ using the matrix representation of $\hat{A}$ and the column representation of $|a\rangle$.

    **(f)** Calculate $\langle b|\hat{A}$ using the matrix representation of $\hat{A}$ and the row representation of $\langle b|$.

  
  
  
