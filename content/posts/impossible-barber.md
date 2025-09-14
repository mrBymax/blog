---
title: "The Thought Experiment of the Impossible Barber"
date: 2025-09-15T00:00:00+02:00
mathjax: true
toc: true
tocBorder: true
draft: true
---

# Introduction

I wanted to start my TE series with a pretty famous one: *Russel's Paradox* (or the Barber Paradox).
Let's see if we can find together some scenarios that appear reasonable, but that are unfeasible.

## Problem Statement

> The barber is the "one who shaves all those, and those only, who do not shave themselves". The question is, does the barber shave himself?

Or, in my favourite way of writing it:
$$
(\exists{x})(\text{person}(x)\land(\forall{y})(\text{person}(y)\implies(\text{shaves}(x,y) \iff\lnot\text{shaves(y,y)})))
$$

To my fellow Computer Scientists (and general Undecidability Enthusiasts), please be patient! :D

_We'll come back to the problem later in this article, before I think it's useful to give some historical background._

## History

`May 1901`

Russell is attempting to discover some flaws in Cantor's proof that "there is no greater cardinal number" when, out of the blue, a new idea, something he never considered appeared.

Here are the words he used to describe what he found:

> There is just one point where I have encountered a difficulty. You state that a function too, can act as the indeterminate element. This I formerly believed, but now this view seems doubtful to me because of the following contradiction. Let w be the predicate: to be a predicate that cannot be predicated of itself. Can w be predicated of itself? From each answer its opposite follows. Therefore we must conclude that w is not a predicate. Likewise there is no class (as a totality) of those classes which, each taken as a totality, do not belong to themselves. From this I conclude that under certain circumstances a definable collection does not form a totality.

He was talking to Gottlob Frege, a German mathematician, pretty known at the time. At the same time, Frege was preparing to publish the second volume of _"Grundgesetze der Arithmetik"_ and he took advantage of the situation to respond to Russel's doubts, with a copy of his book.

But the problem was not solved...

`WWI -> 1921`

Later in the century, a few mathematicians tried to dispose the paradox, but every one failed. 
The most important book published in 1921 (but started at the German front during WWI) was "Tractatus Logico-Philosophicus" by Ludwig Wittgenstein.
In that book (TLP for short), Wittgenstein proposed the following statement:

> The reason why a function cannot be its own argument is that the sign for a function already contains the prototype of its argument, and it cannot contain itself. For let us suppose that the function F(fx) could be its own argument: in that case there would be a proposition F(F(fx)), in which the outer function F and the inner function F must have different meanings, since the inner one has the form O(fx) and the outer one has the form Y(O(fx)). Only the letter 'F' is common to the two functions, but the letter by itself signifies nothing. This immediately becomes clear if instead of F(Fu) we write (do) : F(Ou) . Ou = Fu. That disposes of Russell's paradox. (Tractatus Logico-Philosophicus, 3.333)

### Digression: Tractatus Logico-Philosophicus

What TLP brought to the World is very interesting, and it is recognised as "one of the most significant philosophical works of the century". The main thesis could be summarised into seven propositions:

**Proposition 1**

Proposition 1 presents a concise account of Wittgenstein's metaphysical view, emphasizing that the world is the totality of facts, not things. Facts determine what is or is not the case and are situated in logical space. The world divides into facts, with each element having the potential to be the case independently of others. This section sets the foundation for his picture theory of language by outlining how facts form the core of what constitutes the world.

**Propositions 2 and 3**

These sections explore Wittgenstein's view that the world consists of facts, which are combinations of objects, rather than substances. Objects are described as simple and forming the substance of the world, inherently unalterable and substantial. The theory further elaborates on the picture theory of language, explaining that the world is a totality of interconnected atomic facts, and propositions picture this world by sharing logical structures. Language is likened to a geometric projection representing facts, emphasizing that common structural features must be shown, not said.

**Propositions 4.N to 5.N**

In Propositions 4 to 5, Wittgenstein delves into the nature of philosophy, asserting that many philosophical statements are nonsensical due to misunderstandings of language logic. Philosophy's role is not to produce doctrines but to clarify thoughts, setting limits to what is expressible. He introduces truth tables and conditions that revolutionize logical analysis, emphasizing tautologies and internal relations over external laws of inference. This portrays philosophy as fundamentally different from natural sciences, with a focus on elucidation rather than scientific propositions.

**Proposition 6.N**

Proposition 6 introduces a logical notation emphasizing that all logical sentences derive from a series of NOR operations. Wittgenstein extends his proposition calculus to encapsulate predicate logic, suggesting that logic and mathematics, due to their tautological nature, transcend the metaphysical world. The Tractatus ultimately suggests that philosophical problems dissolve when we understand the limits of language. The paradox of self-referential nonsense is explored, with various interpretative approaches offered, concluding with the analogy of the Tractatus as a ladder to be discarded once climbed.

**Proposition 7**

Proposition 7, the final statement of the Tractatus, encapsulates Wittgenstein's position on the limits of linguistic expression, famously stating: 'Whereof one cannot speak, thereof one must be silent.' This underscores the text's conclusion that language has boundaries beyond which it cannot meaningfully go.

(~Fun Fact: This can also be proven using Grammars' theory and parse trees :D~).

### I AM LYING!

`c. 600 BC`

> "I said in my alarm, Every man is a liar!" Is David telling the truth or is he lying? If it is true that every man is a liar, and David's statement, "Every man is a liar" is true, then David also is lying; he, too, is a man. But if he, too, is lying, his statement that "Every man is a liar", consequently is not true. Whatever way you turn the proposition, the conclusion is a contradiction. Since David himself is a man, it follows that he also is lying; but if he is lying because every man is a liar, his lying is of a different sort.

As you may have guessed, this is just an ancient version of the paradox!
The problem of the liar exploits the common beliefs about truth and falsity, that _in reality_ may lead to contradictions.

For example:
$$
\text{(A): The statement (A) is False}
$$

Make your bet: _is (A) true or false?_

If (A) is false, then "This statement is false", is true. Therefore (A) must be true which contradicts what has been said before.
And we obtain the same thing all the way around!

It's a stall! What do we do?

That's the point: we don't know! BUT we can achieve something.


## Goedel's Incompleteness

These two fundamental theorems are used to set the limits of provability in formal axiomatic theories. These results have been published in 1931 and are important both in mathematical logic and in philosophy of mathematics.

### First Theorem

The first incompleteness theorem states that no consistent system of axioms whose theorems can be listed by an effective procedure (i.e. an algorithm) is capable of proving all truths about the arithmetic of natural numbers. 

For any such consistent formal system, there will always be statements about natural numbers that are true, but that are unprovable within the system. Equivalently, there will always be statements about natural numbers that are false, but that are unprovably false within the system.

### Second Theorem

The second incompleteness theorem, an extension of the first, shows that the system cannot demonstrate its own consistency.

Employing a diagonal argument, Gödel's incompleteness theorems were among the first of several closely related theorems on the limitations of formal systems. They were followed by Tarski's undefinability theorem on the formal undefinability of truth, Church's proof that Hilbert's Entscheidungsproblem is unsolvable, and Turing's theorem that there is no algorithm to solve the halting problem.


## A Word on Kleene (and Curry)'s Work
## A Word on Church's Work

## What to bring Home?

## POP-Culture Time!

Oh yes! This is my favourite part of the article!



