# Proof blueprint: the planar favorite-set lower class

Throughout, \(S\) is planar simple symmetric random walk, \(P\) is its
transition operator, and
\[
        g:=\frac2\pi,\qquad
        M_n:=\max_xL_n(x),\qquad
        u_{J,c}:=2gJ^2-cgJ\log J.
\]
Integer parts and changes of radii by bounded factors are suppressed.  All
such changes alter the displayed levels by \(O(J)\), which is smaller than
the \(J\log J\) margins used below.

# lemma lem:elementary-walk-estimates

## statement

There are constants \(c,C\in(0,\infty)\) with the following properties.

1. If \(\tau_R=\inf\{n:\lVert S_n\rVert_2\ge R\}\), then
   \[
       \sup_{\lVert x\rVert<R}E_x\tau_R\le C R^2,\qquad
       \sup_{\lVert x\rVert<R}P_x(\tau_R>mCR^2)\le 2^{-m}.
   \]
2. For all \(N,R\ge1\),
   \[
       P\left(\max_{k\le N}\lVert S_k\rVert_2\ge R\right)
       \le C\exp\{-cR^2/N\}.
   \]
3. Uniformly for \(1\ll r<\lVert x\rVert<R\),
   \[
   P_x(\tau_{\partial D(0,R)}<\tau_{\partial D(0,r)})
     =\frac{\log(\lVert x\rVert/r)+O(r^{-1})}{\log(R/r)}
   \]
   and the complementary inner-hitting probability is obtained by replacing
   the numerator by \(\log(R/\lVert x\rVert)+O(r^{-1})\).
4. Uniformly for \(x\) a bounded factor away from the boundary of
   \(D(0,R)\),
   \[
       G_{D(0,R)}(x,x)=g\log R+O(1).
   \]
   Conditional on first hitting \(x\), the number of visits to \(x\) before
   leaving the disk is geometric with this mean.

## proof

For (1), optional stopping of
\(\lVert S_{n\wedge\tau_R}\rVert_2^2-(n\wedge\tau_R)\), followed by the
one-step overshoot bound, gives the expectation estimate.  Markov's
inequality at time \(2CR^2\), iterated with the strong Markov property,
gives the geometric tail.  Part (2) follows by applying the usual
exponential martingale separately to both coordinates and to both signs.

For (3) we use the following external result, including its normalization.
In Hao--Li--Okada--Zheng, Favorite sites for simple random walk in two and
more dimensions, paper_id HaoLiOkadaZheng2025, arXiv id 2409.00995,
Lemma 2.1, equation (2.5), the complete statement used here is: uniformly
for \(r<\lVert x\rVert<R\), planar simple random walk satisfies
\[
 P_x(H_{\partial D(0,R)}<H_{\partial D(0,r)})
 =\frac{\log(\lVert x\rVert/r)+O(r^{-1})}{\log(R/r)},\qquad
 P_x(H_{\partial D(0,r)}<H_{\partial D(0,R)})
 =\frac{\log(R/\lVert x\rVert)+O(r^{-1})}{\log(R/r)}.
\]
Here \(H\) is the positive-time hitting time and the boundaries are the
digital outer vertex boundaries defined in that paper.  The later
directed-edge convention can differ from this vertex-boundary convention
only within a one-unit radial collar.  Applying the estimate with \(r,R\)
shifted by at most two units, equivalently repeating its potential-kernel
proof at the directed crossing time, changes the logarithmic terms by
\(O(r^{-1})\).  Hence the same estimate holds for the directed-edge rows
below.  The potential-kernel proof of that result also gives (4).  The
geometric assertion in (4) is the strong Markov
property at successive positive returns to \(x\).

# lemma lem:stopped-resolvent

## statement

Let \(0<z<1\), \(N=(1-z)^{-1}\), and let \(\mu\) be a finite positive
measure on \(\mathbb Z^2\) of mass \(\beta\).  Suppose that
\[
       (I-zP)\mu=\alpha\delta_0-\nu,\qquad \nu\ge0,
       \qquad \alpha-\nu(\mathbb Z^2)=(1-z)\beta.                 \tag{1}
\]
There is a universal \(c>0\) such that, whenever
\(2\le f\le N^{1/8}\),
\[
 \mu\left(B\left(0,C\frac{\sqrt N}{f}\right)\right)
       \ge c\beta\,\frac{1+\log f}{f^2}.                         \tag{2}
\]

## proof

Let \(Q_R=[-R,R]^2\cap\mathbb Z^2\) and set
\[
 w_R:=|Q_R|^{-1}{\bf1}_{Q_R}*{\bf1}_{-Q_R}.
\]
Then \(0\le w_R\le1\), \(w_R(0)=1\), and \(w_R\) is supported in
\(B(0,3R)\).  Put
\[
 G_z:=\sum_{n\ge0}z^nP^n,\qquad \phi_R:=G_z*w_R.
\]
Fourier inversion gives
\[
 \widehat{\phi_R}(\theta)=
 \frac{|\widehat{{\bf1}_{Q_R}}(\theta)|^2/|Q_R|}
      {1-z\widehat P(\theta)}\ge0.
\]
Consequently \(\phi_R(y)\le\phi_R(0)\) for every \(y\).  Pairing (1) with
\(\phi_R\) and using \((I-zP)\phi_R=w_R\) yields
\[
\begin{split}
 \mu(w_R)
 &=\alpha\phi_R(0)-\nu(\phi_R)\\
 &\ge(\alpha-\nu(\mathbb Z^2))\phi_R(0)
   =(1-z)\beta\phi_R(0).                                      \tag{3}
\end{split}
\]
The elementary Fourier integral over
\(\{\lVert\theta\rVert\le c/R\}\), together with
\(1-z\widehat P(\theta)\asymp (1-z)+\lVert\theta\rVert^2\),
gives, for \(R^2\le N/4\),
\[
 \phi_R(0)\ge cR^2\left(1+\log\frac N{R^2}\right).              \tag{4}
\]
Since \(\mu(w_R)\le\mu(B(0,3R))\), take
\(R=\lfloor\sqrt N/(4f)\rfloor\) in (3)--(4).  This proves (2),
after changing the absolute radius constant.

# lemma lem:plateau-bijection

## statement

Let \(K\) be independent of the walk with
\[
       P(K=n)=(1-z)z^n,\qquad n\ge0.
\]
Attach independent continuous priorities \((U_x)_{x\in\mathbb Z^2}\) to
the sites and let \(X_K^*\) be the least-priority member of
\(\mathcal F_K\).  If \(\sigma\) and \(\ell\) are respectively its first and
last visit times, then the endpoint law of \(-X_K^*\), restricted by any
condition measurable before the terminal arm described below, is a positive
mixture satisfying (1).  In particular,
\[
 P\left(\lVert X_K^*\rVert_2\le C\frac{\sqrt K}{f}\right)
       \ge c\,\frac{1+\log f}{f^2},\qquad
       2\le f\le N^{1/8}.                                     \tag{5}
\]

## proof

We give the atomwise bijection; this is needed because a mere informal path
reversal does not control plateaux of tied favorites.

Fix a clock atom \(K=n\), a path
\(s=(s_0,\ldots,s_n)\), and first insert
\[
       1=\sum_x{\bf1}_{\{x=X_n^*\}}.
\]
Thus, in the sector currently considered, \(x\) is deterministic while the
priorities are translated.  Put \(m=M_n\), \(r=m-1\), and let
\(\sigma,\ell\) be the first and last visits to \(x\).  Reverse and center
the prefix through \(\ell\):
\[
       A_i=s_{\ell-i}-x,\qquad 0\le i\le\ell.
\]
It has exactly \(r\) positive returns to zero before time
\(\ell-\sigma\).  Hence it decomposes uniquely as
\[
       A=E_1\oplus\cdots\oplus E_r\oplus C,                    \tag{6}
\]
where the \(E_i\)'s are completed positive root excursions and \(C\)
starts at zero, has no positive return to zero, and ends at
\(a=-x\).  The centered forward suffix
\[
       B_i=s_{\ell+i}-x,\qquad 0\le i\le n-\ell,
\]
also has no positive return to zero.

Write \(H_r(y)\) for the number of visits to \(y\ne0\) in the completed
excursions and \(N_C(y),N_B(y)\) for the corresponding positive-time
counts in \(C,B\).  Translate priorities by the fixed sector shift,
\(V_y=U_{x+y}\).  The statement that the root is the priority-selected
favorite is exactly
\[
 H_r(y)+N_C(y)+N_B(y)
       \le r+{\bf1}_{\{V_y>V_0\}},\qquad y\ne0.                 \tag{7}
\]
Indeed, a better-priority site must be strictly below the root's value
\(r+1\), while a worse-priority site may tie it.

Expose the base tuple
\[
       {\cal B}=(r,E_1,\ldots,E_r,B,V)
\]
and define its fixed capacities
\[
       c_{\cal B}(y):=
       r+{\bf1}_{\{V_y>V_0\}}-H_r(y)-N_B(y),\qquad y\ne0.       \tag{8}
\]
Let \(\tau_c\) be the first positive return of a new walk \(C\) to zero or
the first time some \(N_C(y)\) exceeds (8).  The possible terminal arms
are exactly the prefixes \(C_0,\ldots,C_q\) with \(q<\tau_c\).

Conversely, a feasible base tuple and one such prefix reconstruct the
original path: concatenate (6), reverse it, translate by
\(-a=x\), and append the translated suffix \(B\).  Inequality (7) makes
\(x\) a favorite and excludes every better-priority tie; avoidance of zero
by \(B\) makes \(\ell\) its last visit.  The endpoint \(a\) recovers the
sector \(x=-a\), so both the path and the priority translation are unique.
The forward and inverse maps are therefore genuine bijections, including
\(r=0\).

If \(\rho_r\), \(q\), and \(k\) are the lengths of the completed part,
\(C\), and \(B\), reversal and symmetry preserve the path weight and
\[
 z^{\rho_r}4^{-\rho_r}\,
 z^q4^{-q}\,(1-z)z^k4^{-k}
       =(1-z)z^n4^{-n}.                                      \tag{9}
\]
Thus no multiplicity or normalization factor is hidden.

For a fixed capacity let
\[
       g_c(u)=E_0\sum_{q<\tau_c}z^q{\bf1}_{\{C_q=u\}}.
\]
Direct telescoping gives
\[
       (I-zP)g_c=\delta_0-E_0[z^{\tau_c}\delta_{C_{\tau_c}}].  \tag{10}
\]
Mixing (10) with the positive base weights in (9), and optionally
restricting those base weights by a base-measurable event, proves (1).

It remains to make the radius self-normalized.  Whole-path reversal,
translation to the new starting point, and transport of the iid priorities
preserve the joint law and send
\[
       (\sigma,\ell)\longmapsto(n-\ell,n-\sigma).
\]
As \(\sigma\le\ell\),
\[
       E(n-\sigma)=E\ell\ge n/2,
       \qquad P(n-\sigma\ge n/4)\ge1/3.                        \tag{11}
\]
Also \(P(K\ge N/2)\ge1/4\) for all large \(N\).  Hence the restriction
\[
       \Gamma=\{n-\sigma\ge N/8\}
\]
has mixture mass \(\beta\ge1/12\).  In the tuple,
\[
       n-\sigma=(\ell-\sigma)+(n-\ell)=\rho_r+|B|,
\]
so \(\Gamma\) is base-measurable, as required above.  Apply
Lemma lem:stopped-resolvent to this restricted mixture with
\(R=\sqrt{N/8}/f\).  On \(\Gamma\), \(K\ge N/8\), and so
\(R\le\sqrt K/f\).  This proves (5).

# lemma lem:singleton-geometric-localization

## statement

For the same geometric clock, uniformly for \(2\le f\le N^{1/8}\),
\[
 P\left(\mathcal F_K=\{X\},\
        \lVert X\rVert_2\le C\frac{\sqrt K}{f}\right)
       \ge c\,\frac{1+\log f}{f^2}.                            \tag{12}
\]
The conclusion remains valid, up to a universal change of \(c\), after
restricting the output clock to
\[
       aN\le K\le JN,\qquad J=\log N,\qquad
       a=\frac c8\,\frac{1+\log f}{f^2}.                       \tag{13}
\]

## proof

For every atom counted in (5), insert immediately after the last visit to
its priority-selected favorite \(x\) the fixed loop
\[
       x,\ x+e_1,\ x,\ x+e_2,\ x.                             \tag{14}
\]
The local time at \(x\) rises by two, those at the two neighbors rise by
one, and all other local times are unchanged.  Thus \(x\) is the unique
favorite of the new path.  The old suffix avoids \(x\), so in the image the
last visit to the unique favorite is the final vertex of (14).  Removing
the four preceding prescribed steps is therefore the unique inverse.  On
geometrically weighted path atoms the image-to-source weight ratio is
\(z^4/4^4\), bounded below for \(z\) close to one.  This proves (12).

Now \(P(K<aN)\le2a\), while
\(P(K>JN)\le\exp(-J/2)\).  With the constant in (13) chosen after the
constant in (12), these discarded masses total at most half the right-hand
side of (12).  Four added steps are absorbed by changing the universal
constants.

# lemma lem:inherited-profile-dichotomy

## statement

Let \(H\ge0\) be any finitely supported integer profile and let
\(\ell\ge0\) be a second integer profile with a unique maximizer \(y\).
Every maximizer of \(H+\ell\) lies in
\(\operatorname{supp}H\cup\{y\}\).

## proof

If \(y\) is not a maximizer of \(H+\ell\), then
\(\max(H+\ell)>(H+\ell)(y)\ge\ell(y)\).  Outside
\(\operatorname{supp}H\), the profile \(H+\ell\) equals \(\ell\) and is at
most \(\ell(y)\), so every maximizer lies in \(\operatorname{supp}H\).
If \(y\) is a maximizer, uniqueness of the maximum of \(\ell\) shows that
the only possible maximizer outside \(\operatorname{supp}H\) is \(y\).

# proposition prop:critical-recurrence

## statement

Almost surely,
\[
       \liminf_{n\to\infty}
       \frac{R_n^+}{\sqrt{n/\log n}}=0.                        \tag{15}
\]
Consequently, for every \(\gamma\le\tfrac12\),
\[
       \liminf_{n\to\infty}\frac{R_n^+}{a_\gamma(n)}=0.
                                                                    \tag{16}
\]

## proof

Fix \(\varepsilon>0\).  Choose a deterministic sequence
\[
       J_{k+1}=J_k+10\log J_k,\qquad s_k=\lfloor e^{J_k}\rfloor,
\]
and, for the fresh block beginning at \(s_k\), put
\[
       N_k=\frac{e^{J_{k+1}}}{J_{k+1}^2},\qquad
       f_k=C\varepsilon^{-1}\sqrt{J_{k+1}}.
\]
Apply Lemma lem:singleton-geometric-localization to the fresh increment
walk, with an independent geometric clock of mean \(N_k\).  It gives a
unique fresh favorite \(Y_k\) satisfying
\[
       \lVert Y_k\rVert\le\frac{\varepsilon}{8}
             \sqrt{\frac{K_k}{J_{k+1}}}                       \tag{17}
\]
with conditional probability at least
\[
       d_k=c_\varepsilon\frac{\log J_{k+1}}{J_{k+1}},          \tag{18}
\]
even after
\[
       \frac{d_k}{8}N_k\le K_k\le J_{k+1}N_k.                 \tag{19}
\]
For all large \(k\), (19), plus the four insertion steps, is contained in
\([s_k,s_{k+1})\), and its lower endpoint is much larger than \(s_k\).

Let \(H_k(x)=\sum_{j=0}^{s_k-1}{\bf1}_{\{S_j=x\}}\), while the fresh
profile includes its time-zero visit at \(S_{s_k}\).  Thus their sum is
exactly the full profile at \(s_k+K_k\), with no double counting.  The
fresh profile is translated by \(S_{s_k}\).  By
Lemma lem:inherited-profile-dichotomy, at time
\(t_k=s_k+K_k\) every favorite of the full walk belongs either to the old
range or to \(S_{s_k}+Y_k\).

Part (2) of Lemma lem:elementary-walk-estimates and Borel--Cantelli give
\[
       \max_{j\le s_k}\lVert S_j\rVert
       \le \sqrt{s_k}\,J_k
\]
eventually.  The choices above imply, uniformly over (19),
\[
 \sqrt{s_k}\,J_k=o\left(\sqrt{\frac{K_k}{J_{k+1}}}\right),
 \qquad \log(s_k+K_k)\sim J_{k+1},\qquad s_k=o(K_k).            \tag{20}
\]
Combining (17)--(20), every full favorite at \(t_k\) is in
\[
       B\left(0,\frac{\varepsilon}{2}
                    \sqrt{\frac{t_k}{\log t_k}}\right)        \tag{21}
\]
for all sufficiently large successful \(k\).

Moreover \(J_k\sim10k\log k\), and hence
\[
       \sum_kd_k=\infty.                                      \tag{22}
\]
The fresh increments occupy disjoint deterministic blocks.  On the product
space enlarged by the independent clocks and priorities, let \(E_k\)
be the fresh singleton-success event (17), with clock restriction (19).
Its conditional probability given the past at \(s_k\) is at least
\(d_k\).  Lévy's conditional Borel--Cantelli lemma and (22) imply that
\(E_k\) occurs infinitely often almost surely.  Independently, the
old-range bound and the deterministic comparisons (20) hold eventually
almost surely; on their intersection, every sufficiently late \(E_k\)
implies (21).  Thus (21) occurs infinitely often.  Fubini removes the
auxiliary clocks and priorities: for almost every walk path, their
probability of producing infinitely many witness times is one, so that
path itself has infinitely many such deterministic times.

Intersecting over rational \(\varepsilon>0\) proves (15).  Finally,
\[
       \frac{a_{1/2}(n)}{a_\gamma(n)}
       =(\log n)^{\gamma-1/2}\le1
\]
eventually for \(\gamma\le1/2\), which proves (16).

# lemma lem:external-barrier-input

## statement

Here are the exact continuum objects used below.  This notation is the
notation of Rosen, *Tightness for thick points in two dimensions*,
paper_id Rosen2022TightnessThickPoints, arXiv id 2203.14394.

