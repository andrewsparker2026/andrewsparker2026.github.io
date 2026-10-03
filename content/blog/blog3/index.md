---
title: "What is Kummer Theory"
Date: 2026-09-10
weight: 100
draft: false
showAuthor: true
mathjax: true
showComments: true
---
{{< katex >}}

A down to earth introduction to Kummer theory :

The purpose of this note is to understand a very classical question: **Can we describe cyclic extensions of a field explicitly by adjoining roots?** For quadratic extensions this is familiar: if \(\operatorname{char}(F)\neq2\), then a quadratic extension has the form \(F(\sqrt a)\). Kummer theory explains the higher-degree analogue, why roots of unity enter the picture, and how the whole story can be expressed naturally using Galois cohomology.

Before getting there, let us begin with a small fact about tensor products and composita of fields.

## 1. A warm-up: when is \(L\otimes_F K\) a field?

Let \(L/F\) and \(K/F\) be field extensions contained in some common overfield \(\Omega\). Their compositum \(LK\) is the smallest subfield of \(\Omega\) containing both \(L\) and \(K\). There is a natural \(F\)-algebra homomorphism
\[
\mu:L\otimes_F K\longrightarrow LK,\qquad x\otimes y\longmapsto xy.
\]
Thus, more generally,
\[
\mu\left(\sum_i x_i\otimes y_i\right)=\sum_i x_i y_i.
\]
The map \(\mu\) is injective precisely when \(L\) and \(K\) are **linearly disjoint over \(F\)**. Equivalently,
\[
L\text{ and }K\text{ are linearly disjoint over }F\iff \mu:L\otimes_FK\longrightarrow LK\text{ is injective}.
\]

Suppose now that both \(L/F\) and \(K/F\) are algebraic and linearly disjoint. We claim that
\[
L\otimes_FK\simeq LK.
\]
Indeed, identify \(L\otimes_FK\) with its image \(R\subseteq LK\). An element of \(R\) has the form
\[
z=\sum_i x_i y_i,\qquad x_i\in L,\ y_i\in K.
\]
Since \(L/F\) and \(K/F\) are algebraic, \(z\) is algebraic over \(F\). Take \(0\neq z\in R\), and let
\[
z^m+a_{m-1}z^{m-1}+\cdots+a_1z+a_0=0
\]
be its minimal polynomial over \(F\). Since \(z\neq0\), we have \(a_0\neq0\), and hence
\[
z^{-1}=-\frac1{a_0}\left(z^{m-1}+a_{m-1}z^{m-2}+\cdots+a_1\right)\in F[z]\subseteq R.
\]
Thus \(R\) is a field. Since it contains both \(L\) and \(K\), it contains their compositum \(LK\); but by construction \(R\subseteq LK\). Hence \(R=LK\), and therefore
\[
\boxed{L\otimes_FK\simeq LK.}
\]

The algebraicity hypothesis matters. For example,
\[
F(x)\otimes_FF(y)\hookrightarrow F(x,y)
\]
is injective, but the tensor product is not a field. In fact \(F(x)\otimes_FF(y)\) is a localization of \(F[x,y]\) in which denominators are products \(a(x)b(y)\), and \(1/(x+y)\) does not belong to it.

## 2. Cyclic extensions and radicals

Let \(F\) be a field and let \(n\ge1\). Assume
\[
\operatorname{char}(F)\nmid n
\]
and that \(F\) contains a primitive \(n\)-th root of unity \(\zeta_n\).

Take \(a\in F^\times\), choose \(\alpha\) with \(\alpha^n=a\), and put
\[
K=F(\alpha).
\]
The roots of \(X^n-a\) are
\[
\alpha,\zeta_n\alpha,\ldots,\zeta_n^{n-1}\alpha.
\]
Since \(\zeta_n\in F\), all of them lie in \(K\). Moreover,
\[
(X^n-a)'=nX^{n-1},
\]
and because \(\operatorname{char}(F)\nmid n\), the polynomial \(X^n-a\) is separable. Hence \(K/F\) is Galois.

If \(\sigma\in\operatorname{Gal}(K/F)\), then
\[
\sigma(\alpha)^n=\sigma(\alpha^n)=a,
\]
so \(\sigma(\alpha)=\zeta_n^i\alpha\) for some \(i\). Hence
\[
\sigma\longmapsto\frac{\sigma(\alpha)}{\alpha}
\]
defines an injective homomorphism
\[
\operatorname{Gal}(K/F)\hookrightarrow\mu_n.
\]
Since \(\mu_n\) is cyclic, \(\operatorname{Gal}(K/F)\) is cyclic of order dividing \(n\). Thus
\[
\boxed{F(\sqrt[n]{a})/F\text{ is cyclic of degree dividing }n.}
\]

