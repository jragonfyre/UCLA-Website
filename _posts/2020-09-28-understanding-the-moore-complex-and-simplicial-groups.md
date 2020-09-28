---
layout: post
title: Understanding the Moore complex and simplicial groups
math: true
latex-title: Understanding the Moore complex and simplicial groups
author: Jason Schuchardt
categories:
- simplicial stuff
- math
summary: If $$G$$ is a simplicial group, then there is a complex of (not necessarily)
  groups, $$NG$$, called the Moore complex with $$NG_q = \bigcap_{i=1}^q \ker d_i.$$
  The key result we'd like to understand is the following. $$f:G\to H$$ is injective
  (resp. surjective) if and only if $$Nf:NG\to NH$$ is injective (resp. surjective).
date: 2020-09-28 11:33 -0700
---
If $$G$$ is a simplicial group, then there is a complex of 
(not necessarily) groups, $$NG$$, called the [Moore complex][1] with 
$$NG_q = \bigcap_{i=1}^q \ker d_i.$$ The key result we'd like to understand 
is the following. 

{:.math-quote .proposition #prop1 }
> **Proposition 1:**{:.math-header } If $$G$$ and $$H$$ are simplicial groups, 
> then $$f:G\to H$$ is injective (resp. surjective) if and only
> if $$Nf:NG\to NH$$ is injective (resp. surjective), where by 
> surjective and injective we mean degreewise surjective
> and injective.

This result is Lemma 5 of Chapter II, Section 3 of Quillen's homotopical algebra,
and the proof is said to be similar to the proof of (3.17) in Dold and Puppe's 
*Homologie nicht-additiver Funktoren. Anwendungen*, however, since I can't read 
German very well, nor find a proof on the internet, since most sources focus on 
simplicial abelian groups, I thought I'd write up a proof using what I could make
out of Dold and Puppe's argument.

The key fact necessary for the proof is the following. 
If $$G$$ is a simplicial abelian group, $$g\in G_q$$, and
$$0\le i\le q$$ is an index, then we can write $$g$$ as a product of a $$q$$-simplex with
only the $$i$$th face being nonzero, and degenerate simplices.

Given this fact, we have the following proof of [Proposition 1](#prop1).

*Proof.* 

First we'll start with injectivity, which doesn't require the fact.
Certainly if $$f$$ is injective, then $$Nf$$ is injective. Conversely,
suppose that $$Nf$$ is injective. We'll prove that $$f$$ is injective 
by inducting on the degree. Certainly $$f_0=Nf_0$$ is injective.
Then if $$f(g)=1$$, for $$g\in G_q$$,
we have $$d_if(g)=1=f(d_ig)$$ for all $$i$$.
By the inductive hypothesis, we have 
$$d_ig=1$$ for all $$i$$, so $$g\in NG_q$$, and thus 
$$g=1$$, since $$Nf$$ is injective.

Now we'll move on to the surjectivity half. 
If $$f$$ is surjective, and $$h\in NH_q,$$
then we can produce a preimage of $$h$$ in 
$$NG_q$$ in the following manner.

Let $$g_q$$ be an arbitrary preimage of $$h$$.
Inductively define $$g_{i-1}=g_i\cdot (s_{i-1}d_ig_i)^{-1}$$.
We then have that for $$j>i$$, $$d_j g_i =1,$$
since if $$j=i,$$
we have 
$$d_ig_{i-1}
=(d_ig_i)\cdot d_is_{i-1}d_ig_i)^{-1}
=1,$$
and for $$j>i,$$
we have

$$d_jg_{i-1}
=(d_jg_i)\cdot (d_js_{i-1}d_ig_i)^{-1}
=1\cdot (s_{i-1}d_{j-1}d_ig_i)^{-1}
=(s_{i-1}d_id_jg_i)^{-1}
=1.
$$

Moreover, for $$i\ge 0,$$
$$f(g_i)=h,$$
since $$f(g_q)=h,$$
and for $$0\le i < q,$$

$$f(g_i)
=f(g_{i+1}\cdot (s_id_{i+1}g_{i+1})^{-1})
=h\cdot (s_id_{i+1}f(g_{i+1}))^{-1}
=h\cdot (s_id_{i+1}h)^{-1}
=h\cdot 1,$$

since $$h\in NH_q.$$

Thus $$g_0\in NG_q,$$ and 
$$f(g_0)=h,$$
so $$Nf$$ is surjective.

Finally, if we assume $$Nf$$ is surjective, 
we can prove that $$f$$ is surjective by inducting on 
the degree. As in the injective case, 
since $$Nf_0=f_0,$$ we have that $$f_0$$ is 
surjective.

Now assume that $$f_i$$ is surjective for $$i<q$$.
Now we can use the fact stated above. 
If $$h\in H_q,$$ 
we can write $$h$$ as a product of simplices 
$$h=\prod_i h_i,$$
with exactly one of the $$h_i$$ in $$NH_q$$,
and the rest degenerate.

Then by the assumption that $$Nf$$ is surjective
and the inductive hypothesis, we can find 
$$g_i$$ with $$f(g_i)=h_i$$ for all $$i$$,
and then $$f\left(\prod_i g_i\right) = \prod_ih_i=h,$$
so $$f_q$$ is surjective. $$\blacksquare$$

Now we'd like to prove the fact. It suffices to show 
the following precise statement, which is well known,
and has proofs available elsewhere, like on the 
$$n$$Lab [for instance][2], so I'll omit the proof.

{:.theorem .math-quote}
> **Theorem (J.C. Moore, 1954)**{:.math-header} The simplicial set underlying any 
> simplicial group is a Kan complex, and moreover, for any horn,
> horn fillers may be constructed algorithmically as the product 
> of degenerate simplices.

Thus to prove the fact, we can do the following.
Let $$g$$ be a $$q$$-simplex of a simplicial
group $$G,$$ let $$\lambda_i$$ be the restriction of $$g$$ to the 
$$i$$-horn,
$$\Lambda^q_i$$, and let $$g_i$$ be a filler of $$\lambda_i$$ by 
a product of degenerate simplices.
Then $$gg_i^{-1}$$ has only its $$i$$th face nonzero, and 
$$g=(gg_i^{-1})g_i,$$ as desired.






[1]: https://ncatlab.org/nlab/show/Moore+complex
[2]: https://ncatlab.org/nlab/show/simplicial+group#AsKanComplexes