Let \(X\) be spherical Brownian motion started at \(v\), stopped at its
first hit \(\tau\) of \(\partial B_d(v,r_*)\).  When defining source
stopping times we extend it by an independent Brownian continuation;
the safety event below will imply that every portion actually used lies
before \(\tau\).  Put
\[
 h(r)=2\arctan(r/2),\qquad r_j=r_0e^{-j},\qquad h_j=h(r_j),
                                                               \tag{23}
\]
where \(r_0\) is the fixed small number in Rosen (2.2).  Let \(F_j\) be a
maximal \(d_0h_j\)-separated set, augmented if necessary to a
\(d_0h_j\)-cover; thus \(|F_j|\asymp e^{2j}\).  For \(y\in F_L\),
\(T_{y,j}\) is the number, before \(\tau\), of completed excursions from
\(\partial B_d(y,h_{j-1})\) to \(\partial B_d(y,h_j)\), with the initial
and final incomplete pieces omitted.  Its source shell is
\[
       k_y=\inf\{k:y\notin B_d(v,h_k)\}.                       \tag{24}
\]
Pairs have separation shell \(k\) when
\(2h_k<d(y,y')\le2h_{k-1}\).

Set
\[
 \rho_L=2-\frac{\log L}{L},\qquad l_L=l\wedge(L-l),
\]
\[
 \alpha_{z,+}(l)=\rho_Ll+z+l_L^{1/4},\qquad
 \alpha_{z,-}(l)=\rho_Ll+z-l_L^{1/4}.                        \tag{25}
\]
The upper first-crossing event \(U(y,l,z)\) means
\[
 \sqrt{2T_{y,j}}\le\alpha_{z,+}(j)
       \quad(k_y<j<l),qquad
 \sqrt{2T_{y,l}}>\alpha_{z,+}(l).
\]
Rosen's representative construction is deterministic.  With fixed
tie-breaking, every fine center is sent to its closest point of the
predetermined coarser net at scale
\(h_{l+\frac14 l_L^{1/4}}\); equations (2.26)--(2.33) give the buffered
ball inclusions and domination of its traversal count.  Proposition 2.5,
specifically equations (2.34)--(2.35), then proves the complete estimates
\[
 \#\{\hbox{representatives with source }k\}
 \le C\exp\{2(l-k)+\tfrac12l_L^{1/4}\},                       \tag{26}
\]
\[
 P(U(y,l,z))\le
 C\exp\{-2l-l_L^{1/4}\}e^{-2z}.                              \tag{27}
\]
They hold pointwise for \(1\le k\le l\le L-(4\log L)^4\).
Only the choice \(F_L\cap B_d(v,h_{\log L})^c\), and not the proof of
(26)--(27), imposed \(k\le\log L\).  Hence, for any
\(s\le C_0\log L\), summing just the representatives whose source shell
is at least \(s\) gives
\[
 P\big(\exists y:k_y\ge s,\ \exists l\le L-(4\log L)^4:
              U(y,l,z)\big)
       \le C e^{-2s+o(\log L)}e^{-2z}.                        \tag{28}
\]

We also need the endpoint version of the same upper argument.  Let
\({\cal G}_{y,L,z}\) be the event that the upper barrier in (25) is not
crossed from shell \(k_y+1\) through \(L-1\), and put
\(Y_y=\sqrt{2T_{y,L}}\) and \(B_L=\rho_LL+z\).  Uniformly for
\(k_y\le C_0\log L\), every fixed \(\epsilon_0>0\),
\(\epsilon_0L\le q\le B_L+1\), and fixed \(z\), Rosen's
source calculation (2.8), followed by Appendix Theorem 9.1(a), gives
\[
 P\big({\cal G}_{y,L,z},Y_y\in[q,q+1]\big)
 \le C(k_y+1)^C(2+B_L-q)L^{-2}e^{-q^2/(2L)}.                 \tag{29}
\]
For clarity, the complete Galton--Watson result used in this deduction is
Rosen Appendix Theorem 9.1(a): if \(T\) is critical Galton--Watson with
\(P(\xi=m)=2^{-m-1}\), \(T_0=x^2/2\), and
\[
\delta>0,\quad C\ge0,\quad\eta>1,\quad
\epsilon\in(0,1/2),\quad
2\le x,y\le\eta L,\quad x^2/2\in\mathbb N,\quad
0\le x\le a,\quad0\le y\le b,
\]
\[
\begin{split}
P\big(&\sqrt{2T_j}\le a+(b-a)j/L
             +C(j\wedge(L-j))^{1/2-\epsilon},\ 1\le j<L;\\
&\sqrt{2T_L}\in[y,y+\delta]\big)
\le C'\frac{(1+a-x)(1+b-y)}L\sqrt{\frac{x}{yL}}
e^{-(x-y)^2/(2L)}.                                           \tag{30}
\end{split}
\]
Here is the complete source-to-endpoint deduction.  Write \(m=k_y+1\)
and \(N=L-m\).  Conditional on \(T_{y,m}=t\), the descendants
\((T_{y,m+j})_{0\le j\le N}\) are exactly the critical geometric
Galton--Watson chain in (30), started from \(t\).  The logarithmic
gambler--ruin calculation (2.8) gives
\[
 P(T_{y,m}\ge t)\le Cm e^{-t/m},
\]
and hence, after grouping the integer values of \(t\) for which
\(x=\sqrt{2t}\) lies in a unit band,
\[
 P(\sqrt{2T_{y,m}}\in[x,x+1])
       \le Cm^C e^{-x^2/(2m)}.                               \tag{30a}
\]
On \({\cal G}_{y,L,z}\), \(x\le a:=\alpha_{z,+}(m)=O(m)\).
Apply (30) over the remaining \(N\) generations with this \(a\) and
with \(b=B_L+1\).  The needed deterministic barrier inclusion follows
from
\[
 ((m+j)\wedge(L-m-j))^{1/4}
 \le (1-j/N)m^{1/4}+C(j\wedge(N-j))^{1/4};                  \tag{30b}
\]
for \(j\le N/2\) use
\((m+j)^{1/4}\le m^{1/4}+j^{1/4}\) and
\(m^{1/4}j/N\le j^{1/4}\), while for \(j>N/2\) use the
right-end distance directly.  Thus every parameter in (30) has been
specified, including \(x\le a\), \(q\le b\), and
\(x,q\le\eta N\).

The sole positive start not covered by the hypothesis \(x\ge2\) is
\(t=1\).  Couple a process from two ancestors as the sum of two
independent one-ancestor processes.  On the event, of probability
\(1/2\), that the second ancestor has no child in the first generation,
the total process agrees from generation \(1\) onward with the first
process.  The barrier in (30) is imposed precisely at generations
\(1,\ldots,N-1\), so the \(t=1\) contribution is at most twice the same
event for initial population two, to which (30) applies.  The case
\(t=0\) cannot have the positive endpoint \(q\ge\epsilon_0L\).

Multiplication of (30a) with (30), the identity
\[
 \frac{x^2}{k+1}+\frac{(q-x)^2}{L-k-1}
 =\frac{q^2}{L}+
   \frac{L(x-(k+1)q/L)^2}{(k+1)(L-k-1)},                     \tag{31}
\]
proves (29).  Indeed \(q\ge\epsilon_0L\), \(N\asymp L\),
\(x\le Cm\), and so the square-root factor in (30), together with its
explicit \(N^{-1}\), is at most \(Cm^{1/2}L^{-2}\); all remaining source
and summation factors cost only \(m^C\).

No estimate of the form (29) is asserted at \(q=0\): extinction there
has order-one probability.  In the lattice upper bound below,
\(q<\epsilon_0L\) is instead disposed of by the saturated terminal
Chernoff factor.  We shall also use the following truncated version.
If \(n=J-h\), \(m\le C_0\log J\), and
\[
 B_l=\rho_Jl+z+(l\wedge(J-l))^{1/4},
\]
then (29), with \(L\) replaced by \(n\) and \(B_L\) by \(B_n\), holds
for \(\epsilon_0n\le q\le B_n+1\).  To verify the only new point, put
\(\phi(l)=(l\wedge(J-l))^{1/4}\).  Its two Hölder bounds from \(m\)
and \(n\) give
\[
 \phi(m+j)\le(1-j/N)\phi(m)+(j/N)\phi(n)
                 +C(j\wedge(N-j))^{1/4}.                    \tag{31a}
\]
The affine part \(\rho_Jl+z\) interpolates exactly, so (30) applies with
the arbitrary endpoints \(a=B_m,b=B_n+1\).  In particular, no
\(\rho_n\)-barrier theorem is being assumed.

For the lower event, choose once and for all the number \(x_*>0\) in
Rosen's Section 3 so that
\[
                         m_0:=x_*^2\in\mathbb N.             \tag{32a}
\]
(This \(x_*\) is not the variable called \(x\) in Appendix Theorem 9.1;
the latter equals \(\sqrt{2m_0}\) when that theorem is started with
\(m_0\) particles.)  Put
\[
 F_L^0=F_L\cap\{h_1/40\le d(v,y)\le h_1/20\}.
\]
This fixed annulus, instead of Rosen's full ball, retains a fixed
positive area fraction; the one- and two-point sums in Rosen's proof are
therefore unchanged up to constants, and every source index is \(O(1)\).

We spell out the superscript in Rosen (3.3), because it is important for
the stopping-time comparison below.  Write
\(\Gamma_{y,j}=\partial B_d(y,h_j)\) and set
\[
 A_{y,1}=H_{\Gamma_{y,1}},\qquad
 B_{y,i}=\inf\{t>A_{y,i}:X_t\in\Gamma_{y,0}\},
\]
\[
 A_{y,i+1}=\inf\{t>B_{y,i}:X_t\in\Gamma_{y,1}\},
                    \qquad 1\le i<m_0.                    \tag{32b}
\]
The intervals \([A_{y,i},B_{y,i}]\), and only these intervals, are the
first \(m_0\) source excursions; the intervening intervals
\([B_{y,i},A_{y,i+1}]\) are connectors and are not counted.  Set
\(T_{y,1}^{1,m_0}=m_0\).  For \(l\ge2\), define inside each source
interval
\[
 C_{i,l,1}=\inf\{t\ge A_{y,i}:X_t\in\Gamma_{y,l-1}\},
\]
\[
 D_{i,l,q}=\inf\{t>C_{i,l,q}:X_t\in\Gamma_{y,l}\},\qquad
 C_{i,l,q+1}=\inf\{t>D_{i,l,q}:X_t\in\Gamma_{y,l-1}\},
\]
and put
\[
 T_{y,l}^{1,m_0}=\sum_{i=1}^{m_0}
             \#\{q:D_{i,l,q}<B_{y,i}\}.                   \tag{32c}
\]
Thus Rosen's abbreviation is exactly
\(T_{y,l}^{\,1}=T_{y,l}^{1,x_*^2}\), not a count in one source
excursion.  The strong Markov property and logarithmic gambler's ruin
make \((T_{y,1+j}^{1,m_0})_{j\ge0}\) a critical Galton--Watson chain
with \(m_0\) ancestors and offspring law
\(P(\xi=r)=2^{-r-1}\), \(r\ge0\).

Define \(\widehat I_{y,z}\) by
\[
 \sqrt{2T_{y,l}^{1,m_0}}\le\alpha_{z,-}(l),\quad1\le l<L,
 \qquad \sqrt{2T_{y,L}^{1,m_0}}\ge\rho_LL+z.                \tag{32}
\]
For the outward excursions at scale \(k\), let \(\theta_{k,i}\) be their
angular increments and let \(\nu_k\) be the exit-angle law from radius
\(r_k\) to \(r_{k-1}\).  If
\[
 N_{k,a}=\left\lfloor\frac{(\rho_Lk+z-a+1)^2}{2}\right\rfloor,
\]
 set \(N_k=N_{k,a}\) on
\(\sqrt{2T_{y,k}^{1,m_0}}\in[\rho_Lk+z-a,\rho_Lk+z-a+1]\), and
\[
 W_{y,k}(N_k)=\left\{
 d_{W^1}\left(N_k^{-1}\sum_{i\le N_k}\delta_{\theta_{k,i}},
                 \nu_k\right)
 \le\frac{c_0\log(L-k)}{2\sqrt{N_k}}\right\}.               \tag{33}
\]
With \(L^+=L-(500\log L)^4\) and Rosen's fixed \(d_*\), the event is
\[
       I_{y,z}=\widehat I_{y,z}
          \cap\bigcap_{k=L^+}^{L-d_*}W_{y,k}(N_k).             \tag{34}
\]
Rosen Lemmas 3.3--3.4 state completely that, uniformly for
\(0\le z\le\log L\),
\[
 P(I_{y,z})\asymp(1+z)e^{-2L}e^{-2z},                         \tag{35}
\]
and, for a pair in separation class \(k\),
\[
 P(I_{y,z}\cap I_{y',z})
 \le C(1+z)e^{-4L+2k}e^{-2z}
       e^{-c(k\wedge(L-k))^{1/4}}.                            \tag{36}
\]
The convention for \(L-d_*\le k<L\) is the one-center bound from that
lemma.  Fix \(z_0\) in Rosen's admissible range.  After imposing the
source-safety event below we will choose a fixed \(C_*\) and use the
truncated events
\[
 I_{y}^{\circ}:=I_{y,z_0}\cap
 \{\rho_LL+z_0\le\sqrt{2T_{y,L}^{1,m_0}}
                         \le\rho_LL+z_0+C_*\}                \tag{37}
\]
The notation in (37) is provisional until \(C_*\) is chosen after
safety has been proved.  This order matters: because \(X\) was extended
after \(\tau\), the inequality
\(T_{y,L}^{1,m_0}\le T_{y,L}^{\tau}\) can fail before safety is imposed.

Finally we impose a source safety event without conditioning away a rare
later continuation.  Let \(S_y\) require every connector
\([B_{y,i},A_{y,i+1}]\), \(i<m_0\), to hit \(\Gamma_{y,1}\) before the
larger circle \(\Gamma_{y,-1}\).  In the centered logarithmic cylinder,
the unrestricted connector endpoint subdensity and the safely killed
one, relative to Haar measure, are respectively
\[
 q_\infty(u)={\sinh1\over\cosh1-\cos u},
\]
\[
 q_{\rm sf}(u)=\frac12+2\sum_{n\ge1}{\sinh n\over\sinh(2n)}\cos(nu)
 =\frac\pi2\sum_{k\in\mathbb Z}
       \operatorname {sech}\!\left({\pi\over2}(u+2\pi k)\right).
                                                                    \tag{38a}
\]
Both are continuous and strictly positive, so
\(\kappa_*:=\min_uq_{\rm sf}(u)/q_\infty(u)>0\).  Thus the safe
connector kernel dominates \(\kappa_*\) times the unrestricted kernel
pointwise.  Iterating the strong Markov factorization, with the whole
later path functional left in the last factor, gives
\[
 P(I_{y,z}\cap S_y)\ge\kappa_*^{m_0-1}P(I_{y,z}).           \tag{38b}
\]
This is finite-measure domination against the entire later functional,
not multiplication of marginal probabilities.  Before endpoint
truncation put
\[
 \widetilde Z_L^{\rm sf}:=\sum_{y\in F_L^0}{\bf1}_{I_{y,z_0}\cap S_y}.
\]
Equation (38b) preserves its first moment, whereas
\(I_{y,z_0}\cap S_y\subset I_{y,z_0}\) preserves the pair upper bound
(36).  Rosen's shell summation and Paley--Zygmund therefore give
\[
 E\widetilde Z_L^{\rm sf}\le C,\qquad
 P(\widetilde Z_L^{\rm sf}>0)\ge c_1>0.                   \tag{38c}
\]
Rosen chooses \(r_0\) so that \(4h(r_{-1})<r_*\).  Since
\(d(v,y)\le h_1/20\), there is a fixed \(\chi>0\) such that
\[
             B_d(y,h(r_{-1}))\subset B_d(v,r_*-\chi).       \tag{38d}
\]
Every source block and every connector on \(S_y\) lies in the left
side, hence ends before \(\tau\).  This is the exact stopped-source
certificate used in the coupling below.  In particular, on \(S_y\),
\[
                    T_{y,L}^{1,m_0}\le T_{y,L}^{\tau}.      \tag{38e}
\]
Rosen Theorem 1.6 has the complete upper-tail conclusion
\[
 P\left(\sup_y\sqrt{2T_{y,L}^{\tau}}\ge\rho_LL+z\right)
       \le C(1+z)e^{-2z},\qquad0\le z\le\log L.             \tag{38f}
\]
Choose \(C_*\) so large that the right side at \(z=z_0+C_*\)
is below \(c_1/2\), and now define \(I_y^\circ\) by (37).  Equations
(38c)--(38f) give, with
\[
 Z_L^{\rm sf}:=\sum_{y\in F_L^0}{\bf1}_{I_y^\circ\cap S_y},
\]
\[
 EZ_L^{\rm sf}\le C,\qquad P(Z_L^{\rm sf}>0)\ge c_1/2.       \tag{38}
\]
Thus (37) is now defined and (38) is the required safe count.

## proof

Equations (23)--(38) are either definitions or the cited results with
their source and parameter ranges exposed; the calculation following
(30) proves the additional central-band consequence (29) and (31a).
All the first- and second-moment assertions (35)--(38) remain in Rosen's
original spherical geometry.  In particular, we do **not** infer an
event-level Euclidean two-center theorem from Rosen's occupation-measure
argument in Section 8.  The next lemma instead maps the actual spherical
interfaces into the plane, so the spherical event and its pair law are
preserved exactly until the one-sided lattice coupling is made.

# lemma lem:smooth-interface-discretization

## statement

Fix \(\alpha\in(0,1)\).  Let
\((\Gamma_R^-,\Gamma_R^0,\Gamma_R^+)\) range over triples of
disjoint Jordan curves which, after translation, rotation, and scaling
by \(R^{-1}\), together with their tubular-coordinate charts, belong to
a bounded \(C^{4,\alpha}\) family.  Assume consecutive curves are
separated by distances comparable to \(R\), and that a specified
conformal coordinate sends each triple to three concentric logarithmic
levels.  The interfaces used below are circles or uniformly
Möbius-transformed circles, so this hypothesis entails no loss.

For a boundary function put
\[
 \|f\|_{4,R}:=\sum_{j=0}^4R^j\|\partial_\tau^jf\|_\infty
             +R^{4+\alpha}[\partial_\tau^4f]_\alpha .       \tag{39a}
\]
A lattice starting state is a directed edge whose endpoints lie on opposite
sides of \(\Gamma_R^0\); the lattice query starts from its post-crossing
endpoint and the Brownian query from the normal projection of that endpoint
onto \(\Gamma_R^0\).  The side of a vertex is determined by membership in
the bounded component of the complement (vertices lying on the curve are
assigned to the exterior).  Let \(Q_R^B\) be the Brownian selected-side
subprobability kernel, stopped at first contact with either competing curve,
and let \(Q_R^S\) be the lattice selected-side subprobability kernel, stopped
at the first directed edge whose endpoint-side indicators differ for one of
the two competing curves.  A tangency, or any intersection of an interpolated
edge whose two endpoints remain on the same side, is not a lattice crossing.
Write \(\pi_0,\pi_+\) for normal projection of the digital source
and selected target states.  For a function \(f\) on the selected target
curve and a function \(g\) on the middle curve, define the two differently
typed lifts by
\[
                 U_+f=f\circ\pi_+,
                 \qquad U_0g=g\circ\pi_0.
\]
Then, as an estimate for operators from functions on the selected target
curve to functions on the digital source-edge space,
\[
 \|Q_R^SU_+f-U_0(Q_R^Bf)\|_\infty
       \le CR^{-1}\|f\|_{4,R}.                              \tag{39b}
\]
If the Brownian side probability \(p_R=Q_R^B1\) is constant on the
middle curve and lies in \([c,1-c]\), then, uniformly in the starting
angle,
\[
       Q_R^S1=p_R(1+O(R^{-1}))                               \tag{39c}
\]
and the corresponding row-normalized angular kernels differ by
\(O(R^{-1})\) on \(C^4\) tests.

Consequently, let a chronological radial word consist of \(N\)
ordinary, center-concentric neighboring-interface side decisions at
scales \(R_i\ge M\).  The next queried triple may depend on the already
exposed radial prefix, but not on an unexposed angular mark.  For a fixed
word, let \(E_i\) be the directed-edge state space after its first \(i\)
letters and let \(K^S_{i,w_{i+1}}(e,de')\) be the subkernel realizing the
next prescribed side.  If \(p_i\) is the corresponding Brownian side
probability, then, for every current edge,
\[
 e^{-C/R_i}p_i\le K^S_{i,w_{i+1}}1(e)
          \le e^{C/R_i}p_i .                               \tag{39c'}
\]
After summing all compatible directed-edge refinements,
\[
 e^{-C\sum_iR_i^{-1}}P^B(w)
 \le P^S(w)\le
 e^{C\sum_iR_i^{-1}}P^B(w).                                 \tag{39d}
\]
The same inequality holds after integrating the initial edge against any
entrance law and after summing a disjoint family of complete words.  A
radial-prefix stopping rule is padded by cemetery letters of row mass one.
No assertion is made after conditioning on an edge list generated later by
the word.  Source-root and source-death letters are handled explicitly in
Lemma lem:buffered-transfer.

## proof

Let \(\Omega_R\) be the annulus between the two competing curves and let
\(u\) be the continuum Dirichlet solution with boundary data \(f\) on the
selected component and zero on the other.  Uniform rescaled boundary
regularity gives
\[
       \|D^ju\|_{L^\infty(\overline\Omega_R)}
       \le CR^{-j}\|f\|_{4,R},\qquad0\le j\le4.             \tag{39e}
\]
The compact rescaled family has a tubular radius \(\rho R\).  In a signed
normal chart \(\Phi(s,t)\), with \(t\ge0\) on \(\Omega_R\), choose fixed
numbers \(c_1,\ldots,c_5\) satisfying
\[
             \sum_{a=1}^5c_a(-a)^q=1,
             \qquad q=0,1,2,3,4,
\]
and, for \(-\rho R/5<t<0\), set
\[
 \widetilde u(\Phi(s,t))=\sum_{a=1}^5c_a u(\Phi(s,-at)).
\]
Do this in the two disjoint collars and retain \(\widetilde u=u\) on
\(\overline\Omega_R\).  The five matching identities make
\(\widetilde u\) a \(C^4\) continuation through the boundary, with the
same scaled derivative bounds as (39e).

Let \(\Omega_R\) be understood with the same vertex-side convention and set
\[
 T=\inf\{n\ge1:S_{n-1}\in\Omega_R,\ S_n\notin\Omega_R\}.
\]
Equivalently, \(T\) is the first side-changing directed edge across one of
the two competing components; same-side contacts of the interpolated edge
are ignored.  For \(n<T\), \(S_n\) lies in the open annulus or on its inner
boundary (with the exterior convention above); it cannot lie on the outer
boundary.  At an open-annulus point
\(\Delta\widetilde u(S_n)=\Delta u(S_n)=0\), while at an inner-boundary
lattice vertex the \(C^4\) matching and continuity from the annulus give
\[
 \Delta\widetilde u(S_n)
       =\lim_{\Omega_R\ni x\to S_n}\Delta u(x)=0.
\]
Thus Taylor expansion is legitimate on the full four-neighbor stencil and
its quadratic term vanishes in either case.  The linear and cubic terms
cancel by symmetry.
Thus
\[
 |(P-I)\widetilde u(S_n)|\le CR^{-4}\|f\|_{4,R},
             \qquad n<T.                                   \tag{39f}
\]
For large \(R\), the two boundary components are more than two lattice
spacings apart and each has tubular radius \(\rho R\).  Hence the exit edge
crosses exactly one component, its post-crossing endpoint is within one
lattice spacing of that component and has a unique normal projection.
Moreover \(T\) is no larger than the exit time of a fixed \(CR\)-disk
containing the annulus.  Optional stopping of
\(\lVert S_n-z_*\rVert^2-n\) gives \(ET\le CR^2\), so the accumulated
defect in (39f) is \(O(R^{-2})\|f\|_{4,R}\).  The terminal endpoint is
within one lattice unit of the uniquely crossed component; its value
under \(\widetilde u\) differs from the projected boundary payoff by
\(O(R^{-1})\|f\|_{4,R}\).  The post-crossing starting endpoint and its
projection onto \(\Gamma_R^0\) have the same error.  Optional stopping of
\(\widetilde u(S_{n\wedge T})\) minus its defect sum proves (39b).
Taking \(f=1\), using \(p_R\in[c,1-c]\), and dividing by the row mass
proves (39c).  Notice that the continuation is used only to make a
boundary-crossing stencil legal; harmonicity, or its boundary-continuity
consequence, is invoked only at a live vertex.

For completeness, the logarithmic annular probability behind (39c) is
also the following cited lattice estimate.  Hao--Li--Okada--Zheng,
*Favorite sites for simple random walk in two and more dimensions*,
paper_id HaoLiOkadaZheng2025, arXiv id 2409.00995, Lemma 2.1,
equation (2.5), states in full that, uniformly for
\(r<\lVert x\rVert<R\),
\[
 P_x(H_{\partial D(0,R)}<H_{\partial D(0,r)})
 ={\log(\lVert x\rVert/r)+O(r^{-1})\over\log(R/r)},
\]
and the complementary inner-hit probability is
\[
 P_x(H_{\partial D(0,r)}<H_{\partial D(0,R)})
 ={\log(R/\lVert x\rVert)+O(r^{-1})\over\log(R/r)}.
\]
At fixed logarithmic gaps the main terms are bounded away from zero.

Finally fix a prescribed radial word and let \(\nu_i^S\) be the finite
measure on its current directed-edge states after the first \(i\) letters,
with every earlier edge integrated out.  The radial prefix fixes the next
interface and prescribed side before the current edge is integrated.
Brownian conformal radial symmetry makes its row mass \(p_i\) independent
of the angular endpoint, while (39c') gives
\[
 e^{-C/R_i}p_i\|\nu_i^S\|
 \le\|\nu_i^SK^S_{i,w_{i+1}}\|
 \le e^{C/R_i}p_i\|\nu_i^S\|.                              \tag{39i'}
\]
Forward induction proves (39d).  This remains valid for an adaptive
exploration because the radial prefix determines its next query, and for a
stopped exploration after adjoining the absorbing cemetery state.  It is a
forward marginal comparison, not a conditional law given future entrance
points, and it never applies (39b) to a rare future indicator.

# lemma lem:buffered-transfer

## statement

Fix \(A,C_0<\infty\).  Choose \(h=h_J\) so that
\[
 {h\over\log J}\longrightarrow\infty,\qquad h=o(J),\qquad
 M=e^h,\qquad n=J-h+O(1).                                    \tag{39}
\]
For the lower comparison let \(v\) and \(r_*\) be Rosen's starting
point and outer stopping radius.  Fix stereographic coordinates \(\sigma\) with
\(\sigma(v)=0\), put \(R_*=2\tan(r_*/2)\), and dilate by
\(A_J=e^J/R_*\):
\[
                  \Psi_J=A_J\sigma .
\]
Thus the spherical stopped path becomes, up to an increasing time
change, planar Brownian motion started at zero and stopped on
\(\partial B(0,e^J)\).  For a spherical center \(y\), let \(\chi_y\) be
the rotated stereographic coordinate satisfying
\[
 \chi_y(y)=0,qquad |\chi_y(x)|=2\tan(d(x,y)/2).
\]
The lower-comparison physical interfaces are
\[
 \Gamma_{y,j}=\Psi_J\{x:|\chi_y(x)|=r_0e^{-j}\},
       \qquad-1\le j\le n.                                  \tag{39g}
\]
They are Euclidean circles, although their Euclidean centers need not be
the same.  In the conformal coordinate
\(\chi_y\circ\Psi_J^{-1}\), they are exactly the concentric logarithmic
levels used by Rosen.  Their physical scale is comparable to
\(e^{J-j}\); the \(O(1)\) choice in \(n=J-h+O(1)\) makes the deepest
scale comparable to \(M\).

The linearly interpolated lattice path identifies which smooth curve a
lattice edge crosses, but every probabilistic cut is made at an integer
edge-index stopping time.  If \(D_{y,j}\) is the bounded component inside
\(\Gamma_{y,j}\), then, for adjacent levels and after an outer hit
\(\eta_i\), set
\[
 \sigma_i=\inf\{n>\eta_i:S_{n-1}\notin D_{y,j},\ S_n\in D_{y,j}\},
\quad
 \eta_{i+1}=\inf\{n>\sigma_i:S_{n-1}\in D_{y,j-1},\
                                  S_n\notin D_{y,j-1}\}.   \tag{39h}
\]
A state records the directed crossing edge; interpolation is used only to
assign its projected \(\chi_y\)-angle.
Only portions belonging to the first \(m_0\) source intervals
\([A_{y,i},B_{y,i}]\) in (32b) contribute traversal counts or terminal
bridges.  Inter-source connectors contribute only their guarded coarse
boundary decisions, never their interior occupation.  The whole segment
from \(\sigma_i\) to \(\eta_{i+1}\), including further contacts with the
inner interface, is one outward piece.  Recursing inside each parent
excursion gives the standard nested excursion tree.  The lower
**radial word** \(W_y=(W_{y,1},\ldots,W_{y,m_0})\) is a fixed collection
of \(m_0\) centered words, one for each source interval, with all angles
erased; the complete guard record additionally contains the finitely many
connector boundary decisions.  If
\(\ell_{y,i}\in\{1,-1\}\) records whether the connector after
\(B_{y,i}\) first hits \(\Gamma_{y,1}\) or \(\Gamma_{y,-1}\), write
\[
 \overline W_y=(W_{y,1},\ell_{y,1},W_{y,2},\ldots,
                 \ell_{y,m_0-1},W_{y,m_0})                 \tag{39h'}
\]
for the complete conditioned guard word.  Its traversal coordinate
\(T^S_{y,j}\) is the sum over these
words of completed crossings from \(\Gamma_{y,j-1}\) to
\(\Gamma_{y,j}\).  At the last
fixed number of levels, the interfaces are replaced through one
unit-width digital collar by concentric circles about the nearest lattice
point to \(\Psi_J(y)\), of radii \(M_y,eM_y\) with
\(M_y\in[cM,CM]\).  We relabel \(M_y\) as \(M\); every later estimate is
uniform under this fixed-factor change and \(\log M_y=h+O(1)\).
Define \({\cal R}_y\) by the chronological erasure map which replaces each
completed terminal segment, from its inward directed crossing of radius
\(M\) through its next outward directed crossing of radius \(eM\), by the
two endpoint edges.  It retains \(\overline W_y\), all radial letters and
all crossing edges and projected angles outside the erased segments, but
it does not retain an erased segment's duration, interior crossings, path,
or occupation.  Inward connector pieces outside these erased segments are
exposed.  This quotient sigma-field is the intrinsic coarse sigma-field.

The upper application is instead defined directly on the lattice and is
entirely centered.  Write \(N=e^J\), \(\tau_N=\tau_{D(0,N)}\), and, for
each candidate cell center with \(\|y\|<2N\), set
\[
                  \sigma_y=\tau_{D(y,3N)}.                  \tag{39k}
\]
The pathwise inclusions
\[
 D(0,N)\subset D(y,3N),\qquad \tau_N\le\sigma_y,
 \qquad L_{\tau_N}(x)\le L_{\sigma_y}(x)                  \tag{39l}
\]
hold for every \(x\).  For each one-cell probability we decompose the
extended path up to \(\sigma_y\) using only circles centered at \(y\),
and sum those probabilities only afterwards.  Replacing \(N\) by \(3N\)
changes every logarithmic index by \(O(1)\).  Use Rosen's formal horizon
\(J\), its barrier \(\rho_Jj+z+(j\wedge(J-j))^{1/4}\), and retain only
interfaces through \(n\).  Let \({\cal U}_{J,s}\) be the union of these
centered lattice upper first-crossing events, with source shell at least
\(s\), and let
\({\cal G}^{S,J}_{y,n,z}\) be the corresponding no-crossing event through
\(n-1\), and put
\[
       B_n^J=\rho_Jn+z+(n\wedge(J-n))^{1/4}.
\]
On the detailed range \(\|y\|>M\), its exact source index is
\[
 u_y=\log {3e^J\over\|y\|},\qquad
 k_y=\lceil u_y\rceil,qquad m_y=k_y+1;                    \tag{39m}
\]
centers with \(\|y\|\le M\) belong to the separately treated near-start
range.  Thus \(u_y\in(k_y-1,k_y]\) and \(m_y-u_y\in[1,2)\).
For the lower application relabel the numerical depth \(n\) as \(L\),
use the genuine horizon-\(L\) quantities \(\rho_L,l_L\), and let
\(I_y^{S,\circ}\) be the **radial** lattice version of (37): it retains
the traversal barrier and the bounded terminal band but drops every
angular screen.  Angular screens are used only in the spherical
Brownian certificate that supplies the second moment.  Then
\[
 P({\cal U}_{J,s})\le J^{-2s/\log J+o(1)}+O(J^{-A}),          \tag{40}
\]
\[
 P\big({\cal G}^{S,J}_{y,n,z},
       \sqrt{2T^S_{y,n}}\in[a,a+1]\big)
 \le C(k_y+1)^C(2+B_n^J-a)n^{-2}e^{-a^2/(2n)},
                                                                    \tag{41}
\]
uniformly for \(k_y\le C_0\log J\) and every fixed central range
\(\epsilon_0n\le a\le B_n^J+1\).  No such assertion is made in the
extinction range \(a<\epsilon_0n\).  Most importantly, if
\[
       Z_L^S=\sum_{y\in F_L^0}{\bf1}_{I_y^{S,\circ}},
\]
then
\[
       EZ_L^S\le C,\qquad P(Z_L^S>0)\ge c.                   \tag{42}
\]
Only the Brownian proof of (42) uses the two-center estimate (36).
No two-center lattice estimate is claimed or used.

## proof

There are two logically separate comparisons.  Rare upper and endpoint
events are compared directly, word by word, using Lemma
lem:smooth-interface-discretization.  The global strong coupling is used
only in the safe direction ``strict Brownian lower root implies loose
lattice lower root.''  At no point is a Brownian bad-subkernel estimate
multiplied by an arbitrary future functional of the coupled lattice path.
In the geometric estimates below \(L\) denotes the numerical depth \(n\);
the superscript \(J\) records when the upper barrier retains the larger
formal horizon \(J\).

First note that the geometry in the statement is exact.  Stereographic
projection is conformal and sends spherical Brownian motion to planar
Brownian motion under a continuous increasing time change.  Moreover,
by the definition of \(\chi_y\),
\[
 \Psi_J\bigl(\partial B_d(y,h(r_0e^{-j}))\bigr)
       =\Gamma_{y,j}.
\]
Thus hitting orders, the complete nested excursion tree, all traversal
counts, and all \(\chi_y\)-angular marks are literally Rosen's spherical
objects.  In particular, (36) will be applied only before any lattice
comparison.

For the strong approximation we use Zaitsev, Estimates for the Strong
Approximation in Multidimensional Central Limit Theorem,
paper_id Zaitsev2003StrongApproximation, arXiv id math/0304373,
Theorem 2 and Corollary 1.  The complete result used is: for fixed
dimension \(d\), centered independent vectors with identity covariance
whose laws lie in the analytic finite-exponential-moment class
\({\cal A}_d(\tau)\), one can couple them with independent standard
Gaussian vectors so that, for
\(\Delta_N=\max_{k\le N}\lVert\sum_{i\le k}(X_i-Y_i)\rVert\),
\[
 E\exp\{c\Delta_N/(\tau d^{7/2}\log^*d)\}
 \le \exp\{C d^{9/4+\alpha}\log^*N/\tau^2\},
\]
and hence
\[
 P(\Delta_N>C\log N+x)\le C e^{-cx},\qquad x\ge0,             \tag{30}
\]
for a fixed iid law.  The planar walk increment multiplied by \(\sqrt2\)
has identity covariance and bounded support, so the hypotheses apply.

Take the deterministic time cap
\[
       T_J=e^{2J}J^{20}.
\]
Lemma lem:elementary-walk-estimates and its Brownian analogue show that
the walk or Brownian motion remains inside the outer disk beyond \(T_J\)
with probability \(e^{-cJ^{10}}\).  By (30), after changing Brownian time
by the covariance factor \(1/2\), there is a coupling for which
\[
       \sup_{t\le T_J}\lVert S^{\rm lin}_{2t}-B_t\rVert
       \le b_J:=CJ^8                                         \tag{31}
\]
except on an event of probability \(e^{-cJ^8}\).  Brownian interpolation
between integer times has a smaller Gaussian error.

The crossing convention is an intrinsic deterministic function of the
finite lattice path.  For a curve with bounded component \(D\), a lattice
crossing is recorded exactly when
\(\mathbf1_{\{S_{n-1}\in D\}}\ne\mathbf1_{\{S_n\in D\}}\); a curve vertex
is assigned to the exterior, and same-side tangencies or chord contacts are
ignored.  The crossing angle is the normal projection of the post-crossing
endpoint.  At all used scales the endpoint lies in the uniform tubular
collar, so this projection is unique.  On the compact family of
centers under consideration, the maps \(\chi_y\circ\Psi_J^{-1}\) and
their inverses have uniformly bounded scaled first two derivatives.
Consequently, if two physical paths are within \(b\), then every
crossing of a nominal interface by one path is sandwiched between the
crossings by the other path of the two interfaces obtained by changing
its \(\log|\chi_y|\)-level by \(Cb/R\), where \(R\) is the physical
scale.  This is just the deterministic inclusion of the two
\(b\)-neighborhoods of a smooth separating curve; applying it
successively preserves chronological order.
The crossed directed edge retains the digital-boundary overshoot, which
costs at most two extra lattice units.  Thus
the only difference between the nominal Brownian word and the lattice
word comes from collars of relative logarithmic width
\[
       \delta_J=C\frac{b_J+1}{M}=O\left(\frac{J^8}{M}\right). \tag{33}
\]

For the lower comparison we need only the radial word.  We now define
all stopping lines and guards.  Work in the centered cylinder coordinate
\[
 U_t=-\log\bigl(|\chi_y(X_t)|/r_0\bigr),
\]
after its conformal time change, so that \(U\) is one-dimensional Brownian
motion and \(\Gamma_{y,j}=\{U=j\}\).  For a stopping time \(s\), write
\(H_a[s]=\inf\{t\ge s:U_t=a\}\), with \(\inf\varnothing=\infty\).  Put
\[
             \eta_J=8\delta_J,\qquad N_0=J^4,                \tag{R1}
\]
and take \(J\) large enough that \(0<\delta_J<\eta_J/4\) and
\(\eta_J\le1/4\).

Here is the finite depth-\(L\) word belonging to (32b).  From
\(S_{i,0}=A_{y,i}\), \(K_{i,0}=1\), recursively set, when \(K_{i,r}<L\),
\[
 S_{i,r+1}=\inf\{t>S_{i,r}:U_t\in
             \{K_{i,r}-1,K_{i,r}+1\}\},\qquad
 K_{i,r+1}=U_{S_{i,r+1}}.
\]
When \(K_{i,r}=L\), instead set
\[
 S_{i,r+1}=H_{L-1}[S_{i,r}],\qquad K_{i,r+1}=L-1;            \tag{R1a}
\]
this is a forced terminal return, and the motion below \(\Gamma_{y,L}\)
is deliberately not resolved.  Stop at
\(N_i=\inf\{r\ge1:K_{i,r}=0\}\), so \(B_{y,i}=S_{i,N_i}\).
For \(i<m_0\) put
\[
 C_i=\inf\{t>B_{y,i}:U_t\in\{-1,1\}\}.
\]
On \(S_y\), \(U_{C_i}=1\), \(C_i=A_{y,i+1}\), and the connector is the
single prescribed sign \(0\to1\).  Concatenating the \(m_0\) block words
and these \(m_0-1\) connector signs gives exactly \(\overline W_y\) in
(39h').  A block letter \(j-1\to j\) pushes the next Ulam--Harris child,
a letter \(j\to j-1\) pops it, and (R1a) closes a terminal leaf.  Hence
\[
 T_{y,1}^{1,m_0}=m_0,\qquad
 T_{y,j}^{1,m_0}=\#\{j-1\to j\hbox{ block letters}\},
                  \quad2\le j\le L.                        \tag{R1b}
\]
All these times are recursively defined hitting times of closed sets;
the completed \(m_0\)-block word and the cap \(|\overline W_y|\le N_0\)
are therefore stopping-line measurable.

We next define the guards.  Consider first a competitive letter beginning
at a stopping time \(s\), at level \(k<L\), whose prescribed sign is
\(\epsilon\in\{-1,1\}\).  Its end is
\[
 t=\inf\{u>s:U_u\in\{k-1,k+1\}\},\qquad U_t=k+\epsilon.
\]
Define
\[
\begin{array}{lll}
 p=H_{k+\epsilon(1-\eta_J)}[s],
 &w=H_{k-\epsilon(1-\eta_J)}[s],
 &r=H_{k+\epsilon\eta_J}[p],\\
 e=H_{k+\epsilon(1+\eta_J)}[t],
 &o=H_{k+\epsilon\eta_J}[t].
\end{array}
\]
The bad events for this letter are
\[
 D^{\rm wrong}=\{w<t\},\qquad
 D^{\rm ret}=\{r<t\},\qquad
 D^{\rm post}=\{o<e\}.                                    \tag{R2}
\]
The last comparison is with the old-side collar
\(k+\epsilon\eta_J\), not merely with the old nominal line \(k\).
For a forced terminal return \(L\to L-1\) beginning at \(s\), set
\[
 t=H_{L-1}[s],\quad p=H_{L-1+\eta_J}[s],\quad
 r=H_{L-\eta_J}[p],\quad
 e=H_{L-1-\eta_J}[t],\quad o=H_{L-\eta_J}[t],
\]
and use \(D^{\rm ret}=\{r<t\}\) and
\(D^{\rm post}=\{o<e\}\).  There is no wrong-side guard because the
path below level \(L\) is not resolved.

The first source opening needs its own two guards.  The fixed source
annulus in (32a) gives a uniform initial margin.  Indeed,
\(d(v,y)\le h_1/20\), convexity of \(\tan\) on the relevant fixed small
interval, and \(r_1=r_0e^{-1}\) imply
\[
 |\chi_y(v)|=2\tan\!\left(\frac{d(v,y)}2\right)
 \le 2\tan\!\left(\frac{h_1}{40}\right)
 \le \frac{r_1}{20},
 \qquad U_0\ge1+\log20.
\]
(The lower annulus bound keeps \(U_0\) finite.)  Thus, with
\(c_{\rm src}:=\log20\), one has \(U_0\ge1+c_{\rm src}\), and for
\(\eta_J<c_{\rm src}\) the stopping time
\(c_1=H_{1+\eta_J}[0]\) satisfies \(c_1<A_{y,1}\).  Since the first
opening approaches level \(1\) from the inner side, define
\[
 D^{A_1,{\rm pre}}=\{H_{2-\eta_J}[c_1]<A_{y,1}\},\qquad
 D^{A_1,{\rm post}}=
 \{H_{2-\eta_J}[A_{y,1}]<H_{1-\eta_J}[A_{y,1}]\}.           \tag{R2a}
\]
For \(i\ge2\), the pre-opening guard at \(A_{y,i}\) is exactly
\(D^{\rm ret}\) for connector \(i-1\), and its post-opening guard is
exactly \(D^{\rm post}\) for that connector; they are named both ways
but counted once.  At every \(B_{y,i}\), the last block symbol is the
competitive closing letter \(1\to0\); its wrong, retreat, and post events
in (R2) are respectively the pre-closing and closing-recognition guards.
For \(i<m_0\) the following symbol is the connector \(0\to1\).  At the
last close \(B_{y,m_0}\), retain its post-guard and expose it without any
following letter.  Let \(D_y\) be the union of these events through the
last post-closing collar hit.  Every member of this union has the form
\(\{H_a[S]<H_b[S]\}\) for a named stopping time \(S\), so \(D_y\) is
measurable at that finite stopping line.

We record the exact conditional ratios.  Fix an admissible complete word
\(w\).  Translation, reflection, gambler's ruin, and strong Markov at the
integer-line hits give, for every competitive letter,
\[
 \frac{P(D^{\rm wrong},\overline W_y=w)}{P(\overline W_y=w)}
       =\frac{\eta_J}{2-\eta_J},\qquad
 \frac{P(D^{\rm ret},\overline W_y=w)}{P(\overline W_y=w)}
       =\frac{\eta_J(1+\eta_J)}
          {(1-\eta_J)(2-\eta_J)}.                           \tag{R2b}
\]
If the next symbol is competitive, then
\[
 \frac{P(D^{\rm post},\overline W_y=w)}{P(\overline W_y=w)}
 =\begin{cases}
    \eta_J^2,&\text{if the next sign continues the present direction},\\
    2\eta_J-\eta_J^2,&\text{if it reverses it}.
   \end{cases}                                               \tag{R2c}
\]
Indeed, after translating the new level to \(1\),
\(P_1(H_{\eta_J}<H_{1+\eta_J})=\eta_J\); from \(\eta_J\), the
probabilities of the next exits at \(2\) and \(0\) are respectively
\(\eta_J/2\) and \(1-\eta_J/2\), while either prescribed next sign has
probability \(1/2\).  If the successor is the forced return in (R1a), or
there is no successor, the post ratio is simply \(\eta_J\).  For a forced
return \(L\to L-1\),
\[
 \frac{P(D^{\rm ret},\overline W_y=w)}{P(\overline W_y=w)}
       =\frac{\eta_J}{1-\eta_J}.                            \tag{R2d}
\]
The first-opening pre ratio in (R2a) is also
\(\eta_J/(1-\eta_J)\).  If \(d_1=-1\) is its crossing direction and
\(\epsilon_1\) is the first block sign, its post ratio is
\(\eta_J^2\) when \(\epsilon_1=d_1\), and
\(2\eta_J-\eta_J^2\) otherwise.  The same table applies at every later
opening through its incoming connector.  In particular, at \(B_{y,i}\),
\(i<m_0\), the close has direction \(-1\) and the next connector has sign
\(+1\), so its post ratio is \(2\eta_J-\eta_J^2\).  At the final close
\(B_{y,m_0}\) it is exactly \(\eta_J\), with no fictitious next sign.
All later letters cancel by strong Markov; no arbitrary angular or future
functional is being inserted into these ratios.  A union bound, without
any independence assertion among guards, gives
\[
 P(D_y\mid\overline W_y=w)
 \le8(|w|+2m_0+1)\eta_J
 \le\varepsilon_J,
 \qquad \varepsilon_J:=CJ^4\delta_J=o(J^{-A})               \tag{R3}
\]
for every \(|w|\le N_0\) and every fixed \(A\).  The estimate remains
valid after conditioning on barriers, traversal counts, or any other
function of \(w\), but is not claimed after conditioning on Rosen's
angular screens.

For completeness, here is the deterministic implication used below.  Let
\(\mathcal A_J\) be the finite set of all nominal integer levels and all
guard-collar levels occurring in (R2)--(R2a), including the forced-return
collars.  Let \(V\) be the corresponding log-radius of the linearly
interpolated lattice path, in the coupling time parametrization.  Its
nominal source blocks and truncated word are defined at integer edge indices
by the endpoint-side-change convention above: a letter is recorded only
when an edge's endpoints change sides, and interpolation along such an edge
is used only to locate its crossing and evaluate collar separation.
Same-side tangencies and chord contacts record no letter.  Assume the
following symmetric collar condition: whenever either \(U_t\) or \(V_t\) is
within \(2\delta_J\) of \(\mathcal A_J\), both log-radii are finite and
\(|U_t-V_t|\le\delta_J\).  No comparison is required while both paths lie
strictly on the unresolved inner side of the deepest collars.  Suppose \(S_y\),
\(|\overline W_y|\le N_0\), and \(D_y^c\) occur.  Before the target collar
of a competitive Brownian letter, \(V\) cannot make a side-changing crossing
of the target nominal line, while \(D^{{\rm wrong},c}\) prevents it from hitting the other
neighbor.  From the first target-collar hit until the nominal target,
\(D^{{\rm ret},c}\) keeps \(U\) beyond the old-side collar; hence an early
side-changing target crossing by \(V\) cannot be followed by a reversal.  From the nominal
hit to the far collar, \(D^{{\rm post},c}\) gives the same separation,
and at the far collar
\[
 \epsilon\bigl(V-(k+\epsilon)\bigr)
       \ge\eta_J-\delta_J>0.
\]
Thus \(V\)'s next nominal neighboring line is exactly \(k+\epsilon\),
and it has made no intervening push or pop.  The forced return (R1a) uses
the retreat and post guards only; deeper visits are ignored by both
truncated words.

At \(A_{y,1}\), (R2a) first prevents a premature completed neighboring
letter and then forces \(V\) across the source line.  The preceding
letter argument initializes every later \(A_{y,i}\) through its connector.
Induction in chronological order on the active Ulam--Harris stack now
gives the same push/pop operation at every symbol.  At \(B_{y,i}\) the
same stack empties; for \(i<m_0\) the guarded connector has sign \(0\to1\)
and starts the next stack, while the unconditional final post-guard forces
\(V\) across level \(0\) at \(B_{y,m_0}\).  Hence the two stopped ordered
forests are canonically isomorphic and
\[
 T_{y,j}^{1,m_0}(V)=T_{y,j}^{1,m_0}(U),\qquad1\le j\le L.    \tag{R4}
\]
Moreover the exact word length is
\[
 |\overline W_y|=2\sum_{j=2}^{L}T_{y,j}^{1,m_0}+2m_0-1
       \le CL^3<N_0,                                       \tag{R4a}
\]
on the lower barrier and terminal band.  On the single global coupling
event (31), the symmetric collar condition holds.  Indeed, every
\(2\delta_J\)-neighborhood of a nominal or guard collar used by the
truncated word has physical radius at least \(cM\).  If either path is in
such a neighborhood, physical \(b_J\)-closeness, the radial Lipschitz
inequality, chart distortion, and the \(O(1)\) terminal-interface rounding
give
\[
              |U_t-V_t|\le C(b_J+1)/M\le\delta_J
\]
after fixing the constant in (33).  No log-radius comparison is asserted or
used while both paths are deeper than the terminal collars.  Source safety
keeps every collar test before global killing.  This condition suffices:
any premature target, wrong-neighbor, or reversal crossing occurs at a
member of \(\mathcal A_J\), where collar closeness and
\(\delta_J<\eta_J/4\) contradict the corresponding safe guard.  This also
covers a premature \(L-1\) hit during a forced \(L\to L-1\) return.
Consequently
\[
 I_y^{\circ}\cap S_y\cap D_y^c\cap\{\text{global coupling (31)}\}
       \subseteq I_y^{S,\circ}.                             \tag{R4b}
\]
Only the radial consequence is transferred: Rosen's original angular
screens remain solely on the Brownian certificate.

We first prove the rare upper statements without KMT.  Fix a target cell
and use the centered continuation (39k)--(39l).  Put
\[
 R_j=R_0e^{-j},\qquad R_0=3e^J,
\]
rounding every radius by at most two lattice units.  On the detailed-source
range \(\|y\|>M\), define from the actual starting radius
\[
 u_y=\log {R_0\over\|y\|},\qquad
 k_y=\lceil u_y\rceil,qquad m=k_y+1.                       \tag{45a0}
\]
Then \(u_y\in(k_y-1,k_y]\), \(m-u_y\in[1,2)\), and the
deterministic start lies outside \(D(y,R_{m-1})\).  This index differs by
only \(O(1)\) from \(\lfloor\log(e^J/\|y\|)\rfloor\), so it changes no
shell exponent.  Write
\[
\begin{split}
 E_j^{\rm in}&=\{(a,b):a\notin D(y,R_j),\ b\in D(y,R_j),\ a\sim b\},\\
 E_j^{\rm out}&=\{(a,b):a\in D(y,R_j),\ b\notin D(y,R_j),\ a\sim b\}.
\end{split}                                                \tag{45a1}
\]
Every radial query retains its phase, level, Ulam--Harris stack and child
counters, population vector, and current directed crossing edge.

Potential-kernel optional stopping, uniformly in that edge, gives for
\(k<l\)
\[
 q^S_{k,l}\le C{k+1\over l},\qquad
 p_l^S(e)={l-1+O(R_l^{-1})\over l+O(R_l^{-1})},\qquad
 d_l^S(e)={1+O(R_l^{-1})\over l+O(R_l^{-1})}.              \tag{45a}
\]
Here \(q^S_{k,l}\) includes the first completion at level \(l\), while
\(p_l^S\) and \(d_l^S=1-p_l^S\) are the continuation and death rows
after return to level \(l-1\).  Indeed, the two complete formulas from
Hao--Li--Okada--Zheng, paper_id HaoLiOkadaZheng2025, arXiv id
2409.00995, Lemma 2.1, equation (2.5), quoted in
Lemma lem:smooth-interface-discretization, have respective logarithmic
gaps \(l-1+O(R_l^{-1})\), \(1+O(R_l^{-1})\), and
\(l+O(R_l^{-1})\).  Thus both the continuation and the order-\(1/l\)
death probability are relative estimates.  Strong Markov at every
successive directed hit yields, for \(N\ge1\),
\[
 P(T_{y,l}^{S,k\to0}\ge N\mid\hbox{initial directed edge})
 \le C{k+1\over l}\exp\left\{-{N\over l}+{CN\over lM}\right\}.
                                                                  \tag{45b}
\]
In particular, for \(X=\sqrt{2T_{y,m}}\) and \(x\le Cm\),
\[
                  P(X\in[x,x+1])
       \le Cm^C e^{-x^2/(2m)}.                              \tag{45c}
\]
No independence of directed entrance edges is used in these scalar bounds.

Here is the deterministic representative construction used in the
first-crossing union bound.  Put
\[
       \phi(l)=\exp\{\tfrac14(l\wedge(J-l))^{1/4}\}.
\]
Fix constants
\[
       0<c_{\rm sep}\le c_{\rm mesh}<C_\delta<\frac{e-1}{e+1}.
\]
For each \(l\), choose a deterministic maximal
\(c_{\rm sep}R_l/\phi(l)\)-separated subset of \(\mathbb Z^2\), with
\(c_{\rm sep}\) chosen so that its covering radius (for lattice points) is
at most \(c_{\rm mesh}R_l/\phi(l)\).  Given a candidate lattice center
\(y\) in source shell \(k\), choose a mesh point
\(\widehat y=\widehat y(y,l)\in\mathbb Z^2\) with
\[
 |y-\widehat y|\le c_{\rm mesh}R_l/\phi(l),\qquad
 \delta_l=C_\delta/\phi(l),\qquad R_j^\pm=(1\pm\delta_l)R_j.
\]
For all sufficiently large \(J\), the gap
\((C_\delta-c_{\rm mesh})R_l/\phi(l)\) absorbs the at-most-two-unit
rounding of every radius on the used range.  Moreover
\(\delta_l<(e-1)/(e+1)\), and hence
\(R_{l-1}^->R_l^+\), so every buffered annulus below is nonempty.
Starting with the first entrance into
\(D(\widehat y,R_k^+)\), and stopping on exiting
\(D(\widehat y,R_0^+)\), let
\(\widetilde T_{\widehat y,l}^{S,k\to0}\) count completed crossings from
\(\partial D(\widehat y,R_{l-1}^-)\) to
\(\partial D(\widehat y,R_l^+)\).  The inclusions
\[
\begin{split}
 D(y,R_k)&\subset D(\widehat y,R_k^+),\\
 D(y,R_l)&\subset D(\widehat y,R_l^+),\\
 D(\widehat y,R_{l-1}^-)&\subset D(y,R_{l-1}),\\
 D(y,R_0)&\subset D(\widehat y,R_0^+)
\end{split}                                                \tag{45d0}
\]
show pathwise that
\[
                 T_{y,l}^{S,k\to0}
       \le\widetilde T_{\widehat y,l}^{S,k\to0}.             \tag{45d1}
\]
Indeed every \(y\)-crossing begins outside the representative's buffered
outer circle, ends inside its buffered inner circle, and occurs after the
representative start and before its stop.  The same inclusions cover
\(k=l-1\).  Area comparison for the mesh in a shell of diameter
\(O(R_k)\) gives, for every \(k\le l-1\),
\[
 \#\{\hbox{representatives at }(k,l)\}
 \le C e^{2(l-k)}\phi(l)^2.                                \tag{45d}
\]
The buffered inclusions in Rosen (2.26)--(2.33) do not impose
\(k\le\log J\).  For the four modified radii
\((R_k^+,R_{l-1}^-,R_l^+,R_0^+)\), the same potential-kernel
calculation gives, uniformly in all directed entrance edges,
\[
 \widetilde q_{k,l}^S\le C{k+1\over l},\qquad
 \widetilde p_l^S
 \le1-\frac{1-C/\phi(l)-C/M}{l}.                           \tag{45d2}
\]
Consequently (45b) holds with \(T\) replaced by
\(\widetilde T_{\widehat y,l}^{S,k\to0}\), the additional exponent being
\(CN/(l\phi(l))+CN/(lM)\).  Taking
\(N=\alpha_{z,+}(l)^2/2\) there gives
\[
 P(\widetilde T_{\widehat y,l}^{S,k\to0}\ge N)
 \le C e^{-2l-(l\wedge(J-l))^{1/4}}e^{-2z}.                \tag{45e}
\]
On the used range \(l\le J-(4\log J)^4\), the elementary exponent
calculation gives \(l/\phi(l)=O(1)\) (the bounded early values are
absorbed into \(C\)), and \(N/(lM)=o(1)\).  Multiplying (45d) and (45e)
and summing first in \(l\), then in \(k\ge s\), proves (40), including
the range \(\log J<k\le C_0\log J\).

For the endpoint estimate we compare the source and descendant history as
one chronological word before making any disintegration.  In addition to
the directed-edge/stack states in (45a1), introduce a special deterministic
initial atom \(\star_y\), representing \(S_0=0\).  The first query is
`ROOT' (hit \(D_m\) before leaving \(D_0\)), whose kernel maps
\(\star_y\) to \(E_m^{\rm in}\), or `FAILURE', whose kernel maps
\(\star_y\) to the cemetery state.  After every root, its descendants are
explored depth first: at an active node of level \(j<n\), `BIRTH' is the
first hit of \(D_{j+1}\) and pushes the next child, while `CLOSE' is the
first exit from \(D_{j-1}\) and pops the node.  A level-\(n\) leaf has a
forced return to level \(n-1\), of row mass one.  After a root closes, the
current state lies in \(E_{m-1}^{\rm out}\); the next source query is
another `ROOT', mapping to \(E_m^{\rm in}\), or the final `DEATH', mapping
through \(E_0^{\rm out}\) to the cemetery state.  Thus a word with
\(t\ge1\) roots has the
physical order
\[
 \mathtt{ROOT},\operatorname{DFS}(1),\mathtt{ROOT},
 \operatorname{DFS}(2),\ldots,\mathtt{ROOT},
 \operatorname{DFS}(t),\mathtt{DEATH}.                    \tag{45f0}
\]
The word stops at the first barrier violation, endpoint decision, death,
or a fixed deterministic cap \(Q_*=C_*J^3\), chosen above
\(3+2\sum_{j=m}^n(T_{y,j}+1)\) on the coefficient-two barrier,
and is then padded by cemetery letters.  It contains every terminating
close and the final source death, so there is no residual future condition.

Let \(P_*\) be the angle-free ideal law.  Its first root and failure
probabilities are \(u_y/m\) and \((m-u_y)/m\); subsequent root and death
probabilities are \((m-1)/m\) and \(1/m\); every descendant
birth/close decision has probability \(1/2\).  Potential-kernel optional
stopping, with every output edge summed but every current directed edge
retained, gives the four lattice source rows
\[
\begin{split}
 r_{0,y}^S
   &=\frac{u_y+O(R_m^{-1})}{m+O(R_m^{-1})},
 & f_{0,y}^S
   &=\frac{m-u_y+O(R_m^{-1})}{m+O(R_m^{-1})},\\
 r_m^S(e)
   &=\frac{m-1+O(R_m^{-1})}{m+O(R_m^{-1})},
 & d_m^S(e)
   &=\frac{1+O(R_m^{-1})}{m+O(R_m^{-1})}.
\end{split}                                                \tag{45f-src}
\]
Here the first pair starts from \(\star_y\), while the second pair is
uniform in \(e\in E_{m-1}^{\rm out}\).  Since every candidate satisfies
\(\|y\|<2e^J\),
\[
 u_y\ge\log(3/2),\qquad m-u_y\in[1,2),\qquad m-1\ge1.
\]
Also \(R_m=e^{u_y-m}\|y\|\ge e^{-2}\|y\|\ge e^{-2}M\) on the detailed
range.  Consequently each of the four displayed rows, including the two
order-\(1/m\) FAILURE and DEATH rows, equals its ideal row times
\(1+O(M^{-1})\).  Ordinary birth/close rows are
\((1/2)(1+O(R_{j+1}^{-1}))\).

Fix a complete radial word \(w\), but no directed-edge refinement.  If
\(\nu_r\) is the edge-valued finite measure after its first \(r\) letters,
the next ideal row \(p_r\) is determined by the radial prefix, and the
uniform row estimates give
\[
 e^{-C/M}p_r\|\nu_r\|\le\|\nu_{r+1}\|
       \le e^{C/M}p_r\|\nu_r\|.
\]
Forward induction, with all compatible entrance and exit edges integrated,
therefore gives
\[
 e^{-C|w|/M}P_*(w)\le P_S(w)
       \le e^{C|w|/M}P_*(w).                               \tag{45f}
\]
This is not a conditional comparison given a future edge list.

Under \(P_*\), the source population has the exact law
\[
 \pi_{m,u_y}(0)=1-{u_y\over m},\qquad
 \pi_{m,u_y}(t)={u_y\over m}
       \left({m-1\over m}\right)^{t-1}{1\over m},
       \quad t\ge1,                                       \tag{45g0}
\]
and, conditional on \(t\), the \(t\) descendant trees are independent
critical Galton--Watson trees with
\(P(\xi=r)=2^{-r-1}\).  Hence, for the disjoint union
\(\mathscr U(q)\) of complete barrier-respecting words ending in
\(\sqrt{2T_n}\in[q,q+1]\),
\[
 P_S(\mathscr U(q))
 \le e^{CJ^3/M}\sum_{t\ge1}\pi_{m,u_y}(t)
       P_t^{\rm GW}(\mathscr A_t^{\rm GW}(q)).             \tag{45g}
\]
Only the ideal law on the right has been disintegrated.  Moreover, for
\(x\le Cm\),
\[
 \sum_{\sqrt{2t}\in[x,x+1]}\pi_{m,u_y}(t)
 \le C(1+x)m^{-1}e^{-x^2/(2m)+O(1)}
 \le Ce^{-x^2/(2m)}.                                      \tag{45g'}
\]
Apply Rosen Appendix Theorem 9.1(a), quoted completely in (30), to the
ideal Galton--Watson factor in (45g), group \(\sqrt{2t}\) into unit bands,
and use (31)--(31a).  This proves (41).  The \(t=1\) term is covered by
the extra-ancestor argument following (30), while \(t=0\) cannot reach a
positive central endpoint.  Since \(J^3/M=o(J^{-A})\), the comparison is
relative even for the rare endpoint event.

It remains to prove the lower count.  We retain Rosen's original event
\(I_y^\circ\) and its original angular screens exactly as written in
(33)--(37), and intersect it with the source-safety event \(S_y\).
No tightened or halved screen is used.  Put
\(I_y^{\rm sf}=I_y^\circ\cap S_y\).  By (38),
\[
 P\left(\sum_y1_{I_y^{\rm sf}}>0\right)\ge c_* .            \tag{46}
\]
The screens occur only in this Brownian second-moment certificate; the
lattice target discards all angular screens.

Let \(\widehat I_y^B\) be the Brownian event obtained from
\(I_y^\circ\) by deleting every angular screen and retaining only the
radial barrier, the bounded endpoint band, and the fixed \(m_0\)-source
definition.  Rosen Appendix Theorem 9.1(a), followed by the same source
and barrier calculation as (29), gives
\[
             P(\widehat I_y^B)\le Ce^{-2L},
             \qquad \sum_yP(\widehat I_y^B)\le C.           \tag{47}
\]
Since
\(I_y^{\rm sf}\cap D_y\subseteq
  \widehat I_y^B\cap S_y\cap D_y\), estimate (R3) may be summed over
complete safe radial words before any angular screen is imposed.  Hence
\[
 \sum_yP(I_y^{\rm sf}\cap D_y)
 \le\varepsilon_J\sum_yP(\widehat I_y^B\cap S_y)
 \le\varepsilon_J\sum_yP(\widehat I_y^B)=o(1).              \tag{47a}
\]
Let \({\cal K}_J\) be the single global coupling/time-cap event (31).
The pathwise implication (R4b) gives
\[
 \{Z_L^{\rm sf}>0\}\cap{\cal K}_J
       \setminus\bigcup_y(I_y^{\rm sf}\cap D_y)
       \subseteq\{Z_L^S>0\}.
\]
Consequently, paying the coupling failure only once,
\[
 P(Z_L^S>0)\ge P(Z_L^{\rm sf}>0)
   -\sum_yP(I_y^{\rm sf}\cap D_y)-P({\cal K}_J^c)
 \ge c_*-o(1).                                               \tag{47b}
\]
Source safety and (38d) keep every block, connector, and final exposed
post-closing collar a fixed positive distance inside the stopping boundary,
so the close lattice path is not killed before the transferred blocks
finish.  No Brownian angular screen is transferred.
This is the only use of the two-center estimate (36), and it occurs
entirely on the spherical Brownian side.

For the lattice first moment, extend the path if necessary and decompose
its first \(m_0\) source blocks, treating every connector as an integrated
subkernel of row mass at most one.  For a fixed collection of block words,
apply the edge-marginal induction (39i') to all competitive letters,
uniformly over the entrance law supplied by each preceding connector.
Forced terminal returns have row mass one.  Thus, if \(q\) is the number
of competitive decisions,
\[
 P_S(\hbox{these block words})\le e^{CJ^3/M}2^{-q}.
\]
Summing the disjoint words obeying the lower barrier and terminal band gives
the critical geometric Galton--Watson probability with exactly \(m_0\)
ancestors.  Rosen Appendix Theorem 9.1(a), followed by the fixed-source
calculation already used in (47), gives
\[
       P(I_y^{S,\circ})\le Ce^{-2L},\qquad EZ_L^S\le C.      \tag{47c'}
\]
This proves (42); in particular, the lower first moment does not use the
upper source-population estimate (45c).

Finally we justify the terminal switch used in the definition of
\({\cal R}_y\).  On the compact center family, with
\(F_y=\sigma\circ\chi_y^{-1}\),
\[
 F_y(w)=F_y(0)+a_yw+b_yw^2+O(|w|^3),
       \qquad0<c\le|a_y|\le C.
\]
At \(r_L\asymp e^{-J+h}\), dilation by \(A_J\asymp e^J\) shows that
the actual deepest image circle is at Hausdorff distance
\[
       O(A_Jr_L^2)=O(e^{-J+2h})=o(1)                         \tag{47c}
\]
from its affine concentric circle.  Rounding the center and the digital
boundary costs \(O(1)\), or relative width \(O(M^{-1})\), and is one
additional collar in the lower guard construction (R1)--(R4).  The induced
angular conjugacy, after removing the fixed rotation
\(a_y/|a_y|\), is \(C^4\)-close to the identity by
\(O(e^{-J+h})\); its Haar-density defect is therefore absorbed by
\(M^{-7/24}\log M+M^{-1}\).  Thus the outer \(\chi_y\)-rotation kernels
and the terminal Euclidean rotation kernels use the same common center
up to the stated error.  All lattice
events were defined before introducing the auxiliary coupling and are
measurable in \({\cal R}_y\).  We may therefore discard the Brownian
path after (47b); every later conditional law is the original
simple-random-walk law given \({\cal R}_y\).

# lemma lem:typed-centered-endpoint-product

## statement

Let \(D=D(y,eM)\), let \(A\) be the inner vertex boundary of
\(D(y,M)\), and let \(E\) be the directed edges leaving \(D\).  Put
\[
 H^S(a,e)=P_a((S_{\tau_D-1},S_{\tau_D})=e),\qquad
 ({\cal H}^Sf)(a)=\sum_eH^S(a,e)f(a,e).
\]
Let \(G^S=G_D\).  For \(x,x'\in V:=D(y,M/2)\), define on
\(A\times E\)
\[
 m_x(a,e)={G^S(a,x)H^S(x,e)\over H^S(a,e)},
\]
\[
 q_{x,x'}(a,e)=
 {G^S(a,x)G^S(x,x')H^S(x',e)
  +G^S(a,x')G^S(x',x)H^S(x,e)
  -\mathbf1_{\{x=x'\}}G^S(a,x)H^S(x,e)\over H^S(a,e)},
\]
and let
\[
 {\cal F}_M^{\rm G}={m_x/C:x\in V\}\cup
 \{q_{x,x'}/[C(1+G^S(x,x'))]:x,x'\in V\},               \tag{TP0}
\]
where the fixed \(C\) is large enough that all functions have sup norm
at most one.
Let \(R_i^S(e,da')\) be a fixed radial-only centered return word from a
previous exit edge to the next inward entrance, let
\(\sigma_i=R_i^S1\), \(J_i^S=R_i^S/\sigma_i\), and set
\[
 P_i^S((a,e),d(a',e'))=J_i^S(e,da')H^S(a',de').           \tag{TP1}
\]
The word may be selected adaptively from its radial prefix, but not from an
angular endpoint.  If it contains \(q_i\) elementary letters, all at scales
at least \(M\), and \(\lambda_A^S\) is the center-to-\(A\) first-hit law,
put \(\Lambda^S=\lambda_A^SH^S\).  For \(f\in{\cal F}_M^{\rm G}\) and
every consecutive portion \(r\le s\) of
one centered block,
\[
 \left|\Lambda^SP_r^S\cdots P_s^Sf-\Lambda^Sf\right|
 \le C\left\{M^{-7/24}\log M+{1\over M}
                   \sum_{i=r}^s(q_i+1)\right\}.            \tag{TP2}
\]
The bound is uniform over the fixed realized radial word.  An arbitrary
inter-block reset terminates the estimate; the next block restarts from an
arbitrary law.

## proof

We first make the state spaces explicit.  A discrete pair is
\((a,e)\in A\times E\).  Every exterior kernel starts at the head
\(\operatorname{out}(e)\) of the preceding exit edge.  With
\(P_i^S=J_i^SH^S\), exact operator composition is
\[
 \Lambda^SP_r^S\cdots P_s^Sf
 =\lambda_A^SH^SJ_r^SH^S\cdots J_s^S({\cal H}^Sf).         \tag{TP3}
\]
Thus the rough directed-edge observable is averaged by \({\cal H}^S\)
before any smooth comparison is attempted.

The continuum entrance and exit state spaces are separate copies of
\(\mathbb T\), in the common angular coordinate of the centered block.
Let \(\bar H\) be Brownian exit from radii \(M\) to \(eM\), and let
\(\bar J_i\) be the normalized Brownian return word.  Their densities are
rotation convolutions.  Explicitly,
\[
 {d\bar H(\alpha,\cdot)\over d\theta/(2\pi)}(\beta)
 ={e^2-1\over e^2+1-2e\cos(\beta-\alpha)},                \tag{TP4}
\]
and an elementary side kernel from logarithmic level \(x\) to \(b\) before
\(a\) has unnormalized density
\[
 {1\over2\pi}\left\{{x-a\over b-a}
 +2\sum_{n\ge1}{\sinh(n(x-a))\over\sinh(n(b-a))}
       \cos n(\beta-\alpha)\right\}.                      \tag{TP5}
\]
Consequently Haar measure \(m\) is preserved by \(\bar H\), by every
\(\bar J_i\), and by the continuum pair law
\(\bar\Lambda(d\alpha,d\beta)=m(d\alpha)\bar H(\alpha,d\beta)\).

We next construct the continuum test functions.  Write \(G^S=G_D\).
For \(x,x'\in D(y,M/2)\), the exact bridge identities are
\[
 {\cal H}^Sm_x(a)=G^S(a,x),                               \tag{TP6}
\]
\[
 \begin{split}
 {\cal H}^Sq_{x,x'}(a)
 &=G^S(a,x)G^S(x,x')+G^S(a,x')G^S(x',x)\\
 &\quad-\mathbf1_{\{x=x'\}}G^S(a,x).
 \end{split}                                               \tag{TP7}
\]
Let \(a_\alpha=y+Me^{i\alpha}\) and
\[
       \mathscr G^B(a_\alpha,x)={2\over\pi}
              g_{B(y,eM)}^B(a_\alpha,x).
\]
For \(f=m_x/C\), define
\(\varphi_f(\alpha)=\mathscr G^B(a_\alpha,x)/C\).  For
\(f=q_{x,x'}/[C(1+G^S(x,x'))]\), define \(\varphi_f\) by the right side
of (TP7), replacing only the boundary-variable factors
\(G^S(a,x),G^S(a,x')\) by \(\mathscr G^B(a_\alpha,x)\) and
\(\mathscr G^B(a_\alpha,x')\).  The short-distance lattice coefficients
\(G^S(x,x')\) are retained, including on the diagonal.

After scaling by \(M\),
\[
 g_{B(0,e)}^B(z,\xi)=\log\left|{e^2-z\bar\xi\over e(z-\xi)}\right|,
       \qquad |z|=1,\quad|\xi|\le\tfrac12,               \tag{TP8}
\]
up to the fixed Green normalization.  The denominators stay uniformly
away from zero, and symmetry of \(G^S\) bounds all retained normalized
coefficients.  Hence
\[
                  \sup_f\|\varphi_f\|_{C^4(\mathbb T)}\le C.          \tag{TP9}
\]

The complete external Green comparison used here is
Kozdron--Lawler, *Estimates of random walk exit probabilities and
application to loop-erased random walk*, paper_id
KozdronLawler2005DiscretePoissonKernel, arXiv id math/0501189,
Corollary 3.5, equation (30): if \(A\) is a simply connected lattice
domain of inradius in \([n,2n]\), \(\widetilde A\) is its union-of-squares
domain, and \(u\in A_n^*:=\{z:g_A(0,z)\ge n^{-1/16}\}\), then uniformly
in \(z\in A\),
\[
 G_A(u,z)={2\over\pi}g_{\widetilde A}(u,z)+k_{z-u}
                 +O(n^{-7/24}\log n),                    \tag{TP10}
\]
where \(k_w=k_0+(2/\pi)\log|w|-a(w)\).  Translate the core pole to the
paper's origin and use symmetry.  Here \(k_{a-x}=O(M^{-2})\), the
union-of-squares disk is sandwiched between disks whose radii differ by
\(O(1)\), and normal projection costs \(O(M^{-1})\).  Equations
(TP6)--(TP10) therefore give, with \(U_A\) denoting angular pullback,
\[
 \|{\cal H}^Sf-U_A\varphi_f\|_\infty
       \le C\epsilon_G(M),\qquad
 \epsilon_G(M)=M^{-7/24}\log M.                           \tag{TP11}
\]

Lemma lem:smooth-interface-discretization, with the same tubular
continuation for a disk having only its exit boundary, gives for every
smooth angular test \(F\)
\[
 \|H^SU_EF-U_A\bar HF\|_\infty
       +|\lambda_A^SU_AF-mF|
       \le {C\over M}\|F\|_{C^4}.                         \tag{TP12}
\]
For completeness, the second term is obtained by solving the disk Dirichlet
problem with boundary data \(F\), starting at the center, and repeating
(39e)--(39f); the first is the same argument in the annulus.  Thus (TP12)
does not assume rotational symmetry of a digital circle.

It remains to normalize a complete return word without dividing an
additive error by its possibly tiny mass.  Write its elementary kernels as
\[
 T_{i,l}^S(z,dz')=p_{i,l}^S(z)K_{i,l}^S(z,dz'),\qquad
 \bar T_{i,l}=\bar p_{i,l}\bar K_{i,l},\qquad1\le l\le q_i,
\]
and let \(Q_i^S=K_{i,1}^S\cdots K_{i,q_i}^S\).  Under this normalized
digital chain put
\[
 W_i=\prod_{l=1}^{q_i}{p_{i,l}^S(Z_{l-1})\over\bar p_{i,l}}.
\]
By (39c), if \(\eta_i=C\sum_lR_{i,l}^{-1}\le Cq_i/M\), then
\(e^{-\eta_i}\le W_i\le e^{\eta_i}\).  With
\(\bar s_i=\prod_l\bar p_{i,l}\), the identities
\[
 {R_i^S1(e)\over\bar s_i}=E_{Q_{i,e}^S}W_i,qquad
 J_i^SF(e)={E_{Q_{i,e}^S}[W_iF(Z_{q_i})]
                 \over E_{Q_{i,e}^S}W_i}                  \tag{TP13}
\]
are exact.  Hence
\[
             \|J_i^SF-Q_i^SF\|_\infty
             \le C\eta_i\|F\|_\infty.                    \tag{TP14}
\]

Apply the normalized smooth-test estimate following (39c) to the
\(K_{i,l}^S\) and telescope from the right.  If
\(\Phi_{l,F}=\bar K_{i,l+1}\cdots\bar K_{i,q_i}F\), convolution gives
\(\|\Phi_{l,F}\|_{C^4}\le\|F\|_{C^4}\).  With the appropriate angular
pullback at every state,
\[
 \|Q_i^SU_AF-U_E\bar J_iF\|_\infty
       \le C\eta_i\|F\|_{C^4}.
\]
Together with (TP14),
\[
 \|J_i^SU_AF-U_E\bar J_iF\|_\infty
       \le C\eta_i\|F\|_{C^4}.                            \tag{TP15}
\]
Every future row mass of the fixed word is present in the weight (TP13).

Finally flatten (TP3) into alternating operators
\(H^S,J_r^S,H^S,\ldots,J_s^S\), with terminal test
\(g_f^S={\cal H}^Sf\).  Let \(L_j^S,\bar L_j\) be the corresponding
discrete and Brownian operators, \(U_j\) the pullback on the correct
source space, and
\(\Phi_{j,f}=\bar L_{j+1}\cdots\bar L_N\varphi_f\).  The typed
right-telescoping identity is
\[
\begin{split}
 L_1^S\cdots L_N^Sg_f^S-U_0\bar L_1\cdots\bar L_N\varphi_f
 &=L_1^S\cdots L_N^S(g_f^S-U_N\varphi_f)\\
 &\quad+\sum_{j=1}^NL_1^S\cdots L_{j-1}^S
 [L_j^SU_j\Phi_{j,f}-U_{j-1}\bar L_j\Phi_{j,f}].          \tag{TP16}
\end{split}
\]
All \(\Phi_{j,f}\) have uniformly bounded \(C^4\)-norm by (TP9) and
convolution contraction.  Equations (TP11), (TP12), and (TP15) bound
(TP16) by the right side of (TP2).  In the continuum the alternating
product preserves Haar flux, so it has integral \(m\varphi_f\).  A
separate zero-length use of (TP11)--(TP12) gives
\(|\Lambda^Sf-m\varphi_f|\le C(\epsilon_G+M^{-1})\).
Subtracting these two comparisons proves (TP2).

For a lower conformal block the same proof uses its one common
\(\chi_y\)-angle.  Each occurrence of \(H^S\) has angular conjugacy error
\(O(M^{-1}+e^{-J+h})\).  Since \(2h\le J\),
\(e^{-J+h}\le M^{-1}\), and paying this error once per occurrence is
already contained in \(M^{-1}\sum_i(q_i+1)\).  No angular-dependent branch
choice or normalized future Doob likelihood is inserted into (TP16); such a
choice need not preserve Haar and is handled only by the exact reset density
below.

# lemma lem:terminal-feynman-kac

## statement

Fix a center \(y\) and set \(o_y:=y\).  Let
\[
 D_y=\{z\in\mathbb Z^2:\|z-y\|<eM\},\qquad
 A_y=\partial_{\rm in}\{z:\|z-y\|<M\},\qquad
 V_y=\{z:\|z-y\|<M/2\},
\]
where \(\partial_{\rm in}D=\{a\in D:\exists a'\notin D,\ a'\sim a\}\),
and let \(E_y=\{(u,v):u\in D_y,v\notin D_y,u\sim v\}\) be the directed
exit edges.  A completed
terminal piece begins at the first lattice vertex \(a\) after an inward
crossing of radius \(M\), and is killed on the directed edge \(e\in E_y\)
that first crosses radius \(eM\).  Erasing the interiors of all such
outward pieces gives exactly the intrinsic sigma-field \({\cal R}_y\) of
Lemma lem:buffered-transfer.  Conditional on their endpoint pairs
\(\omega_i=(a_i,e_i)\), their occupation vectors
\(X_i=(X_i(x):x\in V_y)\) are independent killed lattice bridges.

An **admissible centered block word** \(w\) is a positive-probability
radial-only cylinder.  It has \(b=O(J^2)\) completed pieces, at most
\(Q\le J^3\) adjacent-shell decisions, and a fixed
number \(G_0\) of blocks.  Within each block every decision is between
circles centered at \(y\), or, in the lower spherical transfer, between successive level
sets of the single conformal coordinate \(\chi_y\).  In either case the
normalized Brownian kernels are rotation convolutions in one common
angular coordinate; this is what ``centered block'' means here.  Between
two lower blocks the safe connector contributes no observable and its
normalized angular kernel is treated only as an arbitrary reset.  Its
scalar prescribed-side row mass is retained in the exact word
factorization, but no comparison of its angular density or invariant law
is made.  Before factorization, retain only source intervals containing
at least one completed terminal piece as blocks.  Fold any initial empty
intervals and connectors into the first chronological law, every
intervening string of empty intervals and connectors into the preceding
reset, and every terminal such string into the final reset.  Hence
\(b_g\ge1\), and in the lower application \(G_0\le m_0\); the
inter-source connectors and empty intervals contribute no core
occupation.  In the upper application \(G_0=1\) when \(b>0\), after the
centered extension (39k).  The case \(b=0\) is trivial and is henceforth
excluded.  The reset construction below assigns every initial/final
suffix and connector exactly once, so there is no unrecorded future
weight.  Put
\[
 H(a,e)=P_a\big((S_{\tau_{D_y^c}-1},S_{\tau_{D_y^c}})=e\big).
\]
Write \(b_g\) for the number of completed pieces in block \(g\), so
\(\sum_gb_g=b\).  For \(i<b_g\), let
\(R_{g,i}^w(e,da')\) be the sub-Markov kernel of the prescribed exterior
return word, started at \(\operatorname{out}(e_{g,i})\), from
\(e_{g,i}=e\) to the next entrance
\(a_{g,i+1}=a'\).  The pair subkernel factors exactly as
\[
 Q_{g,i}^w((a,e),d(a',e'))=
       R_{g,i}^w(e,da')H(a',de').                           \tag{47c}
\]
Write
\[
 \sigma_{g,i}(e)=R_{g,i}^w1(e),\qquad
 J_{g,i}^w={R_{g,i}^w\over\sigma_{g,i}},
 \qquad\widetilde K_{g,i}^w=J_{g,i}^wH.                    \tag{47d}
\]
For \(g<G_0\), let
\[
 C_g^w(e,d\zeta,d\omega')                                  \tag{47d'}
\]
be the genuine sub-Markov reset kernel which, after the last endpoint
of block \(g\), contains the prescribed final no-more-piece suffix, the
safe connector and its data \(\zeta\), and the prefix of block \(g+1\)
through its first endpoint pair \(\omega'\).  For \(g=G_0\), the same
notation denotes the final suffix to a cemetery state.  Put
\[
 \sigma_{g,b_g}(e)=C_g^w1(e),\qquad
 J_{g,b_g}^w=C_g^w/\sigma_{g,b_g}.                          \tag{47d''}
\]
In a centered suffix every adjacent-shell letter is included in \(Q\).
A lower inter-source connector is not declared centered; its normalized
kernel \(J_{g,b_g}^w\) is used as an arbitrary reset.

Let \(\alpha_{1,w}\) be the actual subprobability law of the first endpoint
pair after imposing only the word prefix through that piece.  Admissibility
means \(\alpha_{1,w}1>0\); put
\(\mu_{1,w}=\alpha_{1,w}/(\alpha_{1,w}1)\).  The
**sequentially normalized** law \(\widetilde P_w\) is the
joint law of all endpoint and reset variables that starts with
\(\mu_{1,w}\), uses \(\widetilde K_{g,i}^w\) internally, and uses the
normalized reset kernels \(J_{g,b_g}^w\) between blocks and at the final
cemetery transition.  Thus the first law of every later block is
generated chronologically by the preceding reset, not conditioned on
its future output.  Write \(P_w\) for the true endpoint-and-reset law
conditioned on the complete word \(w\).  All estimates are uniform over
the arbitrary normalized reset kernels, which are marginalized at the
end.

Let \(\lambda_A\) be the law of the first hit of \(A_y\) by a walk started
at \(o_y\), and set
\[
                 \Lambda_M(da,de)=\lambda_A(da)H(a,de).     \tag{47e}
\]
For a pair observable \(f\), write
\[
                 ({\cal H}f)(a)=\sum_eH(a,e)f(a,e).         \tag{47f}
\]
For \(x,x'\in V_y\), define
\[
 m_x(a,e)={G(a,x)H(x,e)\over H(a,e)},                       \tag{47g}
\]
\[
 q_{x,x'}(a,e)={G(a,x)G(x,x')H(x',e)
 +G(a,x')G(x',x)H(x,e)
 -{\bf1}_{\{x=x'\}}G(a,x)H(x,e)\over H(a,e)}.              \tag{47h}
\]
Uniformly,
\[
 0\le m_x\le C,\qquad0\le q_{x,x'}\le C(1+G(x,x')),       \tag{47h'}
\]
and the exit-edge averages are exactly
\[
 {\cal H}m_x(a)=G(a,x),
\]
\[
 {\cal H}q_{x,x'}(a)=G(a,x)G(x,x')+G(a,x')G(x',x)
             -{\bf1}_{\{x=x'\}}G(a,x).                    \tag{47h''}
\]
The finite normalized observable family is
\[
 {\cal F}_M=\{m_x/C:x\in V_y\}\cup
 \left\{{q_{x,x'}\over C(1+G(x,x'))}:x,x'\in V_y\right\}; \tag{47i}
\]
it has at most \(CM^4\) members.  Put
\[
 \varepsilon_M=CM^{-7/24}\log M,
 \qquad
 \eta_w^*:=CQ/M+CG_{\rm nc},                                \tag{48a}
\]
where \(G_{\rm nc}\le G_0\le m_0\) counts noncentered whole resets; each
is factored once through the separator (59a0) below.  Thus
\(G_{\rm nc}=0\) in the upper application and is fixed in the lower one.
Take the deterministic centers \(c_f=\Lambda_Mf\).  Before the
normalizations in (47i), they satisfy
\[
 c_{m_x}=g+O(\varepsilon_M),                                \tag{48b}
\]
\[
 c_{q_{x,x'}}=gG(x,x')+gG(x',x)-{\bf1}_{\{x=x'\}}g
       +O(\varepsilon_M(1+G(x,x'))).                        \tag{48c}
\]
The exact complete-word density and its bound are
\[
 {dP_w\over d\widetilde P_w}
 ={\displaystyle\prod_{g=1}^{G_0}\prod_{i=1}^{b_g}
          \sigma_{g,i}(e_{g,i})\over
   \displaystyle E_{\widetilde P_w}
       \prod_{g=1}^{G_0}\prod_{i=1}^{b_g}
          \sigma_{g,i}(e_{g,i})},
\qquad
 e^{-2\eta_w^*}\le
 {dP_w\over d\widetilde P_w}
 \le e^{2\eta_w^*}.                                        \tag{48d}
\]
The product visibly includes the final no-more-piece suffix and every
connector likelihood.  For every \(t>0\), conditionally on \(w\),
\[
\begin{split}
P_w\Bigg(&\max_{f\in{\cal F}_M}\left|
 b^{-1}\sum_{i\le b}f(\omega_i)-c_f\right|\\
&>t+C\{G_0/b+\varepsilon_M+Q/M\}\Bigg)
 \le2|{\cal F}_M|\exp\{2\eta_w^*-cbt^2\}.                   \tag{49}
\end{split}
\]

For \(x\in V_y\), \(G=G_{D_y}\), and
\[
 r_\theta(x):=
 \frac{e^\theta-1}
 {1-(G(x,x)-1)(e^\theta-1)},                                 \tag{39}
\]
uniformly for \(0\le r_\theta\le c/h\), \(h=\log M\),
\[
 \log E\left[\exp\left\{\theta\sum_{i=1}^bX_i(x)\right\}
             \,\middle|\,w\right]
       =bg\,r_\theta+O\left(br_\theta^2+
       r_\theta\{G_0+b\varepsilon_M+bQ/M\}
                    +\eta_w^*\right).                       \tag{50}
\]
The estimate is uniform in \(x,w,b\) and concerns completed pieces.
In both applications below, every visit to \(V_y\) lies in a completed
piece, so no conditional incomplete-piece estimate is needed.

For the upper-bound choice from Lemma lem:buffered-transfer,
\[
 h=(C_h\log J)^4,\qquad n=J-h+O(1),\qquad
 U=u_{J,c},\quad c>2,
\]
put \(Y=\sqrt{2b}\).  On a coefficient-two coarse barrier, uniformly over
all \(0\le Y\le 3n\),
\[
\begin{split}
 P\left(\max_{x\in V_y}\sum_iX_i(x)\ge U\mid w,b\right)
 &\le C e^{-2n}J^c e^{b/n}\\
 &\quad{}\times
 \exp\left\{-\kappa\min\left(
 \frac{(p-p_*)^2}{h},\frac{J^2}{h}\right)\right\},            \tag{51}
\end{split}
\]
whenever \(Y\) is in the central range.  Here
\[
 p=B_n+1-Y,\qquad B_n=\rho_Jn+z_0+h^{1/4},\qquad
 p_*=O(\log J).
\]
Here the coefficient-two barrier means
\[
 \sqrt{2T^S_{y,j}}\le
 B_j:=\rho_Jj+z_0+(j\wedge(J-j))^{1/4}
 \quad(k_y<j\le n),                                         \tag{52}
\]
after the fixed \(O(1)\) relaxation of Lemma
lem:buffered-transfer.  The central range is
\(\epsilon n\le Y\le B_n+1\), for one fixed small
\(\epsilon>0\).  For \(Y<\epsilon n\), (51) holds with its last factor
replaced by \(\exp(-\kappa J^2/h)\).

## proof

Let
\[
 H(a,e)=P_a\big((S_{\tau-1},S_\tau)=e\big),\qquad
 \tau=\tau_{D_y^c}.
\]
For the bridge from \(a\) to \(e\), write \(X(x)\) for its occupation of
\(x\).  Splitting at the first visit to \(x\), and then summing the
geometric number of returns to \(x\), gives the exact rank-one identity
\[
\begin{split}
 H_\theta(a,e)
 &:=E_a[e^{\theta X(x)};(S_{\tau-1},S_\tau)=e]\\
 &=H(a,e)+r_\theta G(a,x)H(x,e).                              \tag{42}
\end{split}
\]
Thus
\[
       \frac{H_\theta(a,e)}{H(a,e)}
       =1+r_\theta m_x(a,e),\qquad
       m_x(a,e):=\frac{G(a,x)H(x,e)}{H(a,e)}.                 \tag{43}
\]
Fixed-ratio Harnack gives \(0\le m_x\le C\), uniformly in
\(x\in V_y\).  We will not assert that the atom-level function
\((a,e)\mapsto m_x(a,e)\) has a uniformly smooth interpolation on the
jagged digital exit boundary.  Instead we use the exact smoothing already
present in (47c).  From (43),
\[
 ({\cal H}m_x)(a)=\sum_eH(a,e)m_x(a,e)=G(a,x).               \tag{43a}
\]
More generally, if \(q_{x,x'}(a,e)=E^{a,e}[X(x)X(x')]\), the
two ordered visit-time decompositions give
\[
\begin{split}
 ({\cal H}q_{x,x'})(a)
 &=G(a,x)G(x,x')+G(a,x')G(x',x)\\
 &\quad-{\bf1}_{\{x=x'\}}G(a,x).                            \tag{43b}
\end{split}
\]
Thus the only functions subsequently fed into a return-word kernel are
Green functions with their singularities a distance at least \(M/2\)
from \(A_y\).

We next identify the common center and the only observables that require
comparison.  With \(\lambda_A\) defined as the first-hit law of the
inner vertex boundary, Strong Markov gives
\[
 d_x:=\sum_a\lambda_A(a)G_{D_y}(a,x)
 =G_{D(y,eM)}(o_y,x)-G_{D(y,M)}(o_y,x)
                  +O(M^{-1}\log M).                         \tag{44}
\]
Indeed the one-edge collar can return from \(A_y\) to \(D(y,M/2)\)
before exiting \(D(y,M)\) with probability \(O(M^{-1})\), while the
Green function is at most \(C\log M\).  This remainder is
\(o(\varepsilon_M)\).

The quantitative comparison used here is Kozdron--Lawler,
*Estimates of random walk exit probabilities and application to
loop-erased random walk*, paper_id
KozdronLawler2005DiscretePoissonKernel, arXiv id math/0501189,
Corollary 3.5, equation (30).  In their notation, if \(A\) is a simply
connected lattice domain with inradius in \([n,2n]\), \(\widetilde A\)
is its union-of-squares domain, \(g_A\) is its Brownian Green function,
and \(u\in A_n^*:=\{z:g_A(0,z)\ge n^{-1/16}\}\), then, uniformly in
\(z\in A\),
\[
 G_A(u,z)={2\over\pi}g_A(u,z)+k_{z-u}
                  +O(n^{-7/24}\log n),                    \tag{45}
\]
where \(k_w=k_0+(2/\pi)\log|w|-a(w)\) and \(a\) is the lattice
potential kernel.  The digital disks here satisfy the hypotheses, and
all tags are a fixed fraction from the boundary.  Sandwiching their
union-of-squares domains between disks with radii differing by \(O(1)\)
and subtracting the two radii in (44) yields, uniformly in \(x\in V_y\),
\[
                     d_x=g+O(\varepsilon_M),
 \qquad \varepsilon_M=CM^{-7/24}\log M.                    \tag{46}
\]
Together with the exact identities (43a)--(43b), this gives precisely
the centers (48b)--(48c).  No derivative of the error in (45), and no
smooth interpolation of a rough directed-edge observable, is used.

We now control a complete centered return word.  The state of
\(R_{g,i}^w\) is the preceding directed exit edge, and the walk restarts at
its head; its target is the next inward directed edge.  A word is called
admissible only when its cylinder has positive probability, so every row
normalization below is defined.  Brownian row masses of its elementary
letters are scalar, while Lemma lem:smooth-interface-discretization gives
their relative lattice comparison.  The exact whole-word weighting formula
(TP13) therefore yields, for a scalar \(s_{g,i}>0\),
\[
 \sup_e\left|{\sigma_{g,i}(e)\over s_{g,i}}-1\right|
       \le {Cq_i\over M}.                                  \tag{58c}
\]
This conclusion includes all future row masses inside that fixed return
word; it is not obtained by dividing an additive error by a rare word mass.

In the common logarithmic conformal coordinate, every normalized Brownian
letter is the rotation convolution (TP5), and the terminal disk exit is
(TP4).  Apply Lemma lem:typed-centered-endpoint-product to the exact
exit-edge averages (43a)--(43b).  For consecutive internal transitions
\(r\le s\) in one block and every \(f\in{\cal F}_M\), it gives
\[
 \left|\Lambda_M
   \widetilde K_{g,r}^w\widetilde K_{g,r+1}^w\cdots
   \widetilde K_{g,s}^wf-c_f\right|
 \le C\left\{\varepsilon_M+
       {1\over M}\sum_{i=r}^s(q_i+1)\right\}.              \tag{58e}
\]
Here the continuum counterparts are the explicit disk-Green traces in
(TP6)--(TP9), every suffix is defined by the typed convolution product in
(TP16), and the discrete expression and \(c_f\) are compared separately to
the same Haar-flux integral.  Thus (58e) neither asserts that the discrete
chain preserves \(\Lambda_M\) nor interpolates the raw jagged-edge
observables.  A lower source interval uses its single common
\(\chi_y\)-angle; the terminal chart defect is paid once per occurrence
and is included in the displayed sum.  An inter-source connector is an
arbitrary reset and ends this telescope.
The sequential kernels also have a genuine total-variation contraction,
independently of the smooth comparison.  We use
Athreya--Gadhiwala--Radhakrishnan, *Elliptic Harnack inequality for
simple random walk on \(\mathbb Z^d\)*,
paper_id AthreyaGadhiwalaRadhakrishnan2022EHI, arXiv id 2201.11947,
Theorem 1.1.  Its complete statement is: for every \(d\ge1\) there is
\(C_d\) such that, whenever \(u\ge0\) is discrete harmonic in
\(B(x_0,R)\),
\[
       \max_{B(x_0,R/2)}u\le C_d\min_{B(x_0,R/2)}u.           \tag{58a}
\]
Starting one step inside the outer boundary is too close to use (58a)
directly.  Insert instead the deterministic intermediate circle
\[
                 C_M=\partial D(y,e^{1/2}M),
\]
which every successful outer-to-inner crossing must hit.  For a target
atom \(a\in A_y\), put
\[
 h_a(z)=P_z(S_{H_{A_y}}=a,\ H_{A_y}<\tau_{D(y,eM)}),
 \qquad s(z)=\sum_{a\in A_y}h_a(z),\qquad z\in C_M.
\]
A bounded chain of lattice balls of radius \(cM\), all a fixed positive
fraction from both boundary components, applies (58a) to \(h_a\) and
\(s\).  Uniformly in \(a,z,z_0\in C_M\),
\[
 ch_a(z_0)\le h_a(z)\le Ch_a(z_0),\qquad
 cs(z_0)\le s(z)\le Cs(z_0).
\]
After division by the total successful-leg probability this gives
\[
       J_{\rm in}(z,\cdot)\ge\alpha
                     J_{\rm in}(z_0,\cdot)                  \tag{58b}
\]
with \(\alpha>0\) uniform in \(M,z,z_0\).  Precomposition by all earlier
within-block word factors and postcomposition by \(H\) preserve this row-independent
minorization.  Hence
\(\operatorname {osc}(\widetilde K_{g,i}^wf)\le(1-\alpha)
\operatorname {osc}(f)\) for every bounded \(f\) at every within-block
transition.  Write \(\rho=1-\alpha<1\).  A reset transition is used
exactly and has Dobrushin coefficient at most one; there are only
\(G_0-1\) of them.

There is no common-center assertion for a global connector.  Instead we
factor every reset through a deterministic separator.  Fix
\[
        \lambda_*=e^{3/2}\in(e,e^2),\qquad
        \Sigma_y=\partial D(o_y,\lambda_*M).                \tag{59a0}
\]
The next active outer interface after the terminal \(eM\)-circle has scale
\(e^2M\).  The fixed-gap geometry and (47c) put \(\Sigma_y\) strictly
between them and keep \(D(o_y,\lambda_*M)\) inside the applicable source
interval and global killing domain.

Let \(e=(u,v)\in E_y\) be the last exit edge of a nonempty block, so the
exterior kernel starts at \(v=\operatorname{out}(e)\) and
\(|v-o_y|=eM+O(1)\).  Put
\[
 \theta_-=H_{D(o_y,M)},\qquad
 \theta_+=\tau_{D(o_y,\lambda_*M)},
\]
and on \(\{\theta_+<\theta_-\}\) let \(F_+\) be the directed outward
edge at \(\theta_+\).  For \(g<G_0\), let
\(B_g^w(f,d\zeta,d\omega')\) be the genuine post-separator subkernel
which realizes the rest of the no-more-piece suffix, all folded empty
source intervals and safe connector signs, and the next nonempty block
prefix through its first endpoint pair.  For \(g=G_0\) it instead contains
the remaining suffix and final cemetery transition.  Durations, parities,
angles, and already visible edge data are outputs of this kernel, never
extra scalar conditions.  Set \(r_g^w(f)=B_g^w(f,\hbox{all outputs})\).
The strong Markov property gives the exact factorization
\[
 C_g^w(e,d\gamma)=\sum_f
 P_v(\theta_+<\theta_-,F_+=f)B_g^w(f,d\gamma).              \tag{59a1}
\]
Indeed, a return to \(D(o_y,M)\) before \(\Sigma_y\) after the alleged
last completed piece would, on the subsequent trip to the block's outer
endpoint, force another exit of \(D_y\), hence another completed terminal
piece.  Conversely, no reset restriction other than avoiding the inner
circle is tested before \(\Sigma_y\); all remaining restrictions occur in
\(B_g^w\).

Define on the digital annulus
\[
 \Omega_y=D(o_y,\lambda_*M)\setminus D(o_y,M)
\]
\[
 h_g^w(z)=E_z[r_g^w(F_+);\theta_+<\theta_-].                \tag{59a2}
\]
This is a nonnegative discrete harmonic function at every interior vertex,
with exact Dirichlet value zero on the inner boundary and the possibly rough
edge data \(r_g^w\) on the outer boundary.  Global killing and the entire
later connector/prefix occur only in that outer boundary datum.  Moreover,
\[
                  \sigma_{g,b_g}(e)=C_g^w1(e)=h_g^w(v).     \tag{59a3}
\]
All such \(v\)'s lie in the band
\(\bigl|\|v-o_y\|-eM\bigr|\le2\), a distance
comparable to \(M\) from both components of \(\partial\Omega_y\).
A fixed number of overlapping lattice balls of radius \(cM\), whose doubled
balls remain in \(\Omega_y\), connects any two points of this band.
Athreya--Gadhiwala--Radhakrishnan, paper_id
AthreyaGadhiwalaRadhakrishnan2022EHI, arXiv id 2201.11947,
Theorem 1.1, quoted completely in (58a), and this chain give
\[
       \sup_e\sigma_{g,b_g}(e)
              \le C_H\inf_e\sigma_{g,b_g}(e).              \tag{59a}
\]
If \(h_g^w\) vanishes at one interior start, the mean-value property and
connectedness make it identically zero, and the complete word cylinder has
zero mass and is discarded.  Otherwise every row is positive and the
normalization \(J_{g,b_g}^w=C_g^w/\sigma_{g,b_g}\) is defined.  This proves
(59a) independently of how rare or rough the later event is.

Start the first block with its actual chronological law through the first
endpoint.  Use every normalized internal kernel and every normalized reset
in chronological order, including the final cemetery output, to define
\(\widetilde P_w\).  Direct disintegration of the unnormalized cylinder
measure gives
\[
 {dP_w\over d\widetilde P_w}
 ={\displaystyle\prod_{g=1}^{G_0}\prod_{i=1}^{b_g}
          \sigma_{g,i}(e_{g,i})\over
   \displaystyle E_{\widetilde P_w}
       \prod_{g=1}^{G_0}\prod_{i=1}^{b_g}
          \sigma_{g,i}(e_{g,i})}.                           \tag{60a}
\]
There is no separate initial density and no unrecorded final factor.
Equation (58c), applied also to a centered final suffix, bounds the
logarithmic row oscillation of centered factors by \(Cq_i/M\); (59a) costs
\(\log C_H\) once per genuinely noncentered reset.  Thus in the upper
centered extension \(G_{\rm nc}=0\), while in the lower construction
\(G_{\rm nc}\le G_0\le m_0\).  Scalar
constants cancel between numerator and denominator, so, after absorbing
\(\log C_H\) into \(C\),
\[
 \left|\log{dP_w\over d\widetilde P_w}\right|
 \le2\{CQ/M+CG_{\rm nc}\}=2\eta_w^*.                       \tag{60b}
\]
Here is a proof of (49).  Fix \(w\) and a normalized
\(f\in{\cal F}_M\), expose the sequential joint chain under
\(\widetilde P_w\), and use the Doob martingale of
the whole sum \(\sum_{i\le b}f(\omega_i)\).  Changing \(\omega_i\) changes the
conditional expectation of the future sum by at most
\[
       2G_0\sum_{j\ge0}\rho^j\le {2G_0\over1-\rho};
\]
this deliberately allows an arbitrary reset at every later block.
Azuma--Hoeffding consequently gives
\[
 \widetilde P_w\left(\left|\sum_{i\le b}f(\omega_i)
       -E_{\widetilde P_w}\sum_{i\le b}f(\omega_i)\right|>bt\right)
 \le2e^{-cbt^2}.                                             \tag{61}
\]
More explicitly, if the \(k\)-th endpoint of a block has actual initial
law \(\mu\), contraction and the full prefix comparison (58e) give
\[
\begin{split}
\left|\mu\widetilde K_{g,1}^w\cdots
 \widetilde K_{g,k-1}^wf-c_f\right|
 &\le2\rho^{k-1}\\
 &\quad+C\left\{\varepsilon_M+
 {1\over M}\sum_{j<k}(q_j+1)\right\}.                      \tag{61a0}
\end{split}
\]
For \(k=1\) this just uses \(\|f\|_\infty\le1\).
Summing (61a0) over all endpoints and blocks, and using
\(\sum_j(q_j+1)\le C Q\), gives
\[
 \left|E_{\widetilde P_w}\sum_{i\le b}f(\omega_i)-bc_f\right|
 \le C\{G_0+b\varepsilon_M+bQ/M\}.                         \tag{61a}
\]
A union bound under \(\widetilde P_w\), followed by (48d), proves
(49).  Thus the common center comes from prefix
comparison plus contraction, not from a one-step invariance claim.

We finally prove the Feynman--Kac estimate without making a local
invariance claim for a word-conditioned Doob transform.  Conditional on
the endpoints, (42)--(43) makes the exponential moment
\(\prod_i(1+rm_x(\omega_i))\).  Under \(\widetilde P_w\), put
\[
                 \psi_i=\log(1+rm_x(\omega_i)).              \tag{62}
\]
Since \(0\le m_x\le C\),
\(\psi_i=rm_x(\omega_i)+O(r^2)\) and
\(\operatorname {osc}(\psi_i)\le Cr\).  The same influence calculation
as for (61) shows that every Doob martingale difference for
\(\sum_i\psi_i\) is at most \(CG_0r/(1-\rho)\).  Conditional Hoeffding and
Jensen therefore give
\[
 0\le\log E_{\widetilde P_w}e^{\sum_i\psi_i}
       -E_{\widetilde P_w}\sum_i\psi_i\le Cbr^2.             \tag{62a}
\]
The exact exit-edge average and its Taylor remainder are
\[
 \sum_eH(a,e)\log(1+rm_x(a,e))=rG(a,x)+O(r^2),             \tag{62b}
\]
because \(m_x\le C\) and \(\sum_eH(a,e)m_x(a,e)=G(a,x)\le C\).
The product telescoping (61a), now for \(m_x/C\), and (46) give
\[
 \sum_{i\le b}E_{\widetilde P_w}m_x(\omega_i)
       =bg+O\{G_0+b\varepsilon_M+bQ/M\}.                    \tag{62c}
\]
Combining (62)--(62c) proves the completed-piece version of (50) under
\(\widetilde P_w\).  Finally,
(48d) puts the exact full-word density (60a) between
\(e^{-2\eta_w^*}\) and \(e^{2\eta_w^*}\).  Multiplying the nonnegative
exponential by this global density and taking logarithms changes the
answer by at most \(2\eta_w^*\), exactly the last error in (50).
Thus (50) holds under \(P_w\).  No tilted local kernel or unsupported
conditioned-chain invariance is used.

The inverse of (39) is
\[
       \theta(r)=
       \log\frac{1+G(x,x)r}{1+(G(x,x)-1)r}.                   \tag{49}
\]
Take \(r_0=(gn)^{-1}\).  Since
\(G(x,x)=gh+O(1)\) and \(h^2/J=o(1)\),
\[
 \theta(r_0)=\frac1{gJ}+O(J^{-2}+h^2J^{-3}),\qquad
 \theta(r_0)U=2J-c\log J+O(1),\qquad bg r_0=b/n.              \tag{50}
\]
Since \(G_0=1\), \(b=O(J^2)\), \(Q\le J^3\), and
\(M=e^{(C_h\log J)^4}\), every error term in the new version of (50)
is \(O(1)\) at \(r_0\), uniformly in the word.
A union bound over \(O(e^{2h})\) sites, (50), and Chernoff's inequality
give the first line of (51).

We retain the tilt freedom to sum every endpoint band.  Set
\[
       F_b(r)=\theta(r)U-bgr-C_0br^2.
\]
Here are the derivative and feasibility details.  Uniformly on every fixed
interval \(0\le r\le a/h\),
\[
 \theta'(r)=\frac1{(1+Gr)(1+(G-1)r)},
\]
\[
 -\theta''(r)=\theta'(r)
 \left\{\frac G{1+Gr}+\frac{G-1}{1+(G-1)r}\right\}.
\]
Thus \(c_a\le\theta'(r)\le C_a\),
\(c_ah\le-\theta''(r)\le C_ah\), and
\(|\theta'''(r)|\le C_ah^2\).  Since \(b=O(J^2)\), after increasing
\(J\),
\[
       -C_1J^2h\le F_b''(r)\le-c_1J^2h.                     \tag{51a}
\]
Also
\[
 \theta'(r_0)=1-\frac{2h}{n}
                  +O(n^{-1}+h^2n^{-2}).                     \tag{51b}
\]
Define \(b_*\) by \(F_{b_*}'(r_0)=0\).  Since
\[
       b_*={U\theta'(r_0)\over g+2C_0r_0},
\]
the relations \(J=n+h+O(1)\) and \(h^2=o(J)\) give
\[
 b_*=2n^2-cn\log J+O(n+h^2+h\log J)
     =2n^2-cn\log J+O(n).
\]
Consequently
\[
       Y_*=\sqrt{2b_*}
          =2n-\frac c2\log J+O(1),                            \tag{51}
\]
and hence \(p_*=B_n+1-Y_*=O(\log J)\).  More exactly,
\[
 F_b'(r_0)=(g+2C_0r_0)(b_*-b)
          =(g+o(1)){(Y_*-Y)(Y_*+Y)\over2}.                  \tag{51c}
\]

Fix a sufficiently small constant \(\delta>0\).  If
\(\epsilon n\le Y\le B_n+1\) and \(|Y-Y_*|\le\delta J\), Taylor's
formula, (51a), and the displacement
\[
       s={F_b'(r_0)\over C_1J^2h}
\]
(with \(C_1\) enlarged once) give
\[
 \sup_rF_b(r)-F_b(r_0)
 \ge\kappa\frac{(Y-Y_*)^2}{h}.                              \tag{51d}
\]
This displacement is feasible.  If it is negative, the barrier and
\(h^{1/4}=O(\log J)\) imply \(Y-Y_*=O(\log J)\), whence
\(|s|=O(\log J/(Jh))=o(r_0)\).  If it is positive, choosing \(\delta\)
small ensures \(s<a/(2h)\).  When
\(\epsilon n\le Y\le Y_*-\delta J\), choose instead a fixed
\(s=a_0/h>0\), with \(a_0\) small compared with \(\delta/C_1\).
Equations (51a)--(51c) then give
\[
       F_b(r_0+s)-F_b(r_0)\ge\kappa J^2/h.                  \tag{51e}
\]
There is no range \(Y\ge Y_*+\delta J\) because the upper barrier permits
only an \(O(\log J)\) overshoot above \(Y_*\).

Finally, if \(Y<\epsilon n\), take \(r=a_0/h\) directly.  The integral
formula \(\theta(r)=\int_0^r\theta'(t)\,dt\) gives
\(\theta(a_0/h)\ge c_aa_0/h\).  First choosing \(\epsilon\) and then
\(a_0\) small yields
\[
       F_b(a_0/h)\ge\kappa_0J^2/h,
       \qquad F_b(r_0)=O(J)=o(J^2/h).                        \tag{51f}
\]
Equations (51d)--(51f), and
\(p-p_*=Y_*-Y\), prove precisely the two alternatives in (51).
This proves (51).

Finally, here is the promised incomplete-piece check for the actual
uses.  A lower source block begins and ends on interfaces outside
\(D_y\).  An upper block with \(k\le C_0\log J\) starts at the origin,
which is outside \(D_y\), and ends at \(\sigma_y\), also outside
\(D_y\).  Before the first inward crossing of radius \(M\) the path
cannot visit \(V_y\).  After any visit to \(V_y\), reaching the block's
outer endpoint forces a later crossing of radius \(eM\), so that inward
crossing and all intervening core occupation form a completed piece.
Thus the initial and final incomplete portions contribute exactly zero
to every \(X(x)\) used here.  Upper cells with \(k>C_0\log J\), including
the cells near the walk's starting point, are treated separately by the
one-site Green estimate in (62).

# proposition prop:localized-disk-upper

## statement

For every fixed \(\beta>0,c>2\) and \(A<\infty\),
\[
\begin{split}
 P\left(\max_{\lVert x\rVert\le e^JJ^{-\beta}}
             L_{\tau_{e^J}}(x)\ge u_{J,c}\right)
 \le J^{-2\beta+c-2+o(1)}+O(J^{-A}).                         \tag{53}
\end{split}
\]
The \(o(1)\) is uniform when \(\beta,c\) range over compact subsets of
\((0,\infty)\) and \((2,\infty)\), respectively.

## proof

Use the upper buffer
\[
       h=(C_h\log J)^4,\qquad M=e^h,\qquad n=J-h,
\]
with \(C_h\) fixed large.  Cover the target disk by original \(M\)-cells
obtained from the dilated image of Rosen's predetermined net \(F_n\),
rounding each image center to its nearest lattice point.  The chart has
uniformly bounded distortion on the relevant compact patch, so these
centers are \(cM\)-separated and form a \(CM\)-cover.  After altering the
fixed core and terminal radius factors, every lattice point lies in a
core, the overlap multiplicity is bounded, and Lemmas
lem:buffered-transfer and lem:terminal-feynman-kac use exactly the same
cells.  We continue to denote their radii by \(M/2\) and \(eM\).
For a cell center with \(\|y\|>M\), use the exact index from (45a0),
\[
 u_y=\log {3e^J\over\|y\|},\qquad
 k=k(y)=\lceil u_y\rceil,qquad m=k+1.                     \tag{54a}
\]
Cells with \(\|y\|\le M\) are assigned to the final sitewise range
\(k>C_0\log J\).  Uniform distortion of the fixed chart makes (54a)
equal to the spherical source index (24) up to a bounded additive error,
which is absorbed by the barrier slack.
Every target cell has
\[
       k\ge s:=\beta\log J+O(1).                              \tag{54}
\]
For this fixed cell continue the walk from \(\tau_{e^J}\) to
\(\sigma_y=\tau_{D(y,3e^J)}\).  By (39l), a high local time in the cell
before \(\tau_{e^J}\) is also high before \(\sigma_y\).  All counts,
words, terminal bridges, and the source index below refer to this single
\(y\)-centered extended path.  This domination is applied separately to
each cell before the final union bound.

First exclude a crossing of the fixed positive-intercept
coefficient-two barrier (52) at or before level \(n\).  Since
\(h>(4\log J)^4\) after choosing \(C_h\) large, all these levels lie in
the range of (45d)--(45e).  Restricting the source shells to \(k\ge s\)
and using (40) gives
\[
\begin{split}
 P(\hbox{some bad prefix in the target})
 &\le C\sum_{k\ge s}\sum_{l=k+1}^{n}
 e^{2(l-k)+\frac12 l_J^{1/4}}
 e^{-2l-l_J^{1/4}}\\
 &\le J^{-2\beta+o(1)},\qquad
 l_J:=l\wedge(J-l).                                          \tag{55}
\end{split}
\]
The source-shell extension through \(C_0\log J\) is exactly the direct
lattice extension proved in (45a)--(45e): neither the representative
count nor the one-center crossing estimate requires \(k\le\log J\).

Fix now one original cell in a shell
\[
       s\le k\le C_0\log J.
\]
Restrict the ensuing sum to complete source-inclusive words whose radial
prefix is good; no conditional probability given that prefix, or given a
future entrance-edge list, is taken.  Put \(m=k+1\) and
\[
       X=\sqrt{2T_m},\qquad Y=\sqrt{2T_n}.
\]
The directed-edge source estimate (45c) gives, for each unit band \(I_x\),
\[
       P(X\in I_x)\le C(k+1)^C\exp\{-x^2/(2m)\}.             \tag{56}
\]
For a unit endpoint band \(I_q=[q,q+1]\), let \(\mathscr A(q)\) denote
the disjoint union of complete words that retain the good barrier and end
in \(Y\in I_q\).  The joint source-inclusive comparison (45g), before any
disintegration of the actual lattice law, gives for every source band
\(I_x\)
\[
\begin{split}
 &P_S\bigl(X\in I_x,\mathscr A(q)\bigr)\\
 &\qquad\le e^{CJ^3/M}
   \sum_{\sqrt{2t}\in I_x}\pi_{m,u_y}(t)
       P_t^{\rm GW}(\mathscr A_t^{\rm GW}(q)).              \tag{56a}
\end{split}
\]
Only the ideal law on the right is disintegrated by \(t\).  The remaining
traversal chain has length \(L=n-m\).  Its affine barrier has endpoints
\(a=B_m\) and \(b=B_n+1\), and (31a) shows that it dominates the truncated
\(J\)-barrier without replacing \(\rho_J\) by \(\rho_n\).

Fix \(\epsilon_0>0\) small and
\(\epsilon_0n\le q\le B_n+1\), and put \(p=B_n+1-q\).  For each
\(t\ge2\), set \(x_t=\sqrt{2t}\) and apply (30) pointwise with initial
height \(x_t\), endpoint band \([q,q+1]\), and duration \(L\).  On the
good prefix, \(x_t\le B_m=O(m)\), while the exact geometric source law
satisfies
\[
       \pi_{m,u_y}(t)\le Cm^{-1}\exp\{-x_t^2/(2m)\}.
\]
Because \(m+L=n\), the two exponential costs combine by the exact identity
\[
 \frac{x_t^2}{m}+\frac{(q-x_t)^2}{L}
 =\frac{q^2}{n}+\frac{n(x_t-mq/n)^2}{mL}.                   \tag{57}
\]
Thus there is no ambiguity between a source-band label and the actual
source height.  Equivalently, grouping the \(x_t\)'s into unit bands changes
the displayed exponential by only \(e^{O(1)}\).  The Gaussian sum in the
last term and the remaining source factors cost only a polynomial in
\(m\).  Since \(q\ge\epsilon_0n\) and \(L\asymp n\), the ballot prefactor
in (30), including \(\sqrt{x_t/(qL)}\), gives
\[
 P(\hbox{prefix good},\,Y\in I_q)
 \le C(k+1)^C(1+p)n^{-2}\exp\{-q^2/(2n)\}.                  \tag{58}
\]
For the only positive start below two, namely \(T_m=1\), add an
independent ancestor and require that ancestor to die in its first
generation.  This has probability \(1/2\), so the desired probability is
at most twice the bound from initial population two: from generation
one onward the two paths agree, and these are exactly the generations on
which the barrier in (30) is imposed.  Initial population zero cannot
produce the present positive endpoint.  Thus
(58) is precisely the central-range version of (41), with the source
law and every parameter displayed.  Its lattice comparison is relative,
so there is no absolute KMT remainder to sum over the cells.

The complementary endpoint range needs no ballot estimate.  If
\(Y<\epsilon_0n\), then \(b\le\epsilon_0^2n^2/2+O(n)\), and the saturated
line of (51), uniformly in the radial word, gives
\[
 P(\hbox{terminal mark}\mid w)
 \le C e^{-2n}J^c
       \exp\{\epsilon_0^2n/2-\kappa J^2/h+O(1)\}.            \tag{58a}
\]
After summing this over at most \(Ce^{2n}\) original cells, the result is
\(o(J^{-A})\) for every fixed \(A\), because \(h=o(J)\), after fixing
\(\epsilon_0\) sufficiently small.  This is why neither (29) nor (41)
was claimed in the extinction range.

For the number \(b=T_n+O(1)\) of completed outward pieces in the band
\(I_q\),
\[
       b=q^2/2+O(n).
\]
Conditional on the radial word, Lemma lem:terminal-feynman-kac applies;
the start/end observation at the end of that lemma shows that all visits
to \(V_y\) belong to its completed pieces.  Multiply
(58) by (51).  The factors
\(\exp\{-q^2/(2n)\}\) and \(\exp\{b/n\}\) cancel up to a constant.
Moreover,
\[
 \sum_{0\le p\le B_n+1}(1+p)
 \exp\left\{-\kappa\min\left(
          \frac{(p-p_*)^2}{h},\frac{J^2}{h}\right)\right\}
       =J^{o(1)}.                                             \tag{59}
\]
Indeed the nonsaturated Gaussian sum is
\[
 O\bigl((1+|p_*|)\sqrt h+h\bigr)=J^{o(1)},
\]
while its saturated complement contributes
\(O(J^2)e^{-\kappa J^2/h}=o(1)\).  The small-\(Y\) part has the
saturated factor in (51).  Thus, uniformly
over all endpoint bands and all radial words,
\[
 P(\hbox{this original cell is good and marked})
       \le (k+1)^Ce^{-2n}J^{c-2+o(1)}.                        \tag{60}
\]
This is a bound for one original cell, not for each of its microscopic
descendants.

There are \(O(e^{2(n-k)})\) original cells in shell \(k\).  Summing (60)
and using (54) yields
\[
 \sum_{k=s}^{C_0\log J}e^{2(n-k)}
       (k+1)^Ce^{-2n}J^{c-2+o(1)}
       \le J^{-2\beta+c-2+o(1)}.                              \tag{61}
\]

It remains to treat \(k>C_0\log J\).  For a lattice site in shell \(k\),
Green-function identities and Lemma lem:elementary-walk-estimates give
\[
 P_0(H_x<\sigma_y)\le C(k+1)/J
\]
and, conditionally on the hit,
\[
 P_x(L_{\sigma_y}(x)\ge u_{J,c})
       \le Ce^{-2J}J^c.
\]
There are \(O(e^{2J-2k})\) sites in that shell.  Their total contribution
is
\[
       J^{c-1-2C_0+o(1)}.                                    \tag{62}
\]
Choose \(C_0\) after \(A,c\).  Combining (55), (61), and (62) proves
(53).  The word-cap and digital row errors are superpolynomial by
Lemma lem:buffered-transfer and are included in \(O(J^{-A})\); no KMT
comparison is used in this upper bound.

# lemma lem:terminal-maximum-lower

## statement

Fix \(1<p<2\), set
\[
       h=(\log J)^p,\qquad M=e^h,\qquad L=J-h,
\]
and suppose that a coarse cell has
\[
       b=2L^2-2L\log L+O(L)                                  \tag{63}
\]
completed terminal pieces.  For an endpoint pair \(\omega=(a,e)\), put
\[
 \mu_x(\omega)=E^\omega X(x),\qquad
 q_{x,x'}(\omega)=E^\omega[X(x)X(x')].
\]
Let \(t_J=\log J/(J\log\log J)\), and call its endpoint realization
**moment regular** when, simultaneously for all \(x,x'\in V_y\),
\[
\left|b^{-1}\sum_{i\le b}\mu_x(\omega_i)-\Lambda_M\mu_x\right|
 \le2t_J,\qquad
\left|b^{-1}\sum_{i\le b}q_{x,x'}(\omega_i)
             -\Lambda_Mq_{x,x'}\right|
\le2t_J(1+G(x,x')).                                        \tag{L1}
\]
For every admissible centered block word with (63) and \(G_0\le m_0\),
(49) implies
\[
 P(\hbox{moment regularity fails}\mid w)
 \le CM^4e^{-cbt_J^2}=o(J^{-A})                              \tag{L2}
\]
for each fixed \(A\).  Conditional on the intrinsic coarse sigma-field
\({\cal C}_y\) that exposes the word and endpoint pairs but erases the
bridge interiors, every moment-regular realization satisfies
\[
\begin{split}
 \max_{x\in V_y}\sum_{i\le b}X_i(x)
 &=gb+2\sqrt2\,g\sqrt b\,h\\
 &\quad{}+O_P\left(J\sqrt h+
              \frac{J\log J}{\log\log J}\right).             \tag{L3}
\end{split}
\]
Uniformly over such cells, the conditional probability that the left side
is at least \(u_{J,2+\eta}\) tends to one for every fixed \(\eta>0\).

## proof

Condition on all entrance and directed-exit pairs
\((a_i,e_i)_{i\le b}\).  By the strong Markov property the killed bridge
occupation vectors \(X_i=(X_i(x):x\in V_y)\) are independent.  Their exact
first and second moments are
\[
 E^{a,e}X(x)=\frac{G(a,x)H(x,e)}{H(a,e)},                     \tag{65}
\]
and
\[
\begin{split}
 E_a[X(x)X(x');E=e]
 &=G(a,x)G(x,x')H(x',e)\\
 &\quad+G(a,x')G(x',x)H(x,e)
 -{\bf1}_{\{x=x'\}}G(a,x)H(x,e).                             \tag{66}
\end{split}
\]
These follow by ordering the two visit times and subtracting the common
diagonal.

We verify both the screen and its centering.  Formula (65) is precisely
\(\mu_x(\omega)\), and dividing (66) by \(H(a,e)\) gives
\(q_{x,x'}(\omega)\).  Fixed-ratio Harnack gives
\[
 \|\mu_x/C\|_\infty\le1,\quad
 \left\|{q_{x,x'}\over C(1+G(x,x'))}\right\|_\infty\le1
                                                                  \tag{67}
\]
uniformly in \(x,x'\).  Equations (43a)--(43b) identify their
exit-edge averages with the finite Green
class (47i).  Thus these, and only these, are precisely the observables
covered by (49); no jagged boundary interpolation is invoked.  The
family has at most \(CM^4\) members.  Applying (49), using
\[
 G_0/b+\varepsilon_M+Q/M=o(t_J),\qquad
 \eta_w^*=O(1),                                             \tag{67a}
\]
with \(t=t_J/C_1\), where \(C_1\) is a sufficiently large fixed
multiple of the normalizing constant in (47i), makes the corresponding
unnormalized tolerances at most those in (L1).  The estimate is uniform
over all normalized reset kernels, which are part of the joint law and
then marginalized.  It gives
\[
 P(\hbox{(L1) fails}\mid w)
 \le CM^4\exp\left\{-c{\log^2J\over(\log\log J)^2}\right\}
 =o(J^{-A}),                                                 \tag{68}
\]
because \(h=(\log J)^p=o(\log^2J/(\log\log J)^2)\).  This proves (L2).
This \(M^4\)-function simultaneous screen is used only at this lower
scale \(h=(\log J)^p\), \(1<p<2\).  The upper-bound choice
\(h=(C_h\log J)^4\) never invokes (68): Lemma
lem:terminal-feynman-kac applies the one-point exponential estimate
(50) to each \(x\), and only then takes the spatial Chernoff union bound
appearing immediately after (50).

The center-harmonic values are exact before the quantitative Green
comparison is made.  Multiplying (65)--(66) by
\(\Lambda_M(a,e)=\lambda_A(a)H(a,e)\), summing first over \(e\), and
using (44)--(45), yields
\[
\begin{split}
 \Lambda_M\mu_x&=d_x,\\
 \Lambda_Mq_{x,x'}&=
 d_xG(x,x')+d_{x'}G(x',x)
       -{\bf1}_{\{x=x'\}}d_x,\\
 \sup_{x\in V_y}|d_x-g|&\le C\varepsilon_M.                 \tag{L4}
\end{split}
\]
On a moment-regular realization, (L1), (67), and
\(\sup_{x,x'}G(x,x')\le Ch\) therefore give
\[
 \max_x\left|b^{-1}\sum_iE^{\omega_i}X_i(x)-g\right|
 \le Ct_J+O(\varepsilon_M),                                 \tag{70}
\]
and the covariance of
\[
       b^{-1/2}\sum_{i\le b}
       (X_i-E^{\omega_i}X_i)
\]
differs entrywise from \(2gG_{D_y}(x,x')\) by \(O(1)\).  Indeed the
screen error in the second moment is
\(O(t_J(1+h))=o(1)\), the diagonal term in (L4) is bounded, and
\[
 b^{-1}\sum_i
 E^{\omega_i}X_i(x)E^{\omega_i}X_i(x')
\]
is bounded by the uniform bound on (65).  This proves the asserted
covariance identification without an unproved angular-centering step.

We use the following external Gaussian approximation with all quantities
specified.  Chernozhukov--Chetverikov--Kato, Empirical and multiplier
bootstraps for suprema of empirical processes of increasing complexity,
and related Gaussian couplings,
paper_id ChernozhukovChetverikovKato2015,
arXiv id 1502.00352, Theorem 3.1, states: if
\(Z_i\in\mathbb R^P\), \(1\le i\le b\), are independent with finite
absolute third moments, \(\widetilde Z_i=Z_i-EZ_i\), and
\[
 Z=\max_{j\le P}b^{-1/2}\sum_i Z_{ij},
\]
while \(Y_i\) are independent Gaussian vectors with the same means and
covariances and
\(\widetilde Z=\max_{j\le P}b^{-1/2}\sum_iY_{ij}\), then for every
Borel \(A\subset\mathbb R\) and \(\delta>0\),
\[
 P(Z\in A)\le P(\widetilde Z\in A^{C_7\delta})
 +\frac{C_8\log^2P}{\delta^3\sqrt b}
       \{L_b+M_{b,Z}(\delta)+M_{b,Y}(\delta)\},                \tag{69}
\]
where
\[
 L_b=\max_jb^{-1}\sum_iE|\widetilde Z_{ij}|^3,
\]
\[
 M_{b,Z}(\delta)=b^{-1}\sum_i
 E\left[\max_j|\widetilde Z_{ij}|^3;
       \max_j|\widetilde Z_{ij}|>\delta\sqrt b/\log P\right],
\]
and \(M_{b,Y}\) is the analogous Gaussian quantity.  The constants are
universal.

Here \(P=|V_y|=e^{2h+O(1)}\).  The rank-one formula (42) supplies the
needed uniform tails, including their small prefactor.  At
\(\theta=c_0/h\), with \(c_0\) fixed small, (39) gives
\(r_\theta\le C/h\); hence, for every endpoint pair,
\[
 E^\omega(e^{\theta X(x)}-1)=r_\theta\mu_x(\omega)\le C/h.
\]
Therefore
\[
 P^\omega(X(x)>s)\le Ch^{-1}e^{-cs/h},\qquad
 E^\omega|X(x)-E^\omega X(x)|^3\le Ch^2.                    \tag{71}
\]
Thus \(L_b=O(h^2)\).  At the CCK truncation level
\[
       T={\sqrt b\over\log P}\asymp {J\over h},
\]
a union bound and integration of (71) give
\[
\begin{split}
b^{-1}\sum_iE^\omega\!\left[
 \max_x|\widetilde X_i(x)|^3;\max_x|\widetilde X_i(x)|>T
\right]
\le \exp\{-cJ/h^2+Ch\}.                                     \tag{72}
\end{split}
\]
For the matching Gaussian vector,
\(\max_x\operatorname {Var}(X_i(x))\le Ch\), by the second derivative
of (42), and the Gaussian union bound gives the still smaller
\(\exp\{-cJ^2/h^3+Ch\}\).  Taking \(\delta=1\) in the quoted CCK theorem,
whose \(\log^2P\) factor is \(O(h^2)\), proves that its error is
\[
       O(h^4/J)+\exp\{-cJ/h^2+Ch\}=o(1).                     \tag{73}
\]

Let \(\Gamma=(\Gamma_x:x\in V_y)\) be the centered Gaussian vector with
the covariance of the normalized bridge sum.  By (L4) and (70),
\[
 \max_{x,x'}\left|
 \operatorname {Cov}(\Gamma_x,\Gamma_{x'})
       -2gG_{D_y}(x,x')\right|\le C.                         \tag{74}
\]
The required DGFF input is the following complete maximum statement.
Biskup--Louidor, Full extremal process, cluster law and freezing for the
two-dimensional discrete Gaussian free field,
paper_id BiskupLouidor2016FullExtremalProcess,
arXiv id 1606.00510, display (1.2), Theorem 2.1, and display (1.8),
states the following.  For lattice approximations \(D_M\) of any bounded
regular planar domain, the full extremal process of the zero-boundary
DGFF converges to the Poisson cluster process in Theorem 2.1; in
particular, for every nonempty open \(A\Subset D\), the maximum over
\(MA\cap D_M\), centered by
\[
 m_M=2\sqrt g\log M-\frac34\sqrt g\log\log M,
\]
converges in law to a finite nondegenerate limit, whose distribution is
given by (1.8) with the random measure \(Z^D(A)>0\) almost surely.
Applying this to the disk \(D_y\) and its fixed inner subdisk \(V_y\)
gives
\[
       \max_{x\in V_y}\phi_x
       =2\sqrt g\,h+O_P(\log h).                              \tag{75}
\]
The expectation used next does not follow from convergence in law
alone.  That convergence puts every median of the maximum at
\(m_M+O(1)\).  The maximum coordinate variance is \(O(h)\), and the
two-sided Borell inequality puts its mean within \(O(\sqrt h)\) of its
median.  Consequently
\[
 E\max_{x\in V_y}\phi_x=2\sqrt g\,h+O(\sqrt h).              \tag{75a}
\]
For completeness, if
\(F_\lambda(z)=\lambda^{-1}\log\sum_xe^{\lambda z_x}\), Gaussian
interpolation and differentiation under the integral give
\[
 |E F_\lambda(\Gamma)-EF_\lambda(\sqrt{2g}\phi)|
 \le C\lambda\max_{x,x'}|\Delta\operatorname {Cov}(x,x')|.
\]
Also \(0\le F_\lambda(z)-\max_xz_x\le\lambda^{-1}\log P\).
Choosing \(\lambda=\sqrt{\log P/C}\) in (74) yields
\[
 |E\max_x\Gamma_x-E\max_x\sqrt{2g}\phi_x|\le C\sqrt{\log P}.
                                                                    \tag{76}
\]
Both fields have maximal coordinate variance \(O(h)\), so Borell's
Gaussian concentration inequality adds \(O_P(\sqrt h)\).  Thus
\[
       \max_x\Gamma_x=2\sqrt2\,g h+O_P(\sqrt h+\log h).       \tag{77}
\]
Apply the CCK inequality first with \(A=(-\infty,t]\) and then with
\(A=[t,\infty)\).  In both cases its enlargement is by a fixed constant
and its error tends to zero by (73).  At every continuity point of the
Gaussian maximum the two half-line bounds transfer its upper- and
lower-tail localization to the normalized centered bridge maximum.
Since (77) has fluctuations \(O_P(\sqrt h+\log h)=O_P(\sqrt h)\), the
bridge maximum has the same leading term with an \(O_P(\sqrt h)\)
remainder.  No pathwise coupling of the two maxima is asserted.

Finally (70) says, uniformly in \(x\),
\[
 \sum_iE^{\omega_i}X_i(x)=gb+
 O\left({J\log J\over\log\log J}\right).
\]
Multiplying (77) by \(\sqrt b=O(J)\) and adding these conditional means
gives the asserted terminal formula (L3).

Finally, (63) implies
\[
\begin{split}
 gb+2\sqrt2\,g\sqrt b\,h
 &=2gJ^2-2gJ\log J\\
 &\quad{}+O(h^2+h\log J+J).                                  \tag{73}
\end{split}
\]
Because \(p<2\), both the deterministic error in (73) and the stochastic
error in (L3) are \(o(J\log J)\).  The gap from
\(u_{J,2+\eta}\) is \(\eta gJ\log J\), proving the last assertion.

# proposition prop:disk-maximum-lower

## statement

For every fixed \(\eta>0\), there is \(p_\eta>0\) such that, for all
large \(J\),
\[
       P\left(M_{\tau_{e^J}}\ge u_{J,2+\eta}\right)
       \ge p_\eta.                                           \tag{74}
\]

## proof

Use \(h=(\log J)^p\), \(1<p<2\), and \(L=J-h\).  Apply the lower-root
construction (32)--(38) at depth \(L\), with terminal physical radius
\(M=e^h\), restricting the centers to a fixed compact subdisk so that
their enlarged terminal domains lie inside \(D(0,e^J)\).  The restriction
retains a fixed positive area fraction and all estimates are uniform.
The truncated endpoint band in (37) is
\[
 \sqrt{2T_L}\in[\rho_LL+z_0,\rho_LL+z_0+C_*],
\]
and hence gives exactly (63).

Lemma lem:buffered-transfer transfers the union-existence probability
directly, using Rosen's pair estimate only on the Brownian side.
For each root the terminal pieces are ordered separately inside the
\(m_0\) source intervals; the exposed inter-source connectors are not
part of any endpoint chain.  Their omitted occupation can only increase
the full-walk maximum, so this deletion is harmless for the lower bound.
Its final count assertion together with (L2) gives, for the lattice
coarse-root count
\(Z_L^S\),
\[
       P(Z_L^S>0)\ge p_0,\qquad EZ_L^S\le C,                  \tag{78}
\]
and
\[
\begin{split}
E\sum_y{\bf1}_{I_y^{S,\circ}}
 {\bf1}_{\{\text{the endpoints at }y\text{ are not moment regular}\}}
\le \epsilon_J E\widehat Z_L^S=o(1),                        \tag{79}
\end{split}
\]
where \(\widehat Z_L^S\) is the count obtained by retaining the radial
barrier and endpoint band but dropping every angular screen.  Indeed,
the scalar radial-word comparison (39d), followed by Rosen Appendix
Theorem 9.1(a), gives uniformly in \(y\)
\[
       P(\widehat I_y^{S,\circ})\le Ce^{-2L},
       \qquad E\widehat Z_L^S\le C                         \tag{79a}
\]
because the deterministic net has \(O(e^{2L})\) points.  Conditional on
each complete radial word counted by \(\widehat Z_L^S\), (L2) bounds the
moment-regularity failure by the same \(\epsilon_J=o(J^{-A})\).
Summing first over words and then over centers proves (79).  Notice that
this uses the unscreened radial-root mass; it does not multiply a
radial-word conditional estimate by the smaller screened-root mass.
Thus with probability at least \(p_0-o(1)\) there is a
moment-regular lattice root.  No lattice pair estimate and no
conditioning on the KMT-success event is present in (78)--(79).

For a fixed root \(y\), let \({\cal C}_y\) be generated by the exterior
path together with all entrance and directed-exit pairs after deleting
the completed pieces inside \(D_y\).  The event \(G_y\) that \(y\) is a
moment-regular coarse root is \({\cal C}_y\)-measurable, and conditionally on
\({\cal C}_y\) the deleted paths are the independent killed bridges used
in Lemma lem:terminal-maximum-lower.  We do not select a root before
conditioning.  If \(A_y\) is terminal success, that lemma gives a
deterministic \(\widetilde\epsilon_J\downarrow0\) with
\[
 P(G_y\cap A_y^c)
 =E[{\bf1}_{G_y}P(A_y^c\mid{\cal C}_y)]
 \le\widetilde\epsilon_JP(G_y).                              \tag{80}
\]
Consequently
\[
\begin{split}
 P(\exists y:G_y\cap A_y)
 &\ge P(\exists y:G_y)-\sum_yP(G_y\cap A_y^c)\\
 &\ge p_0-o(1)-\widetilde\epsilon_J EZ_L^S
 \ge p_0/2.                                                   \tag{81}
\end{split}
\]
The sum uses only a union bound, so disjoint terminal disks are not
needed; each summand uses its own intrinsic bridge disintegration.  On
this event (74) follows from the terminal expansion in Lemma
lem:terminal-maximum-lower.  This proves the proposition.

# proposition prop:deterministic-maximum-lower

## statement

Let \(N_j=\lfloor e^{2j}\rfloor\).  For every \(\eta>0\), almost surely,
\[
       M_{N_j}\ge u_{j,2+\eta}
\]
for all sufficiently large \(j\).

## proof

Fix \(0<\delta<\eta\) and \(a>0\) so small that
\(\delta+2a<\eta\).  Proposition prop:disk-maximum-lower and
Lemma lem:elementary-walk-estimates give a disk-success probability
\(p_\delta>0\).  Choose the fixed \(C\) so large that
\[
       \sup_R P_0(\tau_R>CR^2)\le p_\delta/2.
\]
Translation invariance then implies that a walk segment of length
\(CR^2\), from any starting point, has within-segment maximum local time
at least
\[
       u_{\log R,2+\delta}
\]
with probability at least \(p:=p_\delta/2\), uniformly for large \(R\).

Partition the first \(N_j\) increments into
\[
       q_j=\lfloor(\log N_j)^a\rfloor
\]
disjoint blocks of equal length \(m_j\), ignoring a remainder.  Translated
increment paths in these blocks are independent, and their within-block
local times are lower bounds for the full local times.  Choose
\[
       \log R_j=\frac12\log(m_j/C)
       =j-\frac a2\log j+O(1).
\]
A direct expansion gives
\[
       u_{\log R_j,2+\delta}
       =u_{j,\,2+\delta+2a+o(1)}
       \ge u_{j,2+\eta}                                      \tag{78}
\]
for large \(j\).  Therefore
\[
       P(M_{N_j}<u_{j,2+\eta})
       \le(1-p)^{q_j}\le e^{-c j^a}.                          \tag{79}
\]
The right side is summable, and Borel--Cantelli proves the statement.

# proposition prop:supercritical-escape

## statement

For every \(\gamma>\tfrac12\), almost surely,
\[
       \liminf_{n\to\infty}
       \frac{R_n^-}{\sqrt n/(\log n)^\gamma}=\infty.          \tag{80}
\]

## proof

Fix \(\gamma>1/2\) and a positive integer spatial multiplier \(A_0\).
Choose
\[
       0<\delta<\frac{2\gamma-1}{4}.
\]
For \(N_j=e^{2j}\), Proposition prop:deterministic-maximum-lower gives,
eventually,
\[
       M_{N_j}\ge u_{j,2+\delta}.                             \tag{81}
\]

Consider any \(n\in[N_j,N_{j+1}]\).  If a favorite at time \(n\) lies in
\[
       B\left(0,A_0\frac{\sqrt n}{(\log n)^\gamma}\right),
\]
then, by monotonicity of local times and (81), at time \(N_{j+1}\) some
site in
\[
       B\left(0,C_{A_0}e^{j+1}j^{-\gamma}\right)             \tag{82}
\]
has local time at least \(u_{j,2+\delta}\).

Take
\[
       K_j=C_*e^{j+1}\sqrt{\log j},\qquad J'_j=\log K_j.
\]
By the maximal inequality in Lemma lem:elementary-walk-estimates, \(C_*\)
can be chosen so that
\[
       \sum_jP(\tau_{K_j}\le N_{j+1})<\infty.                 \tag{83}
\]
For large \(j\), the ball (82) is contained in
\[
       B(0,K_j(J'_j)^{-\gamma}).
\]
Moreover \(J'_j=j+O(\log\log j)\), and the fixed extra coefficient
\(\delta\) gives
\[
       u_{j,2+\delta}\ge u_{J'_j,2+2\delta}                  \tag{84}
\]
for all large \(j\): the negative term
\(-\delta g j\log j\) dominates the \(O(j\log\log j)\) change in the
leading term.

Choose independently an upper-error exponent \(A_{\rm err}>2\).
On the complement of the summable event in (83), the implication
(81)--(84) and Proposition prop:localized-disk-upper, with
\(\beta=\gamma\) and \(c=2+2\delta\), show that the probability of any
such \(n\) in the whole block is at most
\[
       (J'_j)^{-2\gamma+2\delta+o(1)}+O(j^{-A_{\rm err}}).     \tag{85}
\]
Our choice of \(\delta\) makes the power in (85) strictly smaller than
\(-1\).  Hence (85) is summable.  Borel--Cantelli proves that eventually
no favorite in the \(j\)-th block lies in the ball with multiplier \(A_0\).
Intersecting over \(A_0\in\mathbb N\) proves (80).

# theorem main:precise-escape-rate

## statement

# Precise escape rate of planar favorite sites

Let \((S_k)_{k\ge0}\) be the simple symmetric random walk on \(\mathbb Z^2\), started at the origin, and define
\[
L_n(x)=\sum_{k=0}^{n}\mathbf 1_{\{S_k=x\}},
\qquad
\mathcal F_n=\left\{x\in\mathbb Z^2:L_n(x)=\max_{y\in\mathbb Z^2}L_n(y)\right\}.
\]

Write
\[
R_n^-:=\min_{x\in\mathcal F_n}\|x\|_2,
\qquad
R_n^+:=\max_{x\in\mathcal F_n}\|x\|_2,
\]
and, for \(n\ge3\) and \(\gamma\in\mathbb R\), set
\[
a_\gamma(n):=\frac{\sqrt n}{(\log n)^\gamma}.
\]

Determine the **precise almost-sure lower-class escape rate** of the planar
favorite-point set, in analogy with the one-dimensional favorite-site theorem.
In particular, decide whether there exists a critical exponent
\(\gamma_2\in\mathbb R\) such that, almost surely,
\[
\liminf_{n\to\infty}\frac{R_n^-}{a_\gamma(n)}=\infty
\qquad\text{for every }\gamma>\gamma_2,
\]
whereas
\[
\liminf_{n\to\infty}\frac{R_n^+}{a_\gamma(n)}=0
\qquad\text{for every }\gamma\le\gamma_2.
\]
If no logarithmic-power normalization \(a_\gamma\) gives the correct
dichotomy, identify the correct deterministic gauge (or gauge class) and prove
the corresponding sharp lower-class law, including the critical case.

A solution must determine the slowly varying correction to the diffusive scale.
The coarse statement
\[
R_n^-=n^{1/2+o(1)}
\]
alone does **not** solve the problem.

References:

1. Chenxu Hao, Xinyi Li, Izumi Okada, and Yushu Zheng, “Favorite sites for
   simple random walk in two and more dimensions,” *Probability Theory and
   Related Fields*, 2025, Remark 1.4(1), DOI:
   10.1007/s00440-025-01441-1, arXiv:2409.00995,
   https://doi.org/10.1007/s00440-025-01441-1.
2. Richard F. Bass, “The rate of escape of the most visited site of Brownian
   motion,” *Electronic Journal of Probability* 28 (2023), 1–12,
   Theorem 2.2 (the one-dimensional benchmark), DOI: 10.1214/23-EJP916,
   arXiv:1303.2040, https://doi.org/10.1214/23-EJP916.

## proof

The critical exponent exists and is
\[
                         \boxed{\gamma_2=\frac12}.
\]
Indeed, Proposition prop:supercritical-escape proves, simultaneously for
every \(\gamma>1/2\),
\[
       \liminf_{n\to\infty}\frac{R_n^-}{a_\gamma(n)}=\infty
       \qquad\hbox{almost surely}.
\]
Proposition prop:critical-recurrence proves, simultaneously for every
\(\gamma\le1/2\),
\[
       \liminf_{n\to\infty}\frac{R_n^+}{a_\gamma(n)}=0
       \qquad\hbox{almost surely}.
\]
The countable simultaneous formulation follows first for rational
\(\gamma\) and then for all real \(\gamma\) by monotonicity of
\(a_\gamma\).  Thus the slowly varying correction is exactly
\((\log n)^{-1/2}\), including the critical case.
