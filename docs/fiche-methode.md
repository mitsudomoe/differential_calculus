# Fiche méthode : calculer et justifier une différentielle

Pour chaque fonction, le but est d'expliciter $\mathrm{d}f(a)\cdot h$, puis de
**prouver** qu'il s'agit bien de la différentielle (linéarité, continuité, reste
en $o(\lVert h\rVert)$) plutôt que de le deviner.

## 1. Ce qu'il faut démontrer

Soient $E, F$ des espaces normés, $U \subset E$ un ouvert, $a \in U$ et
$f : U \to F$. Montrer que $f$ est différentiable en $a$, c'est exhiber une
application $L$ telle que

$$
f(a+h) = f(a) + L(h) + R(h),
\qquad
\frac{\lVert R(h)\rVert_F}{\lVert h\rVert_E} \xrightarrow[h \to 0]{} 0 ,
$$

et prouver trois choses sur elle :

1. **Linéarité** : $L(\lambda h + \mu k) = \lambda L(h) + \mu L(k)$.
2. **Continuité** : il existe $C$ tel que $\lVert L(h)\rVert \le C\,\lVert h\rVert$
   pour tout $h$. En dimension finie, elle est automatique.
3. **Reste négligeable** : $\lVert R(h)\rVert \le \varepsilon(h)\,\lVert h\rVert$
   avec $\varepsilon(h) \to 0$.

Alors $L$ est unique : on note $\mathrm{d}f(a) = L$, et sa valeur en $h$ s'écrit
$\mathrm{d}f(a)\cdot h$.

## 2. La démarche en six étapes

On calcule $f(a+h) - f(a)$, on trie les termes par degré en $h$, puis on prouve ce
qu'on a trouvé.

1. **Fixer le cadre.** Noter les espaces, leurs normes, le domaine et le point $a$.
    - Vérifier que le domaine est ouvert : $GL_n(\mathbb{R}) = \det^{-1}(\mathbb{R}^*)$
      l'est, car $\det$ est continu.
    - En dimension infinie, la norme fait partie de l'énoncé : changer de norme
      peut changer la réponse.
2. **Développer** $f(a+h)$ et faire apparaître $f(a)$.
3. **Trier par degré en $h$.**
    - Le terme de degré 0 est $f(a)$ ; il se simplifie.
    - Les termes de degré 1 forment le candidat $L(h)$.
    - Tout le reste, de degré $\ge 2$ ou défini comme un reste de Taylor, forme $R(h)$.
4. **Vérifier $L$.** Prouver la linéarité, puis une majoration
   $\lVert L(h)\rVert \le C\,\lVert h\rVert$ avec $C$ explicite.
5. **Majorer $R$.** Obtenir $\lVert R(h)\rVert \le C\,\lVert h\rVert^2$ (le cas le
   plus fréquent) ou $\lVert R(h)\rVert \le \varepsilon(h)\,\lVert h\rVert$ avec
   $\varepsilon(h) \to 0$.
6. **Conclure.** Écrire $\mathrm{d}f(a)\cdot h = \dots$, c'est-à-dire
   $\mathrm{d}f(a) = (h \mapsto \dots)$.

## 3. Trouver le candidat L

Quand le développement direct est pénible, on devine $L$ par une des méthodes
ci-dessous. Le résultat reste un **candidat** : les étapes 4 et 5 sont toujours à
faire.

### Dérivée directionnelle

$$
L(h) = \frac{\mathrm{d}}{\mathrm{d}t}\, f(a + t h) \Big|_{t=0}
$$

Si le résultat n'est pas linéaire en $h$, la fonction n'est pas différentiable en $a$.

### Règles opératoires

