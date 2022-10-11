# Unit Lemmas

The purpose of this repository is to provide advocation for unit lemmas and to catalog types of unit lemmas.

The original ISSRE paper on this topic is unit-lemmas.pdf, from 2020, and the accompanying 5-minute talk can
be found at UnitLemmas.mp4.

Since the publication of that paper, we have identified additional types of unit lemmas. This repository has
been created so that others might also add other types of unit lemmas that we have not considered.

# Unit Lemma Classification #

**Reflexivity/Irreflexivity**: For a *predicate* `p`, should `p(A, A)` return true (or false) for all `A`?

**Symmetry/Asymmetry**: For a *predicate* `p`, should `p(A, B, …)` return the same result as `p(B, A, …)`?
Should `p(A, B, …)` return the opposite result as `p(B, A, …)`?

**Transitivity**: For a *predicate* `p`, does `p(A, B, …)` and `p(B, C, …)` imply `p(A, C, …)` for all `A`, `B`, `C`?

**Commutativity**: For a function `f`, should `f(A, B, …)` return the same result as `f(B, A, …)`?

**Degeneracy**: For a function over two or more objects of the same type, is there a consistent result to
expect (e.g., 0) when two of the objects are identical?

**Identity**: For a function `f`, is there an `I` such that `f(A, I) = f(I, A) = A` for all `A`?

**Absorption**: For a function `f`, is there a `0` (e.g., `false`) such that `f(A, 0) = f(0, A) = 0` for all `A`?

**Associativity**: For a function `f`, should `f(A, f(B, C, …), …) = f(f(A, B, …), C, …)` for all `A`, `B`, `C`?

**Inverse**: For a function `f`, is there an inverse function `g` such that for all inputs `A`, `f(g(A))=g(f(A))=A`?

**Invariance**: Are there invariances in a function such that the function returns the same value under that invariance?
For example, if calculating the area of a polygon, should the function return the same value under rotation (yes),
translation (yes), reflection (maybe)?

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
@misc{hocking2022unit,
  title={Unit Lemmas},
  url={https://github.com/BenHocking/UnitLemmas},
  urldate={10/11/2022},
  author={Hocking, Ashlie B.},
  year={2022}, month={Oct}
}
```
# Change Log #

10/11/2022, Ben Hocking, added invariance, specialization/generalization, and exemplar unit lemma types