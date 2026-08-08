# Changelog — Simulation de mouvement brownien / diffusion

## v3
- **Ajouté** : axe des vitesses de l'histogramme rendu fixe (indépendant du réglage de vitesse moyenne), pour que le déplacement du profil de vitesses reste visible quand on augmente l'énergie du système.
  - *Pourquoi* : avec un axe recalculé à chaque changement de réglage, la distribution paraissait toujours de la même largeur relative — l'effet de l'augmentation de vitesse n'était donc pas visible.
- **Ajouté** : histogramme en barres empilées bleu/rouge, reflétant la proportion réelle de chaque couleur par tranche de vitesse.
  - *Pourquoi* : illustrer que la vitesse d'une molécule est indépendante de sa couleur (l'énergie se répartit sans distinction de "qui est qui").
- **Ajouté** : ligne pointillée verticale séparant l'enceinte de gaz en deux moitiés.
- **Ajouté** : panneau affichant en direct le pourcentage de molécules bleues dans chaque moitié de l'enceinte, pour visualiser la convergence vers 50/50 lors de la diffusion.

## v2
- **Corrigé** : l'histogramme de distribution des vitesses ne faisait apparaître aucune forme caractéristique reconnaissable.
  - *Pourquoi* : l'axe des vitesses était recalculé à chaque image (frame), ce qui faisait "trembler" l'histogramme en permanence : impossible de voir une forme se stabiliser.
- **Ajouté** : lissage sur une fenêtre glissante de 20 secondes (au lieu d'un instantané à chaque frame), avec réinitialisation automatique de l'accumulation dès qu'un réglage change (nombre de molécules ou vitesse).
- **Ajouté** : courbe théorique de Maxwell-Boltzmann en 2D (loi de Rayleigh) superposée à l'histogramme mesuré, calculée à partir de la vitesse moyenne réellement observée dans la simulation.

## v1 (fichier d'origine fourni par l'utilisateur)
- Simulation de particules en mouvement brownien avec collisions élastiques, réglages du nombre de molécules et de la vitesse moyenne, boutons pause/colorer une moitié/tout recolorer en bleu, et histogramme de distribution des vitesses (non lissé, axe instable).
