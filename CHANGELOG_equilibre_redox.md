# Changelog — Équilibrage de réactions rédox

## v2
- **Corrigé** : le bouton "Suivant" ne s'affichait jamais (resté en `display: none` en permanence), obligeant à deviner qu'il fallait cliquer sur la case suivante dans la grille de progression pour continuer. Il s'affiche désormais après une bonne réponse ou après épuisement des tentatives.
- **Corrigé** : équation n°4 — un "2" était collé en dur dans le texte de l'équation en plus de la case à remplir, produisant un affichage confus ("[case] 2MnO₄⁻" au lieu de "[case] MnO₄⁻").
- **Corrigé** : équation n°14 — simplifiée de `ClO₃⁻ + SO₃²⁻ + H⁺ → Cl⁻ + SO₄²⁻ + H⁺` à `ClO₃⁻ + SO₃²⁻ → Cl⁻ + SO₄²⁻` ; les H⁺ apparaissaient à l'identique des deux côtés de l'équation (donc redondants) au lieu de s'annuler.
- **Ajouté** : statistiques enrichies — "Premier coup" / "Après plusieurs essais" / "Échecs" (au lieu d'un simple compteur bonnes/mauvaises réponses), sur le même principe que le quiz de nomenclature.
- **Ajouté** : récapitulatif de fin de partie listant les équations ratées et celles réussies après plusieurs essais.
- **Choix délibéré** : pas de vérificateur d'équilibrage général acceptant tout multiple valide des coefficients, ni d'indication du milieu acide/basique par équation — l'utilisateur souhaite que les étudiants identifient eux-mêmes le dénominateur commun et le type de milieu (présence de H⁺ ou OH⁻).

## v1 (fichier d'origine fourni par l'utilisateur)
- 20 équations rédox à équilibrer (milieux acide et basique mélangés), 3 essais par équation, grille de progression cliquable, statistiques bonnes/mauvaises réponses. Vérification (lors de l'audit du v2) : équilibrage correct pour 18 des 20 équations sur les plans atomique, électronique et de la charge.