The phrase **degree dividing \(n\)** is important. The degree need not be \(n\); later we shall see that it is controlled by the class of \(a\) in \(F^\times/(F^\times)^n\).

## 3. The converse: Hilbert 90 enters

Now suppose
\[
K/F
\]
is cyclic of degree \(n\), and write
\[
\operatorname{Gal}(K/F)=\langle\sigma\rangle.
\]
Assume again that \(F\) contains a primitive \(n\)-th root of unity \(\zeta_n\). Since
\[
N_{K/F}(\zeta_n)=\zeta_n^n=1,
\]
Hilbert's Theorem 90 gives \(\theta\in K^\times\) such that
\[
\frac{\sigma(\theta)}{\theta}=\zeta_n,
\]
equivalently
\[
\sigma(\theta)=\zeta_n\theta.
\]
Iterating,
\[
\sigma^i(\theta)=\zeta_n^i\theta.
\]
Since \(\zeta_n\) is primitive, these \(n\) elements are distinct. Hence the stabilizer of \(\theta\) in \(\operatorname{Gal}(K/F)\) is trivial. By the Fundamental Theorem of Galois Theory,
\[
[K:F(\theta)]=|\operatorname{Stab}(\theta)|=1,
\]
so \(K=F(\theta)\).

Furthermore,
\[
\sigma(\theta^n)=\sigma(\theta)^n=(\zeta_n\theta)^n=\theta^n,
\]
so
\[
\theta^n\in K^{\operatorname{Gal}(K/F)}=F.
\]
Thus, writing \(a=\theta^n\in F^\times\),
\[
\boxed{K=F(\sqrt[n]{a}).}
\]

We have therefore obtained the classical cyclic form of Kummer theory: if \(\operatorname{char}(F)\nmid n\) and \(F\) contains a primitive \(n\)-th root of unity, then every cyclic extension of degree \(n\) is obtained by adjoining an \(n\)-th root of an element of \(F\).

## 4. Why do we assume \((\operatorname{char}(F),n)=1\)?

Suppose
\[
\operatorname{char}(F)=p
\]
and \(p\mid n\). Already for \(n=p\),
\[
X^p-a
\]
has derivative \(0\), so it is inseparable whenever it is nontrivial. Moreover, in a separable closure \(F^s\),
\[
X^p-1=(X-1)^p,
\]
hence
\[
\mu_p(F^s)=\{1\}.
\]
Thus the usual multiplicative Kummer theory cannot detect cyclic extensions of degree \(p\). More generally, the \(p\)-primary part of the usual Kummer sequence does not behave as the exact sequence of discrete Galois modules that we need. This is why one assumes
\[
\boxed{(\operatorname{char}(F),n)=1.}
\]
Later we shall see that in characteristic \(p\), cyclic extensions of degree \(p\) are instead described by Artin--Schreier theory.

## 5. The fundamental Kummer exact sequence

Let \(F^s\) be a separable closure of \(F\), and put
\[
G_F=\operatorname{Gal}(F^s/F).
\]
Assume \((\operatorname{char}(F),n)=1\). Then the \(n\)-th power map is surjective on \((F^s)^\times\), with kernel \(\mu_n\), so we have a short exact sequence of \(G_F\)-modules
\[
1\longrightarrow\mu_n\longrightarrow(F^s)^\times\xrightarrow{(\cdot)^n}(F^s)^\times\longrightarrow1.
\]

One way of viewing Galois cohomology is as the sequence of derived functors of the invariants functor \(M\mapsto M^{G_F}\). Equivalently,
\[
H^i(G_F,M)\simeq\operatorname{Ext}^i_{\mathbf Z[G_F]}(\mathbf Z,M).
\]
Thus the short exact sequence above gives a long exact cohomology sequence. The relevant portion is
\[
F^\times\xrightarrow{(\cdot)^n}F^\times\xrightarrow{\delta}H^1(G_F,\mu_n)\longrightarrow H^1(G_F,(F^s)^\times).
\]
Hilbert 90 tells us that
\[
H^1(G_F,(F^s)^\times)=0.
\]
Therefore \(\delta\) is surjective and its kernel is exactly \((F^\times)^n\). Hence
\[
\boxed{F^\times/(F^\times)^n\simeq H^1(G_F,\mu_n).}
\]