| Règle | Formule |
| --- | --- |
| Linéaire continue | $\mathrm{d}f(a) = f$, quel que soit $a$ |
| Bilinéaire continue | $\mathrm{d}B(x,y)\cdot(h,k) = B(h,y) + B(x,k)$ |
| Composée | $\mathrm{d}(g\circ f)(a) = \mathrm{d}g\big(f(a)\big)\circ\mathrm{d}f(a)$ |
| Produit (valeurs réelles) | $\mathrm{d}(fg)(a)\cdot h = (\mathrm{d}f(a)\cdot h)\,g(a) + f(a)\,(\mathrm{d}g(a)\cdot h)$ |
| Combinaison linéaire | $\mathrm{d}(f + \lambda g)(a) = \mathrm{d}f(a) + \lambda\,\mathrm{d}g(a)$ |

### Dérivées partielles (dimension finie)

Si toutes les dérivées partielles existent et sont continues au voisinage de $a$,
alors $f$ est $C^1$ et

$$
\mathrm{d}f(a)\cdot h = \sum_i \frac{\partial f}{\partial x_i}(a)\, h_i ,
$$

sans reste à majorer.

## 4. Majorer le reste

Le but est presque toujours d'arriver à $\lVert R(h)\rVert \le C\,\lVert h\rVert^2$.

| Outil | Quand | Majoration |
| --- | --- | --- |
| Cauchy–Schwarz | produits scalaires | $\lvert\langle x, y\rangle\rvert \le \lVert x\rVert\,\lVert y\rVert$ |
| Sous-multiplicativité | produits de matrices | $\lVert AHB\rVert \le \lVert A\rVert\,\lVert H\rVert\,\lVert B\rVert$ |
| Bilinéaire continue | $B(h,k)$ | $\lVert B(h,k)\rVert \le \lVert B\rVert\,\lVert h\rVert\,\lVert k\rVert$ |
| Taylor–Lagrange | composée avec $g \in C^2$ | $\lvert g(x+y) - g(x) - g'(x)\,y\rvert \le \tfrac12 \sup\lvert g''\rvert\, y^2$ |
| Série géométrique | Neumann, exponentielle | $\big\lVert \sum_{k\ge 2} M^k \big\rVert \le \lVert M\rVert^2 / (1 - \lVert M\rVert)$ si $\lVert M\rVert < 1$ |
| Intégrale | fonctionnelles sur $[0,1]$ | $\big\lvert \int \varphi \big\rvert \le \int \lvert\varphi\rvert \le \lVert\varphi\rVert_\infty$ |

Deux remarques :

- En dimension infinie, le $\sup$ de $g''$ doit être pris sur un compact qui contient
  toutes les valeurs de $u + h$. On le fixe en imposant $\lVert h\rVert \le 1$ au départ.
- Une majoration en $\lVert h\rVert^2$ n'est pas obligatoire :
  $\varepsilon(h)\,\lVert h\rVert$ avec $\varepsilon(h) \to 0$ suffit. C'est le cas
  typique quand on n'a que de la continuité uniforme sur un compact (théorème de Heine).

## 5. Montrer qu'une fonction n'est pas différentiable

Un seul argument suffit. On essaie les trois tests dans l'ordre, du plus simple au
plus fin.

1. **$f$ n'est pas continue en $a$.** Une fonction différentiable est continue. On
   cherche une suite ou une courbe le long de laquelle $f$ ne tend pas vers $f(a)$.
2. **La dérivée directionnelle n'existe pas ou n'est pas linéaire en $h$.**
   Exemple : pour $f(x) = \lvert x\rvert$ en $0$, on trouve $f(th)/t \to \lvert h\rvert$
   quand $t \to 0^+$, mais $\to -\lvert h\rvert$ quand $t \to 0^-$.
3. **Le candidat est linéaire, mais le reste n'est pas un $o(\lVert h\rVert)$.**
   C'est l'écart entre Gateaux et Fréchet. On trouve une courbe $h(t) \to 0$ le long
   de laquelle $\lVert R(h(t))\rVert / \lVert h(t)\rVert$ ne tend pas vers $0$.
   Exemple type : $\dfrac{x^3 y}{x^6 + y^2}$ le long de $y = x^3$.

