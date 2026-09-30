# Manuscript and editorial notes

The standalone manuscript is `planar_favorite_sites.tex`; the compiled paper is
`output/pdf/planar_favorite_sites.pdf`. The original `blueprint_verified.md`
has been preserved. The paper includes a four-part proof-ideas section, all
proofs from the blueprint, a notation guide, and linked references. No author
name or affiliation has been supplied.

To compile the standalone source:

```sh
latexmk -norc -pdf planar_favorite_sites.tex
```

The working section files are in `manuscript_parts/`. The final `.tex` has
their contents embedded and does not require these files to compile.

## Source corrections made during drafting

1. **The centered stopping rule in the auxiliary endpoint estimate.** The
   blueprint's discussion of equation (29) identified descendants of counts
   stopped at an off-center global boundary with an exact Galton–Watson
   forest. Rosen's cited equation (2.8) concerns a centered stopping rule.
   Section 5.1.1 now states and proves the complete-centered-excursion
   version, with counts denoted by a superscript `c`. This narrows the
   auxiliary assertion to the version justified by its source. The later
   lattice upper argument already has its own centered continuation and
   relative word comparison, and continues to use those.
2. **Separate spherical radii.** Rosen chooses different initial radii in
   the upper and lower arguments. Section 5 states the two choices separately
   rather than imposing their incompatible requirements on a single radius.
3. **Net maximum in the Brownian tail input.** The supremum attributed to
   Rosen's Theorem 1.6 is restricted to the deterministic net `F_L`, as in
   that theorem. This is the version used for endpoint truncation.
4. **External source precision.** The Zaitsev exponential estimate uses
   `log*(N/tau^2)`, with `tau >= 1`. The fixed-law logarithmic coupling
   consequence is unchanged. The inner-subdomain DGFF maximum is attributed
   to Biskup–Louidor's extremal-process statement and its consequences,
   rather than identifying their equation (1.8) itself as that maximum law.
   The escape question in Hao–Li–Okada–Zheng is anchored explicitly to
   Remark 1.4(1) of arXiv version 1.
5. **Endpoint and clock wording.** The last root return occurs *by* the
   specified time, not strictly before it. Witness times remain path-dependent
   after removing the auxiliary clocks. Geometric-clock parameter conventions
   and the conditional expectation at a fixed clock value are explicit.

These corrections are recorded separately because the task was manuscript
drafting. The work included targeted checks of cited statements, independent
reader checks of the exposition, and consistency checks of the assembly; it
was not a separate, exhaustive referee audit of the blueprint.

## Artifact checks

The integrated manuscript was compiled with pdfLaTeX. Equation, theorem and
bibliographic references resolve, with no duplicate labels or missing glyphs.
The TeX linter reports no errors; its comma warnings concern tuples and
ordinary multiargument notation. All PDF pages were rendered and visually
inspected for clipping, overlap and formula placement.
