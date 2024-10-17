# Unit Lemmas #

The purpose of this repository is to provide advocation for unit lemmas and to catalog types of unit lemmas.

The original ISSRE paper on this topic is unit-lemmas.pdf from 2020. The accompanying 5-minute talk can
be found at UnitLemmas.mp4. A shorter 2-minute "pitch talk" can be found at UnitLemmas_pitch.mp4. The slides
can be found at UnitLemmas.pptx. Finally, some PVS files related to the paper can be found in the PVS directory.
Additional PVS files might be added there later to provide more detailed examples.

In short, *unit lemmas* are to formal specifications what *unit tests* are to software. They are designed to
supplement other forms of verification of formal requirements and specifications, by proving whether formal
definitions (e.g., of functions) have the properties one would expect of them (e.g., one would expect `=`
to be reflexive, and `<` to be irreflexive). Unit lemmas have the additional benefit that they will often
be useful in proving the high-level properties for which the system is designed to possess.

Since the publication of that paper, we have identified additional types of unit lemmas. This repository has
been created so that others might also add other types of unit lemmas that we have not considered.

Also note that with LLMs playing an increasing role in software production, formal proof of software correctness
will become increasingly important. One can extrapolate that in the not-to-distant future, LLMs will assist
formal methods experts in creating formal specifications, as well as proving properties over formal
specifications. This future will have the following impact on unit lemmas:

1. Unit lemmas will typically become much easier to prove.
2. Unit lemmas will become a more critical tool for identifying flaws in tool-generated specifications.

# Unit Lemma Classification #

Note that **Totality** is not included in this list due to formal specification languages already requiring it.

**Reflexivity/Irreflexivity**: For a *predicate* `p`, should `p(A, A)` return true (or false) for all `A`?

**Idempotence**: For a *function* `f`, should `f(A, A)` return `A` for all `A`?

**Idempotence with Composition**: For a *function* `f`, should `f(f(A))` return `f(A)` for all `A`?

**Symmetry/Asymmetry**: For a *predicate* `p`, should `p(A, B, …)` return the same result as `p(B, A, …)`?
Should `p(A, B, …)` return the opposite result as `p(B, A, …)`?

**Transitivity**: For a *predicate* `p`, does `p(A, B, …)` and `p(B, C, …)` imply `p(A, C, …)` for all `A`, `B`, `C`?

**Commutativity**: For a function `f`, should `f(A, B, …)` return the same result as `f(B, A, …)`?

**Identity**: For a function `f`, is there an `I` such that `f(A, I) = f(I, A) = A` for all `A`?

**Absorption**: For a function `f`, is there a `0` (e.g., `false`) such that `f(A, 0) = f(0, A) = 0` for all `A`?

**Associativity**: For a function `f`, should `f(A, f(B, C, …), …) = f(f(A, B, …), C, …)` for all `A`, `B`, `C`?

**Inverse**: For a function `f`, is there an inverse function `g` such that for all inputs `A`, `f(g(A))=g(f(A))=A`?

**Monotonicity**: For a function `f`, does an increase in the inputs imply an increase (or decrease) in the result?
I.e., does A < B necessarily imply f(A) < f(B), f(A) ≤ f(B), f(A) > f(B), or f(A) ≥ f(B)?

**Linearity**: As a special case of monotonicity, does a function `f` have the property that for all a, b, X, Y,
f(aX + bY) = af(X) + bf(Y)?

**Stability**: For a function `f`, does a small change to its inputs necessarily imply a small change to its output?

**Degeneracy**: For a function over two or more objects of the same type, is there a consistent result to
expect (e.g., 0) when two of the objects are identical? (See also: *Reflexivity/Irreflexivity* and *Idempotence*)

**Invariance**: Are there invariances in a function such that the function returns the same value under that invariance?
For example, if calculating the area of a polygon, should the function return the same value under rotation (yes),
translation (yes), reflection (maybe)? *NB: **Permutations**, either of the inputs such that `(A, B, C)` becomes*
*`(B, C, A)` or within an input (such as a list), could be a type of invariance for a function, and **symmetry** is*
*a special case of those permutations.*

**Specialization/Generalization**: For functions `f` and `g`, is `f` a special case of `g`? E.g., if `f` defines
exponentiation over integers and `g` defines exponentiation over reals, then should `f(x, y) = g(x, y)` for all
integers `x` and `y`?

**Range**: Should the result of a specified function fall into a particular range (e.g., only positive values), where
this range is not encoded into the return type?

**Composition**: Should a predicate over two objects always be true (or always false) when one argument (e.g., point)
is a component of the other (line)?

**Alternate Formulation**: Is there an alternate formulation of the specification component that is equally valid?

**Exemplar**: Is there a simple example that demonstrates a case where the function should return a particular value?
E.g., an area calculation for arbitrary polygons returning 4 when the polygon represents a square of side length 2.

**Logical Contradiction**: Can the specification be used to prove false is true? If a specification can be used to
prove false, then we know a flaw exists.

# BibTex References #

## Unit Lemma Paper ##

```
@inproceedings{hocking2020unit,
  title={Unit Lemmas for Detecting Requirement and Specification Flaws},
  author={Hocking, Ashlie B and Rowanhill, Jonathan C and Di Vito, Ben L},
  booktitle={2020 IEEE International Symposium on Software Reliability Engineering Workshops (ISSREW)},
  pages={163--164},
  year={2020},
  organization={IEEE}
}
```

## GitHub repository ##

```
@misc{hocking2024unit,
  title={Unit Lemmas},
  url={https://github.com/BenHocking/UnitLemmas},
  urldate={10/17/2024},
  author={Hocking, Ashlie B.},
  year={2024}, month={Oct}
}
```
# Change Log #

* 10/11/2022, Ben Hocking, added invariance, specialization/generalization, and exemplar unit lemma types
* 10/17/2024, Ben Hocking, added idempotence (inc. with composition), monotonicity, linearity, stability, and notes on LLMs and totality.