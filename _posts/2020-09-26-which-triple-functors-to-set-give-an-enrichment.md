---
layout: post
title: Which triple functors to Set give an enrichment?
math: true
latex-title: Which triple functors to $$\Set$$ give an enrichment?
author: Jason Schuchardt
categories:
- category theory
- adjunctions
- math
summary: "If $$\\calV$$ is a monoidal category, \n$$\\underline{\\calC}$$ is a $$\\calV$$-category,
  then we get a functor \n$$\\calV^\\op\\times \\calC^\\op\\times \\calC\\to \\Set,$$\nwhere
  $$\\calC$$ is the underlying ordinary category of \n$$\\underline{\\calC}$$ defined
  by \n$$\\calV(-,\\underline{\\calC}(-,-))$$. We'd like to understand which such
  functors \ndescribe enriched categories.\n"
date: 2020-09-26 17:54 -0700
---
Let's recall the definition of a category enriched in a monoidal category $$\calV.$$

{: .definition .math-quote }
> **Definition 1**{: .math-header } 
> A category $$\uln{\calC}$$ enriched over $$\calV$$ (or a $$\calV$$-category for short)
> consists of the data 
> of 
> 
> 1. a collection of objects $$\calC_0$$, 
> 2. for each pair of objects $$x,y\in\calC_0$$
>    an object $$\uln{\calC}(x,y)$$ of $$\calV,$$
> 3. for each triple of objects $$x,y,z\in\calC_0,$$ a morphism in $$\calV$$
>    $$\circ_{x,y,z} : \uln{\calC}(y,z)\otimes\uln{\calC}(x,y) \to \uln{\calC}(x,z),$$
> 4. and for each object $$x\in\calC_0$$ a 
>    $$\calV$$-morphism $$\iota_x : 1_\calV \to \uln{\calC}(x,x)$$ such that 
> 
> the composition is associative and unital in the sense of satisfying
> appropriate coherence conditions.

It turns out that this is equivalent to specifying the following alternate data

{: .definition .math-quote }
> **Definition 2**{: .math-header } 
> A category $$\uln{\calC}$$ enriched over $$\calV$$ (or a $$\calV$$-category for short)
> consists of the data 
> of 
> 
> 1. an ordinary category $$\calC$$, and 
> 2. a bifunctor $$\uln{\calC}:\calC^\op\times\calC\to \calV,$$ 
> 3. an extranatural transformation
>    $$\circ_{x,y,z} : \uln{\calC}(y,z)\otimes\uln{\calC}(x,y) \to \uln{\calC}(x,z),$$
>    or equivalently a natural transformation 
>    
>    $$\circ : \int^{y\in\calC} \uln{\calC}(y,z)\otimes\uln{\calC}(x,y)\to \uln{\calC}(x,z),$$
>    
>    assuming the coend exists in $$\calV,$$
> 4. and for each object $$x\in\calC_0$$ a 
>    $$\calV$$-morphism $$\iota_x : 1_\calV \to \uln{\calC}(x,x)$$ such that 
> 
> the composition is associative and unital in the sense of satisfying
> appropriate coherence conditions, and 
> the maps $$\calC(x,y)\to\calV(1_\calV,\uln{\calC}(x,y))$$ given by 
> $$f\mapsto f^* \circ \iota_y$$ and $$f\mapsto f_* \circ \iota_x$$ are 
> bijections.

The first definition prioritizes enriched categories as separate from ordinary 
categories. The second focuses on enriched categories as additional structure on 
ordinary categories. The equivalence is given by the fact that an enriched category
$$\uln{\calC}$$
in the first sense has an underlying ordinary category $$\calC$$ whose hom sets are 
given by $$\calC(x,y):=\calV(1_\calV,\uln{\calC}(x,y))$$. The maps $$\iota_x$$
are then the identities in the underlying category.

Given an enriched category then, we can consider the functor 
$$\calV(-,\uln{\calC}(-,-)) : \calV^\op\times\calC^\op\times \calC\to \Set.$$
Essentially we have taken the Yoneda embedding of the enriched category structure.