## 6. What is the connecting homomorphism?

Take \(a\in F^\times\), and choose \(\alpha\in F^s\) such that
\[
\alpha^n=a.
\]
For \(\sigma\in G_F\),
\[
\left(\frac{\sigma(\alpha)}{\alpha}\right)^n
=\frac{\sigma(\alpha^n)}{\alpha^n}
=\frac{\sigma(a)}a=1,
\]
so
\[
\frac{\sigma(\alpha)}{\alpha}\in\mu_n.
\]
Define
\[
c_a(\sigma)=\frac{\sigma(\alpha)}{\alpha}.
\]
Then
\[
c_a(\sigma\tau)=\frac{\sigma\tau(\alpha)}{\alpha}
=\sigma\left(\frac{\tau(\alpha)}{\alpha}\right)\frac{\sigma(\alpha)}{\alpha}
=c_a(\sigma)\,\sigma(c_a(\tau)),
\]
which is precisely the \(1\)-cocycle condition. Therefore
\[
\delta(a)=[c_a].
\]
The connecting homomorphism is thus extremely concrete: it records how Galois automorphisms move an \(n\)-th root of \(a\).

## 7. When \(\mu_n\subset F\)

Suppose now that all \(n\)-th roots of unity lie in \(F\). Then \(G_F\) acts trivially on \(\mu_n\). Hence the cocycle relation simplifies to
\[
c(\sigma\tau)=c(\sigma)c(\tau),
\]
so every cocycle is simply a continuous homomorphism
\[
G_F\longrightarrow\mu_n.
\]
Moreover, for the trivial action all \(1\)-coboundaries are trivial. Therefore
\[
H^1(G_F,\mu_n)=\operatorname{Hom}_{\mathrm{cont}}(G_F,\mu_n).
\]
Combining this with Kummer theory,
\[
\boxed{F^\times/(F^\times)^n\simeq\operatorname{Hom}_{\mathrm{cont}}(G_F,\mu_n).}
\]

## 8. The kernel of the Kummer character

Let \(a\in F^\times\), choose \(\alpha\) such that \(\alpha^n=a\), and consider
\[
c_a:G_F\longrightarrow\mu_n,\qquad c_a(\sigma)=\frac{\sigma(\alpha)}{\alpha}.
\]
Then
\[
c_a(\sigma)=1\iff \sigma(\alpha)=\alpha.
\]
Therefore
\[
\ker(c_a)=\operatorname{Gal}(F^s/F(\alpha)).
\]
Consequently, by Galois theory,
\[
G_F/\ker(c_a)\simeq\operatorname{Gal}(F(\alpha)/F),
\]
while by the first isomorphism theorem,
\[
G_F/\ker(c_a)\simeq\operatorname{im}(c_a)\subseteq\mu_n.
\]
Hence
\[
\operatorname{Gal}(F(\alpha)/F)\simeq\operatorname{im}(c_a),
\]
so \(F(\alpha)/F\) is cyclic of degree dividing \(n\).

## 9. Why do we look at \(F^\times/(F^\times)^n\)?

There is already an elementary reason. If
\[
a=bc^n,\qquad c\in F^\times,
\]
then
\[
\sqrt[n]{a}=c\sqrt[n]{b},
\]
so
\[
F(\sqrt[n]{a})=F(\sqrt[n]{b}).
\]
Thus adjoining an \(n\)-th root cannot distinguish \(a\) from \(a\) multiplied by an \(n\)-th power. This is exactly why the quotient
\[
F^\times/(F^\times)^n
\]
appears.

But there is a second subtlety. Different elements of \(F^\times/(F^\times)^n\) can still give the same field. For example, if \([a]\) has order \(m\), then the elements
\[
[a]^r,\qquad (r,m)=1,
\]
generate the same cyclic subgroup and determine the same kernel of the corresponding character. Thus it is really the cyclic subgroup
\[
\langle[a]\rangle\subseteq F^\times/(F^\times)^n
\]
that remembers the cyclic extension. If \([a]\) has order \(m\), then
\[
[F(\sqrt[n]{a}):F]=m.
\]
Hence cyclic subgroups of order \(m\mid n\) in \(F^\times/(F^\times)^n\) correspond to cyclic extensions of degree \(m\).

