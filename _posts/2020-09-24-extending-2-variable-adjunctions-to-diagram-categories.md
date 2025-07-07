---
layout: post
title: Extending 2-variable adjunctions to diagram categories
latex-title: Extending 2-variable adjunctions to diagram categories
date: 2020-09-24 18:58 -0700
math: true
categories: 
  - category theory
  - adjunctions
  - math
author: Jason Schuchardt
summary: |
  We'd like to understand and generalize the result 
  that the category of simplicial $$\calC$$-objects is 
  enriched, tensored and cotensored over $$\sSet.$$
---

We'd like to understand the following proposition, due (as near as I can tell) to Quillen
in *Homotopical Algebra*:

{: .proposition .math-quote }
> **Proposition**{: .math-header } 
  If $$\calC$$ is a category, then the category of simplicial $$\calC$$-objects is
  enriched, tensored, and cotensored over $$\sSet$$.

In fact, this is a special case of the following proposition

{: .proposition .math-quote }
> **Proposition**{:.math-header }
> If $$-\otimes- : \calC\times \calD\to \calE$$ forms a 2-variable adjunction with 
> $$[-,-] : \calC^\op\times\calE \to \calD$$ and $$\{-,-\} : \calD^\op\times \calE\to \calC$$,
> $$I$$ is a small category, and $$\calC$$ and $$\calD$$ are complete and cocomplete, then there is a 
> 2-variable adjunction $$-\widehat{\otimes} - : \calC^I \times \calD^I \to \calE^I$$, with left and right adjoints 
> $$\widehat{[-,-]}$$ and $$\widehat{\{-,-\}}$$ respectively, defined by the following formulae, 
> where $$F:I\to \calC$$, $$G:I\to\calD$$, $$H:I\to \calE$$:
> 
> $$
> F\widehat{\otimes}G = 
> I\toby{\Delta}
> I\times I 
> \toby{F\times G}
> \calC\times\calD
> \toby{\otimes}
> \calE,
> $$
> 
> $$
> \widehat{[F,H]}
> =
> \int_{i\in I} \left[ I(-,i) \otimes Fi,Hi \right],
> $$
> 
> $$
> \widehat{\{G,H\}}
> =
> \int_{i\in I} \left\{ I(-,i) \otimes Gi,Hi \right\}
> $$

*Proof.*

The proof is a standard exercise in manipulating ends, we'll give the natural isomorphism for $$\widehat{\otimes}$$ 
and $$\widehat{[-,-]}$$, since the other natural isomorphism is the symmetric.

