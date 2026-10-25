# Normes usuelles

En dimension finie, toutes les normes sont équivalentes : la différentiabilité et la
différentielle ne dépendent pas de la norme choisie. En dimension infinie, la norme
fait partie de l'énoncé.

## Sur ℝⁿ

| Norme | Définition | À retenir |
| --- | --- | --- |
| $\lVert\cdot\rVert_1$ | $\sum_i \lvert x_i\rvert$ | duale de $\lVert\cdot\rVert_\infty$ |
| $\lVert\cdot\rVert_2$ (euclidienne) | $\big(\sum_i x_i^2\big)^{1/2} = \langle x, x\rangle^{1/2}$ | Cauchy–Schwarz : $\lvert\langle x, y\rangle\rvert \le \lVert x\rVert_2\,\lVert y\rVert_2$ |
| $\lVert\cdot\rVert_\infty$ | $\max_i \lvert x_i\rvert$ | majorations terme à terme |

Inégalités entre ces normes, à savoir retrouver :

$$
\lVert x\rVert_\infty \le \lVert x\rVert_2 \le \lVert x\rVert_1 \le \sqrt{n}\,\lVert x\rVert_2 \le n\,\lVert x\rVert_\infty .
$$

## Sur les matrices Mₙ(ℝ)

| Norme | Définition | À retenir |
| --- | --- | --- |
| Subordonnée | $\sup_{x \neq 0} \lVert Ax\rVert / \lVert x\rVert$ | sous-multiplicative ; $\lVert Ax\rVert \le \lVert A\rVert\,\lVert x\rVert$ ; $\lVert I\rVert = 1$ |
| Frobenius | $\big(\sum_{i,j} a_{ij}^2\big)^{1/2} = \sqrt{\operatorname{tr}(A^{\mathsf T} A)}$ | sous-multiplicative, mais $\lVert I\rVert_F = \sqrt{n}$ |
| $\max_{i,j} \lvert a_{ij}\rvert$ | plus grand coefficient | **pas** sous-multiplicative : à éviter pour les produits |

## Sur les espaces de fonctions

| Espace | Norme | Définition | À retenir |
| --- | --- | --- | --- |
| $C^0([a,b])$ | $\lVert\cdot\rVert_\infty$ (uniforme) | $\sup_t \lvert f(t)\rvert$ | complète ; majore les intégrales |
| $C^0([a,b])$ | $\lVert\cdot\rVert_1$, $\lVert\cdot\rVert_2$ | $\int \lvert f\rvert$, $\big(\int f^2\big)^{1/2}$ | non complètes, non équivalentes à $\lVert\cdot\rVert_\infty$ |
| $C^1([a,b])$ | norme $C^1$ | $\lVert f\rVert_\infty + \lVert f'\rVert_\infty$ | contrôle $f$ et $f'$ ; complète |

Sur $C^0([0,1])$, on a seulement

$$
\lVert f\rVert_1 \le \lVert f\rVert_2 \le \lVert f\rVert_\infty ,
$$

sans réciproque possible : $f_k(t) = t^k$ donne $\lVert f_k\rVert_1 = \frac{1}{k+1} \to 0$
alors que $\lVert f_k\rVert_\infty = 1$.

## Sur les applications linéaires et bilinéaires

| Objet | Norme | Définition | À retenir |
| --- | --- | --- | --- |
| $\mathcal{L}(E,F)$ | norme d'opérateur | $\sup_{h \neq 0} \lVert L(h)\rVert / \lVert h\rVert$ | $\lVert L(h)\rVert \le \lVert L\rVert\,\lVert h\rVert$ : c'est le $C$ de l'étape 4 |
| Bilinéaires sur $E \times F$ | norme de $B$ | $\sup \lVert B(h,k)\rVert / (\lVert h\rVert\,\lVert k\rVert)$ | $\lVert B(h,k)\rVert \le \lVert B\rVert\,\lVert h\rVert\,\lVert k\rVert$ |