## 10. What if \(\mu_n\not\subset F\)?

The Kummer exact sequence is still valid whenever
\[
(\operatorname{char}(F),n)=1,
\]
and therefore
\[
\boxed{F^\times/(F^\times)^n\simeq H^1(G_F,\mu_n)}
\]
still holds. What changes is the \(G_F\)-action on \(\mu_n\).

If \(\mu_n\not\subset F\), then \(\mu_n\) is generally a nontrivial \(G_F\)-module. Thus a cocycle satisfies
\[
c(\sigma\tau)=c(\sigma)\sigma(c(\tau)),
\]
rather than
\[
c(\sigma\tau)=c(\sigma)c(\tau).
\]
Therefore \(H^1(G_F,\mu_n)\) can no longer be identified with \(\operatorname{Hom}_{\mathrm{cont}}(G_F,\mu_n)\). Nor, in general, can we identify \(\mu_n\) with the trivial \(G_F\)-module \(\mathbf Z/n\mathbf Z\).

Cyclic extensions of degree dividing \(n\) are instead described by continuous characters
\[
G_F\longrightarrow\mathbf Z/n\mathbf Z,
\]
that is,
\[
H^1(G_F,\mathbf Z/n\mathbf Z)
=\operatorname{Hom}_{\mathrm{cont}}(G_F,\mathbf Z/n\mathbf Z),
\]
where \(\mathbf Z/n\mathbf Z\) carries the trivial \(G_F\)-action. When \(\mu_n\subset F\), choosing a primitive \(n\)-th root of unity gives an isomorphism of \(G_F\)-modules
\[
\mathbf Z/n\mathbf Z\simeq\mu_n,
\]
and the two descriptions coincide. When \(\mu_n\not\subset F\), they do not.

### The torsor picture

For \(a\in F^\times\), let
\[
T_a=\{x\in F^s:x^n=a\}.
\]
The group \(\mu_n\) acts on \(T_a\) by multiplication. This action is free and transitive: if \(x,y\in T_a\), then
\[
\left(\frac yx\right)^n=1,
\]
so there is a unique \(\zeta\in\mu_n\) such that \(y=\zeta x\). Such a set is called a **\(\mu_n\)-torsor**. Concretely, once one root is chosen, multiplying it by the elements of \(\mu_n\) gives every root exactly once.

Choose \(\alpha\in T_a\). Then
\[
\mu_n\longrightarrow T_a,\qquad \zeta\longmapsto\zeta\alpha
\]
is a bijection. Under this identification, since \(\sigma(\alpha)=c_a(\sigma)\alpha\), we have
\[
\sigma(\zeta\alpha)=\sigma(\zeta)c_a(\sigma)\alpha.
\]
Thus the induced Galois action on the copy of \(\mu_n\) is
\[
\boxed{\zeta\longmapsto \sigma(\zeta)c_a(\sigma).}
\]
The factor \(c_a(\sigma)\) is precisely the twisting data recorded by the class \([c_a]\in H^1(G_F,\mu_n)\).