## 6. Pièges fréquents

- **Erreur de type.** Écrire $\mathrm{d}f(a) = 2\langle a, h\rangle$ est faux, car
  $h$ y apparaît sans être défini. Il faut écrire
  $\mathrm{d}f(a)\cdot h = 2\langle a, h\rangle$, ou
  $\mathrm{d}f(a) = \big(h \mapsto 2\langle a, h\rangle\big)$.
- **Non-commutativité.** Avec des matrices, $XH \neq HX$ en général : on ne regroupe
  pas les termes de degré 1 comme avec des nombres.
- **$O$ au lieu de $o$.** Montrer $\lVert R(h)\rVert \le C\,\lVert h\rVert$ ne suffit
  pas : il faut que $\lVert R(h)\rVert / \lVert h\rVert$ tende vers $0$.
- **Continuité de $L$ oubliée.** Automatique en dimension finie, à prouver en
  dimension infinie.
- **Gateaux pris pour Fréchet.** Des dérivées dans toutes les directions, même
  linéaires en $h$, ne prouvent pas la différentiabilité.
- **Domaine non ouvert.** La définition exige que $a + h$ reste dans le domaine pour
  $h$ petit.
- **Norme oubliée.** En dimension infinie, une même fonctionnelle peut être
  différentiable pour une norme et pas pour une autre.

## 7. Modèle de rédaction

Exemple : $J(u) = \displaystyle\int_0^1 u'(t)^2 \,\mathrm{d}t$.

**Cadre.** $E = C^1([0,1])$ muni de
$\lVert h\rVert = \lVert h\rVert_\infty + \lVert h'\rVert_\infty$. $J$ est définie sur
$E$ tout entier, qui est ouvert. On fixe $u \in E$.

**Développement et tri.** Pour $h \in E$ :

$$
J(u+h) - J(u) = \underbrace{2\int_0^1 u' h'}_{L(h)} + \underbrace{\int_0^1 h'^2}_{R(h)}
$$

**Vérification de $L$.** $L$ est linéaire, car l'intégrale et la dérivation le sont.
Elle est continue, car

$$
\lvert L(h)\rvert \le 2\,\lVert u'\rVert_\infty\,\lVert h'\rVert_\infty \le 2\,\lVert u'\rVert_\infty\,\lVert h\rVert .
$$

**Majoration du reste.**

$$
0 \le R(h) \le \lVert h'\rVert_\infty^2 \le \lVert h\rVert^2,
\qquad\text{donc}\qquad
\frac{\lvert R(h)\rvert}{\lVert h\rVert} \le \lVert h\rVert \xrightarrow[h\to 0]{} 0 .
$$

**Conclusion.** $J$ est différentiable en tout $u \in E$, et pour tout $h \in E$ :

$$
\boxed{\;\mathrm{d}J(u)\cdot h = 2\int_0^1 u'(t)\,h'(t)\,\mathrm{d}t\;}
$$

## 8. Checklist avant de rendre

- [ ] Espaces, normes, domaine ouvert et point $a$ sont écrits explicitement.
- [ ] Le candidat $L$ ne contient que des termes de degré 1 en $h$.
- [ ] La linéarité de $L$ est justifiée.
- [ ] La continuité de $L$ est prouvée avec une constante explicite.
- [ ] Le reste est majoré par $C\,\lVert h\rVert^2$ ou par $\varepsilon(h)\,\lVert h\rVert$ avec $\varepsilon(h) \to 0$.
- [ ] La conclusion est écrite sous la forme $\mathrm{d}f(a)\cdot h = \dots$, avec $h$ dans le bon espace.
- [ ] Le résultat est vérifié sur un cas simple : dimension 1, $a = 0$, ou matrices diagonales.

Les normes citées ici sont rassemblées dans [Normes usuelles](normes-usuelles.md).
