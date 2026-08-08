# Changelog — Tableau périodique interactif

Toutes les versions notables du programme sont listées ici, de la plus récente à la plus ancienne, avec le raisonnement derrière chaque changement.

## v11
- **Corrigé** : la case active (halo) passait derrière ses voisines de droite/dessous, la faisant paraître incomplète.
- **Pourquoi** : les cases suivantes dans le tableau (plus tardives dans le code HTML) étaient peintes par-dessus le halo. Ajout d'un `z-index` sur la case active pour qu'elle passe systématiquement au premier plan, peu importe sa position dans le tableau.

## v10
- **Ajouté** : mise en évidence visuelle de la case en cours de réponse (cadre violet + halo qui pulse brièvement puis se stabilise).
- **Pourquoi** : après un passage automatique à la case suivante (ou un défilement), rien n'indiquait clairement quelle case était concernée par la question affichée.

## v9
- **Corrigé** : le champ de saisie de la réponse dépassait de la boîte de dialogue sur mobile.
- **Pourquoi** : le champ n'avait pas de largeur fixe. Largeur fixée à 80px, centrée, avec `box-sizing: border-box` pour rester dans les marges quelle que soit la taille d'écran.

## v8
- **Corrigé** : sur mobile, l'ouverture du clavier pouvait faire défiler la page trop loin et couper la case sélectionnée en haut de l'écran.
- **Pourquoi** : c'est le navigateur qui, par défaut, fait défiler la page pour remonter le champ actif au-dessus du clavier — un comportement natif indépendant de notre code, et qui pouvait surcompenser. Utilisation de `focus({preventScroll: true})` pour désactiver ce défilement automatique tout en gardant le clavier fonctionnel.

## v7
- **Corrigé** : le défilement vertical de la page était bloqué en orientation paysage sur mobile.
- **Pourquoi** : la propriété `touch-action: pan-x` empêchait explicitement tout défilement vertical dès que le doigt touchait la zone du tableau. Élargie à `pan-x pan-y`.
- **Ajouté** : taille de case réduite automatiquement en orientation paysage sur écran court, pour voir plusieurs périodes sans défilement vertical.
- **Ajouté** : sur mobile, la boîte de dialogue apparaît désormais juste à côté de la case cliquée (position flottante calculée), au lieu d'être placée sous le tableau et de nécessiter un défilement pour la voir.
- **Modifié** : le défilement automatique vers une case ne se déclenche plus que si la case n'est pas déjà visible à l'écran, pour limiter les sauts de défilement.
- **Modifié** : fond de page enrichi (dégradé discret + motif de points), le fond précédent étant jugé trop sobre.

## v6
- **Corrigé** : sur PC, le tableau et la barre latérale n'étaient plus centrés (tableau collé à gauche, barre collée à droite avec un grand vide au milieu).
- **Pourquoi** : la barre latérale n'avait pas de largeur fixe, et le tableau, en flex-grow, occupait toute la largeur disponible au lieu de se limiter à son contenu.
- **Corrigé** : le fond avait disparu (uni gris) suite à un nettoyage trop agressif en v5 ; réintroduction d'un fond discret (motif de points).
- **Modifié** : boîte de dialogue repositionnée en flux normal juste sous le tableau (au lieu d'une position fixe en bas d'écran), pour s'adapter automatiquement à la hauteur du tableau (mode normal vs étendu avec sa 7e période).
- **Modifié** : taille de case uniformisée entre le mode normal et le mode étendu (60px partout), le mode étendu s'appuyant sur le défilement horizontal plutôt que sur des cases réduites.

## v5
- **Corrigé** : sur PC, le tableau en mode normal était coupé (visible jusqu'à la 5ᵉ colonne environ) à cause d'une largeur de page trop contrainte (`max-width: 1100px`) mal dimensionnée par rapport au contenu réel.
- **Ajouté** : recentrage automatique (`scrollIntoView`) sur la case en cours de réponse, pour éviter de répondre à une case qui n'est plus affichée à l'écran après un passage automatique.
- **Corrigé** : ajout de la balise `<meta name="viewport">`, absente jusque-là — cause probable de l'affichage vide constaté sur mobile.

## v4
- **Ajouté** : la période 7 (Fr → Og) dans le mode étendu, complétant le tableau à 118 éléments.
- **Modifié** : boîte de dialogue déplacée en bas de l'écran (au lieu d'un centrage qui recouvrait le tableau), avec une croix pour la fermer sans répondre.
- **Ajouté** : défilement horizontal tactile natif (`overflow-x: auto`) pour naviguer dans le tableau sur mobile, sans développement spécifique côté application.

## v3
- **Corrigé** : la casse du symbole tapé est désormais forcée en temps réel (1ère lettre majuscule, 2e minuscule), sans avoir besoin d'appuyer sur Shift.
- **Ajouté** : repère visuel (bordure épaisse) entre le baryum (Ba) et le lutécium (Lu) en mode normal, pour signaler que les lanthanides (La–Yb) sont masqués à cet endroit.
- **Ajouté** : mode étendu activable (bouton), affichant le bloc f entre le bloc s et le bloc d (forme longue à 32 colonnes), portant le total à 86 éléments (lanthanides inclus, avant l'ajout de la période 7 en v4).
- **Modifié** : animation de réussite remplacée par une pluie de confettis suivie d'un fondu-zoom de la fenêtre de résumé (au lieu de l'ancien effet "feux d'artifice").

## v2
- Version de base : tableau à 72 éléments (périodes 1–6), lutécium placé en groupe 3 (recommandation IUPAC 2021), sans lanthanides ni actinides affichés.