If we replace \(\alpha\) by another root \(\alpha'=\xi\alpha\), with \(\xi\in\mu_n\), then
\[
c_{\alpha'}(\sigma)
=\frac{\sigma(\xi\alpha)}{\xi\alpha}
=\frac{\sigma(\xi)}{\xi}\,c_\alpha(\sigma).
\]
Thus changing the chosen root changes the cocycle by a coboundary, so the cohomology class is independent of the choice.

Now suppose \(\mu_n\subset F\). Then \(\sigma(\xi)=\xi\) for every \(\xi\in\mu_n\). Hence the coboundary factor
\[
\frac{\sigma(\xi)}{\xi}
\]
is \(1\), so changing the chosen root does not change the cocycle at all. The original \(G_F\)-action on \(\mu_n\) is trivial, and the twisted action becomes simply
\[
\zeta\longmapsto c_a(\sigma)\zeta.
\]
Thus \(c_a\) is an honest character \(G_F\to\mu_n\).

At the same time, once \(F\) already contains \(\mu_n\), adjoining one root \(\alpha\) automatically gives all the roots \(\zeta\alpha\). Hence \(F(\alpha)\) is the splitting field of \(X^n-a\); since the polynomial is separable, \(F(\alpha)/F\) is Galois, and its Galois group is cyclic. This is why, when \(\mu_n\subset F\), the torsor picture and the cyclic-field picture line up so neatly.

If \(\mu_n\not\subset F\), the torsor still exists perfectly well, but the field generated by one chosen root need not contain the other roots. For example,
\[
F=\mathbf Q,\qquad n=3,\qquad a=2.
\]
Then
\[
[2]\in\mathbf Q^\times/(\mathbf Q^\times)^3
\simeq H^1(G_{\mathbf Q},\mu_3),
\]
but
\[
\mathbf Q(\sqrt[3]{2})/\mathbf Q
\]
is not Galois, since it does not contain \(\zeta_3\sqrt[3]{2}\) and \(\zeta_3^2\sqrt[3]{2}\). Thus \(H^1(G_F,\mu_n)\) still classifies the Kummer classes, or equivalently these \(\mu_n\)-torsors, but when the \(G_F\)-action on \(\mu_n\) is nontrivial those classes do not directly classify cyclic Galois extensions of \(F\).

## 11. The characteristic-\(p\) analogue: Artin--Schreier theory

Suppose now that
\[
\operatorname{char}(F)=p.
\]
As observed above, \(X^p-a\) is inseparable, so adjoining \(p\)-th roots is not the correct way to construct cyclic extensions of degree \(p\). Instead consider the additive map
\[
\wp:F^s\longrightarrow F^s,\qquad x\longmapsto x^p-x.
\]
Its kernel is \(\mathbf F_p\), so we have an exact sequence of \(G_F\)-modules
\[
0\longrightarrow\mathbf F_p\longrightarrow F^s\xrightarrow{x\mapsto x^p-x}F^s\longrightarrow0.
\]
Taking Galois cohomology gives
\[
F\xrightarrow{\wp}F\longrightarrow H^1(G_F,\mathbf F_p)\longrightarrow H^1(G_F,F^s).
\]
Additive Hilbert 90 gives
\[
H^1(G_F,F^s)=0.
\]
Hence
\[
\boxed{F/\wp(F)\simeq H^1(G_F,\mathbf F_p),}
\]
where
\[
\wp(F)=\{x^p-x:x\in F\}.
\]
Since \(\mathbf F_p\) has trivial \(G_F\)-action,
\[
H^1(G_F,\mathbf F_p)=\operatorname{Hom}_{\mathrm{cont}}(G_F,\mathbf F_p).
\]
Thus equations
\[
X^p-X-a
\]
play in characteristic \(p\) the role played by \(X^n-a\) in Kummer theory.

## 12. From cyclic extensions to Kummer extensions

So far we have essentially studied one radical at a time. Kummer theory naturally allows us to adjoin many radicals simultaneously.

Assume again that
\[
(\operatorname{char}(F),n)=1,\qquad \mu_n\subset F.
\]
Let
\[
D\subseteq F^\times/(F^\times)^n
\]
be a finite subgroup. Choose representatives
\[
a_1,\ldots,a_r\in F^\times
\]
whose classes generate \(D\), and define
\[
K_D=F\left(\sqrt[n]{a_1},\ldots,\sqrt[n]{a_r}\right).
\]
Such an extension is an \(n\)-Kummer extension. Since every individual radical extension is Galois and cyclic of degree dividing \(n\), their compositum \(K_D/F\) is a finite abelian Galois extension whose Galois group has exponent dividing \(n\).

## 13. A small duality lemma

Let \(A\) be a finite abelian group of exponent dividing \(n\). Put
\[
A^\vee=\operatorname{Hom}(A,\mathbf Z/n\mathbf Z).
\]
There is a natural map
\[
A\longrightarrow A^{\vee\vee},
\]
given by evaluation:
\[
a\longmapsto\bigl(\chi\longmapsto\chi(a)\bigr).
\]
For finite abelian \(A\) of exponent dividing \(n\), this map is an isomorphism:
\[
\boxed{A\simeq A^{\vee\vee}.}
\]

There is also a natural isomorphism
\[
\mu_n\otimes_{\mathbf Z/n\mathbf Z}A^\vee
\longrightarrow\operatorname{Hom}(A,\mu_n),
\]
given explicitly by
\[
\zeta\otimes\chi\longmapsto\bigl(a\longmapsto\zeta^{\chi(a)}\bigr).
\]
After choosing a primitive \(n\)-th root \(\zeta_n\), we may identify \(\mu_n\simeq\mathbf Z/n\mathbf Z\), but the formulation above keeps the roots of unity visible, which is exactly what we want for the Kummer pairing.

## 14. The Kummer pairing

Let
\[
G=\operatorname{Gal}(K_D/F).
\]
For \(\sigma\in G\) and \([a]\in D\), choose \(\alpha\in K_D\) with \(\alpha^n=a\), and define
\[
\langle\sigma,[a]\rangle=\frac{\sigma(\alpha)}{\alpha}.
\]
Since
\[
\left(\frac{\sigma(\alpha)}{\alpha}\right)^n=1,
\]
the value lies in \(\mu_n\). Thus we have a map
\[
\boxed{G\times D\longrightarrow\mu_n.}
\]

We check that it is well defined. If \(\alpha'=\zeta\alpha\) with \(\zeta\in\mu_n\), then \(\zeta\in F\), so
\[
\frac{\sigma(\alpha')}{\alpha'}
=\frac{\sigma(\zeta\alpha)}{\zeta\alpha}
=\frac{\zeta\sigma(\alpha)}{\zeta\alpha}
=\frac{\sigma(\alpha)}{\alpha}.
\]
If \(a'=ab^n\) with \(b\in F^\times\), we may take \(\alpha'=\alpha b\), and again the value does not change. Hence the pairing depends only on \([a]\in D\).

It is also bilinear. For \(\sigma,\tau\in G\),
\[
\langle\sigma\tau,[a]\rangle
=\frac{\sigma\tau(\alpha)}{\alpha}
=\langle\sigma,[a]\rangle\langle\tau,[a]\rangle,
\]
because \(\mu_n\subset F\). Similarly, if \([a],[b]\in D\), choosing \(\alpha^n=a\) and \(\beta^n=b\),
\[
\langle\sigma,[ab]\rangle
=\frac{\sigma(\alpha\beta)}{\alpha\beta}
=\langle\sigma,[a]\rangle\langle\sigma,[b]\rangle.
\]

## 15. The left kernel

Suppose \(\sigma\in G\) satisfies
\[
\langle\sigma,[a]\rangle=1
\]
for every \([a]\in D\). Then \(\sigma\) fixes every chosen \(n\)-th root of every element of \(D\). But \(K_D\) is generated over \(F\) by these roots, so \(\sigma=\operatorname{id}\). Therefore the left kernel is trivial, and the pairing gives an injection
\[
G\hookrightarrow\operatorname{Hom}(D,\mu_n).
\]

## 16. The right kernel

Now suppose \([a]\in D\) satisfies
\[
\langle\sigma,[a]\rangle=1
\]
for every \(\sigma\in G\). Choose \(\alpha\in K_D\) with \(\alpha^n=a\). Then \(\sigma(\alpha)=\alpha\) for every \(\sigma\in G\), so
\[
\alpha\in K_D^G=F.
\]
Therefore
\[
a=\alpha^n\in(F^\times)^n,
\]
hence \([a]=1\) in \(F^\times/(F^\times)^n\). So the right kernel is also trivial, and
\[
D\hookrightarrow\operatorname{Hom}(G,\mu_n).
\]

## 17. Kummer duality

Since \(D\) and \(G\) are finite abelian groups of exponent dividing \(n\), their dual groups have the same cardinality as the original groups. From the two injections
\[
G\hookrightarrow\operatorname{Hom}(D,\mu_n),
\qquad
D\hookrightarrow\operatorname{Hom}(G,\mu_n),
\]
we obtain
\[
|G|\le|D|,
\qquad
|D|\le|G|.
\]
Hence \(|G|=|D|\), and both injections are isomorphisms:
\[
\boxed{\operatorname{Gal}(K_D/F)\simeq\operatorname{Hom}(D,\mu_n)}
\]
and
\[
\boxed{D\simeq\operatorname{Hom}(\operatorname{Gal}(K_D/F),\mu_n).}
\]
Equivalently, the Kummer pairing
\[
\operatorname{Gal}(K_D/F)\times D\longrightarrow\mu_n
\]
is a **perfect pairing**. In particular,
\[
\boxed{[K_D:F]=|D|.}
\]

The two sides may be displayed as
\[
\operatorname{Gal}(K_D/F)\longrightarrow\operatorname{Hom}(D,\mu_n),
\qquad
\sigma\longmapsto
\left([a]\mapsto\frac{\sigma(\sqrt[n]{a})}{\sqrt[n]{a}}\right),
\]
and dually
\[
D\longrightarrow\operatorname{Hom}(\operatorname{Gal}(K_D/F),\mu_n),
\qquad
[a]\longmapsto
\left(\sigma\mapsto\frac{\sigma(\sqrt[n]{a})}{\sqrt[n]{a}}\right).
\]

## 18. Cyclic extensions as the rank-one case

Suppose \(D\) is cyclic:
\[
D=\langle[a]\rangle.
\]
Then
\[
K_D=F(\sqrt[n]{a}),
\]
and Kummer duality gives
\[
\operatorname{Gal}(K_D/F)\simeq\operatorname{Hom}(\langle[a]\rangle,\mu_n).
\]
If \([a]\) has order \(m\), then
\[
|\operatorname{Gal}(K_D/F)|=m,
\]
and therefore
\[
[F(\sqrt[n]{a}):F]=m.
\]
So the cyclic extensions with which we began are precisely the special case of Kummer theory in which the subgroup \(D\) is generated by a single class.

What initially looked like the elementary statement
\[
K=F(\sqrt[n]{a})
\]
is therefore the rank-one shadow of a broader duality:
\[
\boxed{\text{finite subgroups of }F^\times/(F^\times)^n
\quad\longleftrightarrow\quad
\text{finite abelian Kummer extensions of }F.}
\]
The bridge between the two sides is the deceptively simple expression
\[
\boxed{\frac{\sigma(\sqrt[n]{a})}{\sqrt[n]{a}}.}
\]
That expression first appeared when we studied a single cyclic extension, reappeared as the connecting homomorphism in the Kummer exact sequence, and finally became the perfect pairing underlying the general theory.

Perhaps that is the main point of Kummer theory: adjoining radicals and taking characters of the absolute Galois group are not two unrelated constructions. Once the required roots of unity are present, they are two descriptions of the same arithmetic phenomenon.

## 19.  A final glimpse toward class field theory

There is a striking resemblance between the picture above and local class field theory.

Let \(K\) now be a local field. Local class field theory provides the reciprocity map

\[
\operatorname{rec}_K:K^\times\longrightarrow
\operatorname{Gal}(K^{\mathrm{ab}}/K),
\]

and for every finite abelian extension \(L/K\) it induces an isomorphism

\[
\boxed{
K^\times/N_{L/K}(L^\times)
\;\simeq\;
\operatorname{Gal}(L/K).
}
\]

Thus finite abelian extensions of \(K\) are encoded by open subgroups of finite index in \(K^\times\), namely the norm groups

\[
N_{L/K}(L^\times).
\]

Notice the similarity with Kummer theory. When \(\mu_n\subset K\), a cyclic extension

\[
L=K(\sqrt[n]{a})
\]

is described by a Kummer character

\[
c_a:G_K\longrightarrow\mu_n,
\qquad
c_a(\sigma)=
\frac{\sigma(\sqrt[n]{a})}{\sqrt[n]{a}}.
\]

The extension is determined by the kernel of this character. Local class field theory gives another description of the same extension: it corresponds to the norm subgroup

\[
N_{L/K}(L^\times)\subset K^\times,
\]

and

\[
K^\times/N_{L/K}(L^\times)
\simeq
\operatorname{Gal}(L/K).
\]

So in Kummer theory we describe an abelian extension by a character of the absolute Galois group, while local class field theory turns the picture around and replaces the abelianized Galois group by the much more concrete multiplicative group \(K^\times\).

There is an even closer connection. If \(\mu_n\subset K\), the \(n\)-th Hilbert symbol gives a pairing

\[
(\ ,\ )_n:
K^\times/(K^\times)^n
\times
K^\times/(K^\times)^n
\longrightarrow
\mu_n.
\]

For

\[
L=K(\sqrt[n]{a}),
\]

the map

\[
b\longmapsto(a,b)_n
\]

is a character of \(K^\times\), and its kernel is precisely

\[
N_{L/K}(L^\times).
\]

Thus

\[
\boxed{
b\in N_{L/K}(L^\times)
\iff
(a,b)_n=1.
}
\]

This gives a beautiful bridge between the two theories: the Kummer class of \(a\) determines the extension \(L/K\), while local class field theory identifies exactly which elements of \(K^\times\) are norms from that extension.

In this sense, the Kummer pairing we have just studied is already a first glimpse of the reciprocity and duality phenomena that lie at the heart of local class field theory.


