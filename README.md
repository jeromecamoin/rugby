# Lame & Cartes — Les Terres Sauvages

Un jeu web en un seul fichier (`index.html`) : un FPS médiéval-fantastique en
pixel art où l'on combat **en temps réel avec un deck de cartes**, façon
rogue-lite. Mélange de *Slay the Spire* et d'un RPG d'action en vue première
personne.

## Jouer

Ouvrez simplement `index.html` dans un navigateur (Chrome/Firefox/Edge),
ou servez le dossier :

```sh
python3 -m http.server 8000
# puis http://localhost:8000
```

## Principe

- Vous explorez une lande sauvage en vue première personne (moteur raycasting,
  sprites 2D, tout est généré par code — aucun fichier externe).
- Les monstres (gobelins, squelettes archers, orcs, troll-boss) vous attaquent
  **en direct**, comme dans un RPG d'action.
- Vous, vous jouez des **cartes** tenues en main par votre héros : attaques,
  défenses, bonus, mouvements. Chaque carte coûte de l'énergie (qui se recharge
  avec le temps). La main se re-pioche automatiquement depuis le deck ; la
  défausse est remélangée quand le deck est vide.
- Après chaque vague, choisissez une nouvelle carte à ajouter à votre deck
  (rogue-lite). La mort termine la partie : on recommence à la vague 1.

## Commandes

| Action | Touche |
|---|---|
| Se déplacer | ZQSD / WASD / flèches |
| Regarder | Souris |
| Jouer une carte | 1‑6, ou clic gauche (carte sélectionnée) |
| Sélectionner une carte | Molette |
| Défausser (re-pioche auto) | Clic droit ou F |
| Pause | Échap |

## Cartes

- **Attaque** : Taillade, Coup Puissant, Couteau, Boule de Feu, Éclair, Tourbillon
- **Défense** : Bouclier, Muraille, Parade (renvoie la mêlée)
- **Bonus** : Potion, Rage, Inspiration (pioche 2)
- **Mouvement** : Ruée (dash offensif, esquive), Pas Arrière, Hâte

---

Le dépôt contient aussi `rugby_game.html`, un jeu de rugby indépendant.
