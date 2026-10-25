# Calcul différentiel

Notes de travail et fiches méthode de calcul différentiel, du cadre des espaces
normés jusqu'aux fonctionnelles en dimension infinie.

L'objet central est la **différentielle de Fréchet** : l'application linéaire
continue $\mathrm{d}f(a)$ qui approche $f$ au voisinage de $a$,

$$
f(a+h) = f(a) + \mathrm{d}f(a)\cdot h + o(\lVert h\rVert).
$$

## Contenu

| Page | Ce qu'on y trouve |
| --- | --- |
| [Fiche méthode](fiche-methode.md) | La démarche en six étapes pour expliciter $\mathrm{d}f(a)\cdot h$ et prouver que c'est bien la différentielle, les outils de majoration, les pièges et un modèle de rédaction |
| [Normes usuelles](normes-usuelles.md) | Les normes sur $\mathbb{R}^n$, les matrices, les espaces de fonctions et les applications linéaires, avec leurs inégalités |

## Version imprimable

La fiche existe aussi en PDF, au format A4 :
[Fiche-methode-differentielle.pdf](Fiche-methode-differentielle.pdf).
Le source LaTeX est [fiche-methode.tex](fiche-methode.tex).

## Construire le site

Les pages s'affichent directement sur GitHub. Pour le site complet :

```sh
pip install -r docs/requirements.txt
mkdocs serve
```
