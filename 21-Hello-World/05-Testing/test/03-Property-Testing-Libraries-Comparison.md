# Property Testing Libraries Comparison

Besides QuickCheck, there are two other property testing libraries in the Purescript ecosystem:
- [StrongCheck](https://pursuit.purescript.org/packages/purescript-strongcheck/4.1.1/docs/Test.StrongCheck.Perturb) and its corresponding [StrongCheck-Laws](https://pursuit.purescript.org/packages/purescript-strongcheck-laws/2.0.0/docs/Test.StrongCheck.Laws) package
- [Jack](https://pursuit.purescript.org/packages/purescript-jack/2.0.0) (currently doesn't work for `0.12.0`)

Here's a comparison table between the three:

| Feature | QuickCheck | StrongCheck | Jack |
| - | - | - | - |
| Equivalent Haskell Library | QuickCheck | QuickCheck | Hedgehog |
| Uses Arbitrary | Yes | Yes | No
| Supports "Shrinking" | No | No | Yes
| Supports "exhaustive" testing | No | Yes | No
| Supports "statistical" testing | No | Yes | No
| Can generate functions<br><br>Supports monadic tests | Yes | Yes | No

According to @garyb, one of the core contributors to Purescript:
> Originally StrongCheck (SC) was fully stack safe where there were some cases that QuickCheck (QC) was not, but QC is now too. I wouldn't use SC now unless I needed `smallCheck` (exhaustive testing) or `statCheck` (statistical testing) as it is significantly slower, to the point of it being annoying on some tests

Consider also reading through [QuickCheck, Hedgehog, and Validity](https://www.fpcomplete.com/blog/quickcheck-hedgehog-validity), an article on Haskell's different testing libraries.

Lastly, QuickCheck's `Gen` type and combinators are used in `Benchotron`, the Purescript benchmarking library (covered next)