Suppose that we have a generic such functor, $$A:\calV^\op\times\calC^\op\times\calC\to \Set.$$
What conditions can we impose on it such that when the functors $$A(-,x,y)$$ are representable for 
all $$x$$ and $$y$$ the representing objects form an enriched category structure which has $$A$$ as its 
Yoneda embedding?

Well, first of all, we have distinguished elements $$\iota_x\in A(1_\calV,x,x)$$ for all $$x\in\calC,$$
which are the identity elements. In fact, in order for this to be the data of an enriched category whose 
underlying category is $$\calC,$$ we need a natural isomorphism 
$$\calC(-,-)\simeq A(1_\calV,-,-),$$
with $$1_x$$ corresponding to $$\iota_x.$$

In addition,
we have a composition extranatural transformation
$$\circ : A(v,y,z)\times A(u,x,y)\to A(v\otimes u,x,z),$$
which for a functor coming from an enriched category is given by tensoring the maps together and 
composing with the composition of the enriched category. The composition should be associative, and 
the units and the composition should be compatible in the sense 
that 
$$\iota_y \circ f = f = f\circ \iota_x$$ 
modulo the unit isomorphisms of $$\calV.$$

Now suppose the functors $$A(-,x,y)$$ are all representable. Can we recover the composition of 
$$\uln{\calC}$$ when $$A$$ comes from $$\uln{\calC}$$? 
Let $$(\uln{\calC}(x,y),\alpha_{x,y})$$ represent $$A(-,x,y).$$
Then 

$$\alpha_{y,z}\circ \alpha_{x,y} \in A(\uln{\calC}(y,z)\otimes \uln{\calC}(x,y),x,z)$$

corresponds to some map 

$$\circ_{x,y,z} : \uln{\calC}(y,z)\otimes\uln{\calC}(x,y)\to\uln{\calC}(x,z)$$

such that $$\alpha_{y,z}\circ \alpha_{x,y} = \circ_{x,y,z}^*\alpha_{x,z}.$$
We can use this condition to show that this recovered composition is associative and 
unital, and its not hard to check that this recovered composition will be the same 
as the original composition in the case that $$A$$ came from an enriched category.

As a result, we have the following conclusion:

{: .proposition .math-quote }
> **Definition/Proposition 3**{: .math-header } 
> If $$\calC$$ is an ordinary category, $$\calV$$ is a monoidal category, then 
> a *preenrichment* of $$\calC$$ over $$\calV$$ is the data of 
> 
> 1. A functor $$A:\calV^\op\times\calC^\op\times\calC\to \Set,$$
> 2. a natural isomorphism $$\calC(-,-)\simeq A(1_\calV,-,-),$$
> 3. an extranatural transformation 
>    
>    $$ \circ : A(v,y,z)\otimes A(u,x,y) \to A(v\otimes u, x,z)$$
> 
> such that $$\circ$$ is associative and unital in the sense discussed above.
> 
> Then as a result of the discussion above, $$A$$ describes an enrichment of 
> $$\calC$$ over $$\calV$$ if and only the functors 
> $$A(-,x,y)$$ are representable for all $$x$$ and $$y$$ in $$\calC.$$ 
> Similarly $$A$$ describes a $$\calV$$-module structure on $$\calC$$ 
> if and only if the functors $$A(v,x,-)$$ are representable for all 
> $$v\in\calV$$ and $$x\in\calC$$, and $$A$$ describes a $$\calV$$-cotensor
> structure on $$\calC$$ if and only if the functors 
> $$A(v,-,y)$$ are representable for all $$v\in\calV$$ and $$y\in\calC$$.
> 
> When we have a Day convolution on presheaves on $$\calV,$$ (I think we need 
> to assume that $$\calV$$ is small), then this is equivalent to
> the data of an enriching 
> of $$\calC$$ in presheaves on $$\calV$$ with Day convolution. 

All of this seems to come from the profunctor point of view, which seems to have 
the advantage that we don't have to assume that anything is representable.
Solutions to existence problems always exist from this point of view, they are 
just presheaves rather than genuine objects.

It occurs to me that we could probably do this entire construction for a 
monoidal category, which seems like it should give the definition of a 
[promonoidal category](https://ncatlab.org/nlab/show/promonoidal+category),
or any other adjunction plus structure set up.



