# Summary Math 115A - Week_1

## 1. What is a vector? What is a vector space?
> **a scalar** is any quantity which can be described by a single number.

(Ex: an object has a mass of $m$ kg forsome real number $m$). Other examples of scalar quantities from physics include charge, density, speed, length, time,.etc.

> **a vector** is any member of ***a vector space***; a vector space is any class of objects which can be added together, or multiplied with scalars

**[Definition]** A vector space is any collection $V$ of objects (called vectors) for which two operations can be performed:

* **Vector addition**, which takes two vectors $v$ and $w$ in $V$ and returns another vector $v + w$ in $V$. (Thus $V$ must be closed under addition.)
* **Scalar multiplication**, which takes a scalar $c$ in $\mathbb{R}$ and a vector $v$ in $V$, and returns another vector $cv$ in $V$. (Thus $V$ must be closed under scalar multiplication)

Furthermore, for $V$ to be a vector space, the following properties must be satisfied:

* **(I. Addition is commutative)** For all $v; w \in V , v + w = w + v.$
* **(II. Addition is associative)** For all $u; v; w \in V , u+(v+w) = (u+v)+w.$
* **(III. Additive identity)** There is a vector $0 \in V$ , called the zero vector, such that $0 + v = v$ for all $v \in V$ .
* **(IV. Additive inverse)** For each vector $v \in V$, there is a vector $−v \in V$, called the additive inverse of v, such that $−v + v = 0$.
* **(V. Multiplicative identity)** The scalar $1$ has the property that $1v = v$ for all $v \in V$
* **(VI. Multiplication is associative)** For any scalars $a; b \in \mathbb{R}$ and any vector $v \in V$ , we have $a(bv) = (ab)v$.
* **(VII. Multiplication is linear)** For any scalar $a \in \mathbb{R}$ and any vectors $v; w \in V$ , we have $a(v + w) = av + aw$.
* **(VIII. Multiplication distributes over addition)** For any scalars $a; b \in \mathbb{R}$ and any vector $v \in V$ , we have $(a + b)v = av + bv$.

## 2. Examples of vector spaces
**An $\mathbb{R}^2$ row vector**