$$
\newcommand\of[1]{\left({#1}\right)}
\newcommand\hattimes{\widehat{\otimes}}
\newcommand\hatbrak[2]{\widehat{\left[{#1},{#2}\right]}}
\newcommand\hatbrace[2]{\widehat{\left\{ {#1},{#2}\right\}}}
\begin{aligned}
\calE^I
\of{
    G, \hatbrak{F}{H}
}
&\simeq 
\int_{j\in I} 
\calE
\of{
    Gj, \int_{i\in I} [I(j,i)\otimes Fi, Hi]
}
\\
&\simeq 
\int_{i,j\in I} 
\calE
\of{
    Gj, [I(j,i)\otimes Fi, Hi]
}
\\
&\simeq 
\int_{i,j\in I} 
\calE
\of{
    \of{I(j,i)\otimes Fi}\otimes Gj, Hi
}
\\
&\simeq 
\int_{i,j\in I} 
\calE
\of{
    I(j,i)\otimes \of{Fi\otimes Gj}, Hi
}
\\
&\simeq 
\int_{i,j\in I} 
\Set\of{
    I(j,i),
    \calE
    \of{
        Fi\otimes Gj, Hi
    }
}
\\
&\simeq 
\int_{i\in I}
\calE
\of{
    Fi\otimes Gi, Hi
}
\\
&\simeq
\calE^I\of{F\hattimes G,H} \qquad \blacksquare
\end{aligned}
$$


The result itself is fairly mundane to prove, but the ideas 
behind it and the consequences are quite interesting.

## Some Consequences

Let's first observe some corollaries.

{: .corollary .math-quote }
> **Corollary**{:.math-header } 
  (a) If $$\calV$$ is closed (symmetric) monoidal, complete,
      and cocomplete, then 
      $$\calV^I$$ is also closed (symmetric) monoidal.
  (b) $$\sSet$$ is closed symmetric
      monoidal.
  (c) If $$\calC$$ is $$\calV$$-enriched, tensored, and 
      cotensored, complete and cocomplete as an ordinary 
      category, and $$\calV$$ is as in (a), then 
      $$\calC^I$$ is $$\calV^I$$-enriched, tensored, and 
      cotensored.
  (d) If $$\calC$$ is complete and cocomplete, then 
      $$\calC^{\Delta^\op}$$ is $$\sSet$$-enriched, tensored,
      and cotensored.

*Proof.* 

(a) Since the multiplication on the functor category is 
the pointwise tensor product, it's easy to check that we get 
monoidal structure natural isomorphisms on the functor 
category.

(b) This follows from (a), since $$\sSet=\Set^{\Delta^\op}$$.

(c) Directly analagous to (a), since being enriched, tensored,
and cotensored can be expressed as there being a tensor
$$\calV\times \calC \to \calC$$, 
which has appropriate unitality and associativity isomorphisms
which are compatible with those of the monoidal structure on 
$$\calV$$, and admitting the appropriate adjoints to form a 
2-variable adjunction. 

(d) Follows from (c) in exactly the same manner as (a).
We note that the tensor product of a simplicial set $$K_\bullet$$ and 
a simplicial object $$C_\bullet$$ is given by 

$$(K_\bullet\otimes C_\bullet)_n = K_n\otimes C_n,$$

the hom simplicial set between simplicial objects $$C_\bullet$$
and $$D_\bullet$$ is given by 

$$\underline{[\Delta^\op,\calC]}(C_\bullet,D_\bullet)_n
= [\Delta^\op,\calC](\Delta^n \otimes C_\bullet, D_\bullet),$$

and the cotensor of a simplicial set $$K_\bullet$$ with a 
simplicial object $$C_\bullet$$ is given by 

$$[K_\bullet,C_\bullet]_n = \int_{m\in \Delta^\op} 
[\Delta^n_m\times K_m, C_m].$$


## Some Thoughts and Observations

Firstly, we can exploit the symmetry of 2-variable adjunctions to get 2-variable adjunctions
$$(\calC^\op)^I\times \calE^I \to \calD^I$$ given by 
$$(F,H)\mapsto [F-,H-]$$
and $$(\calD^\op)^I\times \calE^I\to \calC^I$$ given by 
$$(G,H)\mapsto \{G-,H-\}$$. 
The left mapping adjoint in these adjunctions gives us 2-variable adjunctions 
$$\calC^{I^\op}\times \calD^I\to\calE^I$$
and 
$$\calD^{I^\op}\times \calC^I\to \calE^I.$$

In particular, this should give us a simplicial enrichment on the category of cosimplicial
objects. 

The first functor defined is the cotensor, $$[K_\bullet,C_\bullet]_n=[K_n,C_n],$$ as described above, since it is of the 
form $$\sSet^\op\times \calC^\Delta\to \calC^\Delta$$. By symmetry, we can view it as 
a tensor for the purposes of the proposition above. When we think of $$[-,-]:\Set^\op \times\calC \to \calC$$ as the tensor, then 
the right mapping adjoint is of the form $$\calC^\op\times \calC\to \Set^\op$$, which is equivalent to 
$$\calC\times \calC^\op\to\Set .$$  Thus the right mapping adjoint should be given by $$\calC^\op :\calC\times\calC^\op\to \Set.$$
The right mapping adjoint of the cotensor of simplicial objects will thus be of the form 
$$(\calC^\Delta)^\op\times \calC^\Delta \to (\Set^\op)^\Delta \simeq \sSet^\op,$$ and be computed by 

$$(F,G)\mapsto \int^{m\in\Delta} \calC^\op([\Delta^{-}_{m},Fm],Gm),$$

where the end should have become a coend, since we swapped $$\Set^\op$$ with $$\Set$$, but it's going to need to turn back into an end for 
the final formula,
and I can't figure out where the calculation went wrong.
Then (identifying the functor with its opposite) this is
of the form 
$$\calC^\Delta\times(\calC^\Delta)^\op\to \sSet.$$
Note that the arguments to the right mapping functor are reversed from what we expect for the enriched hom functor. Swapping these
gives the formula:

$$
\underline{\calC^\Delta}(F,G)_n = \int_{m\in \Delta} \calC(Fm, [\Delta^n_m,Gm]).
$$

As a quick check, computing

$$
\begin{aligned}
\sSet(K_\bullet,\underline{\calC^\Delta}(F,G)_\bullet)
&\simeq 
\int_{n\in\Delta^\op}\int_{m\in\Delta} \Set(K_n,\calC(Fm,[\Delta^n_m,Gm]))
\\
&\simeq 
\int_{n\in\Delta^\op}\int_{m\in\Delta} \Set(\Delta^{n_m},\calC(Fm,[K_n,Gm]))
\\
&\simeq 
\int_{n\in\Delta^\op}\calC(Fn,[K_n,Gn])
\\
&\simeq 
\calC^{\Delta^\op}(F_\bullet,[K_\bullet,G_\bullet]),
\\
\end{aligned}
$$

as required.

It turns out that we've recovered the construction of the simplicial enriching on cosimplicial objects
described by $$n$$Lab [here](https://ncatlab.org/nlab/show/simplicial+object#simplicial_enrichment), which
we obtain by regarding the category of cosimplicial objects in $$\calC$$ as the opposite of the 
category of simplicial objects in $$\calC^\op.$$

We can compute the hom simplicial sets of the construction on $$n$$Lab as well to verify this. We get

$$
\underline{\calC^\Delta}(F,G)_n = 
\int_{m\in\Delta}\calC^\op([\Delta^n_m,Gm],Fm)=
\int_{m\in \Delta} \calC(Fm, [\Delta^n_m,Gm]).
$$


