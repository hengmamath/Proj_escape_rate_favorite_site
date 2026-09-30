# Continuum and transfer section: integration notes

Draft file: `continuum_transfer.tex`. This covers all material in blueprint_verified.md lines 408–1719, reorganized into setup, compact lemma interfaces, and the full calculations. Labels are `eq:ct-external-*`, `eq:ct-smooth-*`, and `eq:ct-transfer-*`, where `*` is the original equation tag (`prime` replaces apostrophe). The three lemma labels are unchanged. Equations now number sequentially. Only external cross-reference is `lem:elementary-walk-estimates`.

## Verified bibliographic interfaces and source corrections

- Rosen2022: Jay Rosen, *Tightness for Thick Points in two dimensions*, arXiv:2203.14394. Primary HTML: https://arxiv.org/html/2203.14394 . Checked §2 geometry, Proposition 2.5 representative construction, Lemmas 3.3–3.4, Theorem 1.6, and Appendix Theorem 9.1(a). This was targeted source checking for writing, not an independent audit of all proofs.
- HLOZ2025: Hao–Li–Okada–Zheng, *Favorite Sites for Simple Random Walk in Two and More Dimensions*, arXiv:2409.00995. Primary HTML: https://arxiv.org/html/2409.00995v2 . The displayed two annular hitting probabilities were checked against Lemma 2.1/(2.5).
- Zaitsev2003: A. Yu. Zaitsev, *Estimates for the Strong Approximation in Multidimensional Central Limit Theorem*, arXiv:math/0304373. Primary PDF: https://arxiv.org/pdf/math/0304373 . Theorem 2 and Corollary 1 checked. Corrected the displayed exponent from `log^* N / tau^2` to `log^*(N/tau^2)` and stated `tau>=1`. For fixed law the O(log N) consequence is unchanged.

The blueprint used one fixed r0 for both upper and lower spherical arguments, whereas Rosen §2 uses `2r_* <= h_0`, and §3 explicitly resets to smaller r0 with `4h(r_-1) <= r_*`. The draft states these as separate fixed choices. No comparison mixes those two radii.

The blueprint's discussion preceding (29) asserted that descendants conditional on a population stopped at the off-center global boundary tau are exactly GW, citing Rosen (2.8). That equation is a centered-stop calculation, and the asserted exact identification is not justified by it. The draft replaces this unused version of (29) by its fully specified complete-centered-excursion version, denoting counts T^c. The later lattice endpoint proof (45f–g) already works independently with an explicitly centered continuation and its ideal source law; its conclusion is unchanged. This correction should be mentioned in the delivery notes because it narrows the original auxiliary claim, rather than silently certifying it.

The blueprint (38f) wrote an unrestricted `sup_y` and attributed it to Rosen Theorem 1.6; the theorem has `sup_{y in F_L}`. The draft states the net version, which is all the endpoint truncation needs. The extension from z>=z0 to bounded nonnegative z follows by enlarging C.

The draft retains the blueprint's convenient x,y>=2 restriction in the quoted GW upper theorem, although the checked source in fact allows sqrt(2). Thus the supplied extra-ancestor argument is sufficient but unnecessary; no strengthening of the imported theorem is claimed.

## Rendering and remaining scope

The isolated section compiles with pdfLaTeX to 18 pages, using standard article, amsmath/amsthm/mathrsfs and 1-inch margins. All internal references resolve. No overfull or underfull boxes remain in this isolated compile. All 18 pages were also rendered and visually inspected for clipping and overlap; none was observed. The only undefined references/citations there are expected dependencies on the main manuscript's lemma and bibliography.

The last fixed number of terminal levels have affine-circle error O(e^{-J+2h})=o(1) under h=o(J); their O(1) rounding error fits the stated guard width. No definite issue in that terminal switch was found during the scoped drafting pass. The full terminal bridge/conditioning argument lies in the next section and was not audited here.