![](https://i.imgur.com/FYfGs18.png)

**A 3-dimensional row vector**

![](https://i.imgur.com/WHxTGxc.png)

### Non-vector spaces
* Latitude and longitude.
* Unit vectors.
* The positive real axis.
* Monomials.

### Vector arithmetic
> **Vector cancellation law** If $u; v; w$ are vectors such that $u+v = u+w$, then $v = w$.

**Proof:** Since $u$ is a vector, we have an additive inverse $−u$ such that $−u+u = 0$, by axiom **IV**. Now we add $−u$ to both sides of $u+v = u+w$ 

we have: $−u + (u + v) = −u + (u + w)$

Now use axiom **II**: $(−u + u) + v = (−u + u) + w$

then axiom **IV**: $0 + v = 0 + w$

then axiom **III**: $v = w$

## 3.Vector subspaces
Many vector spaces are subspaces of another. A vector space $W$ is a subspace of a vector space $V$ if $W \subseteq V$, and the laws of vector addition and scalar multiplication are consistent.

**Lemma** Let $V$ be a vector space, and let $W$ be a subset of $V$ . Then $W$ is a subspace of $V$ if and only if the following two properties are satisfied:

* If $w_1$ and $w_2$ are in $W$ , then $w_1 + w_2$ is also in $W$
* If $w$ is in $W$ and $c$ is a scalar, then $cw$ is also in $W$

**Proof** First suppose that $W$ is a subspace of $V$ . Then $W$ will be closed under addition and multiplication directly from the definition of vector space. This proves the "only if" part.

Now we prove the harder "if part". In other words, we assume that $W$ is a subset of $V$ which is closed under addition and scalar multiplication, and we have to prove that $W$ is a vector space. In other words, we have to verify the axioms **I-VIII**.

Most of these axioms follow immediately because $W$ is a subset of $V$, and $V$ already obeys the axioms **I-VIII**. For instance, since vectors $v_1; v_2$ in $V$ obey the commutativity property $v_1+v_2 = v_2+v_1$, it automatically follows that vectors in $W$ also obey the property $w_1 + w_2 = w_2 + w_1$, since all vectors in $W$ are also vectors in $V$ . This reasoning easily gives us axioms **I, II, V, VI, VII, VIII**.

There is a potential problem with **III** though, because the zero vector $0$ of $V$ might not lie in $W$. Similarly with **IV**, there is a potential problem that if $w$ lies in $W$, then $−w$ might not lie in $W$. But both problems cannot occur, because $0 = 0w$ and $−w = (−1)w$, and $W$ is closed under scalar multiplication

---

The intersection of two subspaces is again a subspace. For instance, since the diagonal matrices $D_n(\mathbb{R})$ and the trace zero matrices $M^0_{n×n}(\mathbb{R})$ are both subspaces of $M_{n×n}(\mathbb{R})$, their intersection $D_n(\mathbb{R}) \cap M^0_{n×n}(\mathbb{R})$ is also a subspace of $M_{n×n}(\mathbb{R})$. On the other hand, the union of two subspaces is usually not a subspace. For instance, the $x-axis$ $\{(x; 0) : x \in \mathbb{R}\}$ and $y-axis$ $\{(0; y) : y \in \mathbb{R}\}$, but their union $\{(x; 0) : x \in \mathbb{R}\} \cup \{(0; y) : y \in \mathbb{R}\}$ is not.

## 4.Span, linear dependence, linear independence
### Linear combinations
> **Definition**. Let $S$ be a collection of vectors in a vector space $V$ (either finite or infinite). A ***linear combination*** of $S$ is defined to be any vector in $V$ of the form

$$a_1v_1 + a_2v_2 + \ldots + a_nv_n$$ 

>where $a_1,\ldots,a_n$ are scalars (possibly zero or negative), and $v_1,\ldots,v_n$ are some elements in $S$. The ***span*** of $S$, denoted $span(S)$, is defined to be the space of all linear combinations of $S$:

$$span(S) := \{a_1v_1 + a_2v_2 + \ldots + a_nv_n : a_1,\ldots ,a_n \in \mathbb{R}; v_1, \ldots ,v_n \in S\}$$

Occasionally we will need to deal when $S$ is empty. In this case we set
the span $span(\emptyset)$ of the empty set to just be $\{0\}$, the zero vector space. (Thus 0 is the only vector which is a linear combination of an empty set of vectors. This is part of a larger mathematical convention, which states that any summation over an empty set should be zero, and every product over an empty set should be 1.)

**Theorem** Let $S$ be a subset of a vector space $V$ . Then $span(S)$ is a subspace of $V$ which contains $S$ as a subset. Moreover, any subspace of $V$ which contains $S$ as a subset must in fact contain all of $span(S)$

**Proof** If $S$ is empty then this theorem is trivial (in fact, it is rather vacuous - it says that the space $\{0\}$ contains all the elements of an empty set of vectors, and that any subspace of $V$ which contains the elements of an empty set of vectors, must also contain $\{0\}$), so we shall assume that $n ≥ 1$. We now break up the theorem into its various components.

**(a)** First we check that $span(S)$ is a subspace of $V$. To do this we need to check three things: that $span(S)$ is contained in $V$; that it is closed under addition; and that it is closed under scalar multiplication.

**(a.1)** To check that $span(S)$ is contained in $V$ , we need to take a typical element of the span, say $a_1v_1 + \ldots + a_nv_n$, where $a_1; \ldots ; a_n$ are scalars and $v_1; \ldots ; v_n \in S$, and verify that it is in $V$. But this is clear since $v_1; \ldots ; v_n$ were already in $V$ and $V$ is closed under addition and scalar
multiplication.

**(a.2)** To check that the space $span(S)$ is closed under vector addition, we take two typical elements of this space, say $a_1v_1 + \ldots + a_nv_n$ and $b_1v_1 + \ldots + b_nv_n$, where the $a_j$ and $b_j$ are scalars and $v_j \in S$ for $j = 1; \ldots n$, and verify that their sum is also in $span(S)$. But the sum is

$$(a_1v_1 + \ldots + a_nv_n) + (b_1v_1 + \ldots + b_nv_n)$$

which can be rearranged as

$$(a_1 + b_1)v_1 + \ldots + (a_n + b_n)v_n$$

**(a.3)** To check that the space $span(S)$ is closed under vector addition, we take a typical element of this space, say $a_1v_1+\ldots a_nv_n$, and a typical scalar $c$. We want to verify that the scalar product 

$$c(a_1v_1 + \ldots + a_nv_n)$$

is also in $span(\{v1; \ldots ; v_n\})$. But this can be rearranged as

$$(ca_1)v_1 + \ldots + (ca_n)v_n.$$ 

Since $ca_1; \ldots ; ca_n$ can were scalars, we see that we are in $span(S)$ as desired.

**(b)** Now we check that $span(S)$ contains $S$. It will suffice of course to show that $span(S)$ contains $v$ for each $v \in S$. But each $v$ is clearly a linear combination of elements in $S$, in fact $v = 1.v$ and $v \in S$. Thus $v$ lies in $span(S)$ as desired.

**(c)** Now we check that every subspace of $V$ which contains $S$, also contains $span(S)$. In order to stop from always referring to "that subspace", let us use $W$ to denote a typical subspace of $V$ which contains $S$. Our goal is to show that $W$ contains $span(S)$.

This the same as saying that every element of $span(S)$ lies in $W$. So, let $v = a_1v_1 + \ldots + a_nv_n$ be a typical element of $span(S)$, where the $a_j$ are scalars and $v_j \in S$ for $j = 1; \ldots ; n$. Our goal is to show that $v$ lies in $W$.

Since $v1$ lies in $W$ , and $W$ is closed under scalar multiplication, we see that $a_1v_1$ lies in $W$ . Similarly $a2v2; \ldots ; a_nv_n$ lie in $W$ . But $W$ is closed under vector addition, thus $a_1v_1 +\ldots+a_nv_n$ lies in $W$ , as desired. This concludes the proof of the Theorem.

![](https://i.imgur.com/wQkheu9.png)
![](https://i.imgur.com/6YAroQ7.png)

### Spanning sets
> **Definition** A set $S$ is said to *span* a vector space $V$ if $span(S) = V$;
i.e. every vector in $V$ is generated as a linear combination of elements of $S$. We call $S$ a ***spanning set*** for $V$. (Sometimes one uses the verb "generated" instead of "spanned", thus $V$ is *generated by* $S$ and $S$ is a *generating set* for $V$.)

Spanning sets are useful because they allow one to describe all the vectors in a space $V$ in terms of a much smaller space $S$. 

![](https://i.imgur.com/He8l5zx.png)

### Linear dependence and independence
Consider the following three vectors in $\mathbb{R}^3: v_1 := (1; 2; 3), v_2 := (1; 1; 1), v_3 := (3; 5; 7)$. As we now know, the span $span(\{v_1; v_2; v_3\})$ of this set is just the set of all linear combinations of $v_1, v_2, v_3$:

$$span(\{v_1; v_2; v_3\}) := \{a_1v_1 + a_2v_2 + a_3v_3 : a_1; a_2; a_3 \in R\}:$$

Thus, for instance $3(1; 2; 3) + 4(1; 1; 1) + 1(3; 5; 7) = (10; 15; 20)$ lies in the span. However, the $(3; 5; 7)$ vector is redundant because it can be
written in terms of the other two:

$$v_3 = (3; 5; 7) = 2(1; 2; 3) + (1; 1; 1) = 2v_1 + v_2$$

or more symmetrically

$$2v_1 + v_2 − v_3 = 0$$

Thus any linear combination of $v_1, v_2, v_3$ is in fact just a linear combination of $v_1$ and $v_2$:

$$a_1v_1+a_2v_2+a_3v_3 = a_1v_1+a_2v_2+a_3(2v_1+v_2) = (a_1+2a_3)v_1+(a_2+a_3)v_2$$

Because of this redundancy, we say that the vectors $v_1; v_2; v_3$ are *linearly dependent*. More generally, we say that any collection $S$ of vectors in a vector space $V$ are *linearly dependent* if we can find distinct elements $v_1, \ldots ,v_n \in S$, and scalars $a_1, \ldots ,a_n$ not all equal to zero, such that

$$a_1v_1 + a_2v_2 + \ldots + a_nv_n = 0$$

(Of course, 0 can always be written as a linear combination of $v_1, \ldots ,v_n$ in a trivial way: $0 = 0v_1 + \ldots +0v_n$. Linear dependence means that this is not the only way to write 0 as a linear combination, that there exists at least one non-trivial way to do so). We need the condition that the $v_1, \ldots ,v_n$ are distinct to avoid silly things such as $2v_1 + (−2)v_1 = 0$.

In the case where $S$ is a finite set $S = \{v_1, \ldots ,v_n \}$, then $S$ is linearly dependent if and only if we can find scalars $a_1, \ldots ,a_n$ not all zero such that

$$a_1v_1 + \ldots + a_nv_n = 0$$

If a collection of vectors $S$ is not linearly dependent, then they are said to be **linearly independent**. 

**Theorem.** Let $S$ be a subset of a vector space $V$ . If $S$ is linearly dependent, then there exists an element $v$ of $S$ such that the smaller set $S − \{v\}$ has the same span as $S$:

$$span(S − \{v\}) = span(S)$$

Conversely, if $S$ is linearly independent, then every proper subset $S^{'} \subsetneq S$ of $S$ will span a strictly smaller set than $S$:

$$span(S^{'}) \subsetneq span(S)$$

Since $S$ is linearly dependent, then by definition there exists distinct $v_1; \ldots ;v_n$ and scalars $a_1; \ldots ;a_n$, not all zero, such that

$$a_1v_1 + \ldots + a_nv_n = 0$$

We know that at least one of the $a_j$ are non-zero; without loss of generality we may assume that $a_1$ is non-zero (since otherwise we can just shuffle the $v_j$ to bring the non-zero coefficient out to the front). We can then solve for $v_1$ by dividing by $a_1$:

$$v_1 = −\frac{a_2}{a_1}v_2 − \ldots − \frac{a_n}{a_1}v_n$$

Thus any expression involving $v_1$ can instead be written to involve $v_2; \ldots ; v_n$ instead. Thus any linear combination of $v_1$ and other vectors in $S$ not equal to $v_1$ can be rewritten instead as a linear combination of $v_2; \ldots ; vn$ and other vectors in $S$ not equal to $v_1$. Thus every linear combination of vectors in $S$ can in fact be written as a linear combination of vectors in $S − \{v_1\}$. On the other hand, every linear combination of $S − \{v_1\}$ is trivially also a linear combination of $S$. Thus we have
$span(S) = span(S − \{v_1\})$ as desired.

![](https://i.imgur.com/f38nBdb.png)


## 5.Systems of linear equations
How can we tell when one given vector $v$ is in the span of some other vectors $v_1; v_2; \ldots v_n$? For instance, is the vector $(0; 1; 2)$ in the span of $(1; 1; 1), (3; 2; 1), (1; 0; 1)?$ This is the same as asking for scalars $a_1, a_2, a_3$ such that

$$(0; 1; 2) = a_1(1; 1; 1) + a_2(3; 2; 1) + a_3(1; 0; 1)$$

We can multiply out the left-hand side as

$$(a_1 + 3a_2 + a_3; a_1 + 2a_2; a_1 + a_2 + a_3)$$

and so we are asking to find $a_1, a_2, a_3$ that solve the equations

$a_1 +3a_2 +a_3 = 0$

$a_1 +2a_2 = 1$

$a_1 +a_2 a_3 = 2$

This is a **linear system of equations**; **"system"** because it consists of more than one equation, and **"linear"** because the variables $a_1, a_2, a_3$ only appear as linear factors (as opposed to quadratic factors such as $a_1^2$ or $a_2a_3$, or more non-linear factors such as $sin(a1)$).

## 6.Bases
A ***basis*** of a vector space $V$ is a set $S$ which spans $V$ , while also being linearly independent. In other words, a basis consists of a bare minimum number of vectors needed to span all of $V$ ; remove one of them, and you fail to span $V$

**Lemma.** Let $\{v_1; v_2, \ldots ,v_n\}$ be a basis for a vector space $V$ . Then
every vector in $v$ can be written uniquely in the form

$$v = a_1v_1 + \ldots + a_nv_n$$

for some scalars $a_1, \ldots ,a_n.$

**Proof.** Because $\{v_1; \ldots ; v_n\}$ is a basis, it must span $V$ , and so every vector $v$ in $V$ can be written in the form $a_1v_1+ \ldots +a_nv_n$. It only remains to show why this representation is unique. Suppose for contradiction that a vector $v$ had two different representations

$$v = a_1v_1 + \ldots + a_nv_n$$

$$v = b_1v_1 + \ldots + b_nv_n$$

where $a_1; \ldots ; a_n$ are one set of scalars, and $b_1; \ldots ; b_n$ are a different set of scalars. Subtracting the two equations we get 

$$(a_1 − b_1)v_1 + \ldots + (a_n − b_n)v_n = 0$$

But the $v_1; \ldots ; v_n$ are linearly independent, since they are a basis. Thus the only representation of 0 as a linear combination of $v_1; \ldots ; v_n$ is the trivial representation, which means that the scalars $a_1 − b_1; \ldots ; a_n − b_n$ must be equal. That means that the two representations $a_1v_1 + \ldots + a_nv_n , b_1v_1 + \ldots + b_nv_n$ must in fact be the same representation. Thus $v$ cannot have two distinct representations, and so we have a unique representation as desired. 

---

The standard basis of $R^n$ is $\{e_1; e_2; \ldots ; e_n\}$, where $e_j$ is the vector whose $j^{th}$ entry is 1 and all the others are 0. Thus for instance, the standard basis of $\mathbb{R}^3$ consists of $e_1 := (1; 0; 0), e_2 := (0; 1; 0),$ and $e_2 := (0; 0; 1).$

The standard basis of the space $P_n(\mathbb{R})$ is $\{1; x; x^2; \ldots ; x^n\}$. The standard basis of $P(\mathbb{R})$ is the infinite set $\{1; x; x^2; \ldots \}$

## Resources
* [https://colab.research.google.com/drive/1vpf1y-n4XtH-dGdCU8Ga7_7jgCeCt_OV?usp=sharing](https://colab.research.google.com/drive/1vpf1y-n4XtH-dGdCU8Ga7_7jgCeCt_OV?usp=sharing){:target="_blank"}

