# RED DEATH — Document de Direction Créative

> Shooter d'exploration isométrique — survie, tension, loot
> Univers inspiré de *Le Masque de la Mort Rouge* d'Edgar Allan Poe

**Rôle du document :** transformer le concept en systèmes cohérents, lisibles et réalisables. Chaque proposition vise un équilibre entre **identité forte** (Poe + calligraphie vivante) et **faisabilité de production** (systèmes simples, expressifs, mesurables).

**Phrase-pilier (north star) :**
> *Plus tu restes, plus le monde t'écrit dedans.*

Le temps est la ressource centrale. Tout le design tourne autour d'une seule tension : **explorer vite mais incomplet, ou rester et se corrompre.**

---

## 1. GAMEPLAY

### 1.1 Boucle de gameplay principale (macro)

Structure en **expéditions** (runs) dans un manoir/domaine décadent, découpé en ailes (niveaux).

```
PRÉPARATION (hub sûr)
   └─ Réparer la combinaison, dépenser le loot, choisir l'aile cible
      ↓
ENTRÉE DANS L'AILE (la jauge de contamination commence à monter)
   └─ EXPLORER → trouver loot / fragments / leviers
   └─ ÉVITER ou ENGAGER les ennemis (combat rare, coûteux)
   └─ GÉRER la dégradation de la combinaison
      ↓
POINT DE DÉCISION RÉCURRENT : « je pousse plus loin, ou je m'extrais ? »
      ↓
EXTRACTION (porte de sortie) OU MORT (perte partielle du loot non sécurisé)
      ↓
RETOUR HUB → on recommence, plus équipé, l'aile suivante est plus hostile
```

**Principe d'or :** la boucle ne se gagne pas par le combat, elle se gagne par la **gestion du risque temporel**. Le joueur n'est jamais « bloqué par un mur d'ennemis » ; il est pressé par sa propre jauge.

### 1.2 Boucle minute par minute (micro) — l'expérience de tension

Objectif : que le joueur ressente une **pression croissante et lisible** sur ~8–12 min par aile.

| Temps | État de la combinaison | Ressenti visé | Décision typique du joueur |
|---|---|---|---|
| 0–2 min | Intacte, contamination basse | Confiance, exploration libre | « J'ouvre tout, je fouille » |
| 2–5 min | Premières dégradations | Vigilance | « Je priorise les bonnes salles » |
| 5–8 min | Combinaison usée, contamination ½ | Stress | « Je cherche une sortie ou une réparation » |
| 8–10 min | Visières fissurées, contamination haute | Urgence | « Je sacrifie du loot pour survivre » |
| 10+ min | Seuil critique | Panique contrôlée | « Je cours vers l'extraction » |

**Règle de design :** la tension doit être **auto-infligée**. Le joueur décide de rester pour le loot ; le jeu ne fait que rendre visible le coût. C'est le moteur émotionnel du jeu.

### 1.3 Le « risk/reward » spatial : la Profondeur

Chaque aile est conçue en **anneaux de profondeur** : plus on s'enfonce, plus le loot est riche **et** plus la contamination ambiante monte vite.

- **Anneau extérieur** : safe-ish, loot commun, peu de contamination.
- **Anneau médian** : loot intéressant, ennemis, contamination modérée.
- **Cœur (« la Chambre Pourpre »)** : meilleur loot, contamination galopante, point de non-retour si on s'attarde.

La sortie d'extraction est souvent **loin du cœur** → s'enfoncer profond = pari sur le temps de retour.

### 1.4 Exemples concrets de situations de jeu

**Situation A — « Le couloir qui s'écrit »**
Le joueur entre dans une galerie. Les murs sont vierges. À mesure qu'il avance, des lettres calligraphiques **sourdent du sol et grimpent les murs** (signal visuel = contamination locale qui monte). S'il s'attarde pour fouiller les coffres, le texte atteint le plafond et **déclenche** l'apparition d'un ennemi (un « Murmure », voir §3). Décision : fouiller vite et partir, ou tout prendre et combattre.

**Situation B — « Le choix du masque »**
Une salle contient un kit de réparation **et** un trésor de loot, mais une seule action possible avant qu'une horloge (l'Horloge d'Ébène, voir §5) ne sonne et ne ferme la salle. Réparer = survivre plus longtemps mais repartir les mains vides ; looter = richesse mais combinaison condamnée.

**Situation C — « L'extraction sous corruption »**
Contamination à 85 %. L'écran se couvre de typographie noire qui ronge les bords. Le joueur connaît le chemin de sortie mais sa vision se réduit. Course finale tendue : chaque seconde compte, le combat est suicidaire, seule la lecture du niveau sauve.

---

## 2. SYSTÈME DE CONTAMINATION

Le cœur identitaire du jeu. Doit être **une seule jauge lisible** mais aux conséquences multiples.

### 2.1 Modèle de progression (simple, mesurable)

La contamination est une jauge 0 → 100. Elle monte selon **trois sources additives** :

1. **Temps passif** : montée lente et constante dans une aile (la combinaison fuit toujours un peu).
2. **Exposition environnementale** : zones contaminées (brume rouge, salles infectées, anneaux profonds) = multiplicateur de montée.
3. **Dégâts à la combinaison** : chaque coup encaissé déchire la combinaison → la fuite passive accélère **durablement**.

> **Faisabilité :** une seule variable `contamination`, un `taux` recalculé chaque frame = `base + zone_mult + (1 - intégrité_combinaison)`. Trivial à implémenter, riche en émergence.

### 2.2 La double jauge : Contamination vs Intégrité de la combinaison

C'est la subtilité clé du concept original, qu'il faut préserver :

- **Intégrité de la combinaison** (100 → 0) : protège, mais se dégrade avec le temps et les coups.
- **Contamination du joueur** (0 → 100) : la conséquence ; monte d'autant plus vite que l'intégrité baisse.

**Twist du concept (très important, fidèle au brief) :** la combinaison **protège ET contamine**. Plus elle est usée, plus elle laisse passer la peste ; mais le port prolongé augmente *aussi* la contamination de base — le médecin de peste finit empoisonné par sa propre armure. Mécaniquement :

> Au-delà d'un seuil de temps, retirer/alléger la combinaison réduit la montée passive **mais** supprime la protection contre les attaques et zones. Choix tactique : blindé-mais-condamné vs exposé-mais-respirant.

### 2.3 Effets concrets en gameplay (par paliers)

Effets **graduels et lisibles**, jamais brutaux (pour rester équitable) :

| Seuil | Effet gameplay | Justification design |
|---|---|---|
| 25 % | Rechargement de l'arquebuse légèrement plus lent (mains qui tremblent) | Touche le système le plus tendu : le reload |
| 50 % | Réduction du champ de vision / portée de la lumière | Augmente l'incertitude spatiale |
| 75 % | Hallucinations : faux ennemis typographiques, faux loot | Crée le doute perceptif (signature Poe) |
| 90 % | Drain de vie lent ; chaque seconde coûte | Compte à rebours final |
| 100 % | « Mort Rouge » : game over de l'expédition | Conséquence claire et thématique |

**Principe :** les effets dégradent la **performance et la perception**, pas les contrôles (jamais d'inversion de touches frustrante). Le joueur reste compétent mais **diminué**.

### 2.4 Réduire la contamination (les soupapes)

Sans soupape, le système est punitif. Le joueur doit pouvoir **respirer** :

- **Kits de purge** (loot rare) : baisse directe de la jauge, animation rituelle (vulnérable pendant ~2 s).
- **Sanctuaires** : salles « propres » (vitraux intacts, encens) où la contamination **redescend lentement** si on s'arrête → mais on perd du temps/loot ailleurs.
- **Extraction** : remet la jauge à un niveau de base au hub.

### 2.5 Feedback visuel & sonore

La jauge ne doit **presque jamais** être lue comme un chiffre. Elle est *ressentie* par l'environnement et le son.

**Visuel (escalade) :**
- Bas : monde net, calligraphie discrète gravée dans les objets.
- Moyen : les lettres se **détachent** des surfaces, flottent, rampent vers le joueur.
- Haut : le texte **envahit** l'écran depuis les bords (vignette typographique noire), le HUD lui-même se met à « baver » des lettres.
- Critique : la vue iso se teinte de rouge, des mots-clés de Poe (« RED », « DEATH », « OUT ») apparaissent fugacement dans le décor.

**Sonore (escalade) :**
- Bas : ambiance feutrée, gouttes, respiration calme dans le masque.
- Moyen : la respiration s'accélère et se fait sifflante (filtre du masque qui s'encrasse) ; chuchotements illisibles.
- Haut : battement de cœur, voix qui **épellent des lettres** (la corruption « se lit » à l'oreille).
- Critique : silence soudain + un seul son grave de cloche (rappel de l'Horloge d'Ébène) → angoisse maximale.

> **Diégétisation :** la respiration dans le masque est le meilleur indicateur de contamination — toujours présente, jamais intrusive, instantanément lisible. C'est le « pouls » du jeu.

---

## 3. COMBAT

Le combat est **rare, dangereux, décisif**. Ce n'est pas un power fantasy ; c'est un dernier recours coûteux.

### 3.1 L'arquebuse à une main — design du feeling

Arme unique principale : poudre noire + mèche, **un coup, puis un long reload tactique**.

**Cycle de tir (rythme imposé) :**
1. **Visée** : tir précis, hitscan ou projectile lent et lourd (préférer projectile pour la lecture iso et l'esquive ennemie).
2. **Tir** : *énorme* feedback — recul, flash, nuage de fumée qui **masque temporairement la vue** (conséquence tactique : tirer aveugle pendant 1 s).
3. **Reload (le cœur du système)** : séquence en **3 temps** manuels, façon rituel —
   - verser la poudre,
   - tasser/bourrer,
   - rallumer la mèche.
4. **Mèche** : entre le déclenchement et le tir, court délai (la mèche brûle) → timing, anticipation.

**Reading & risk :** pendant le reload (long, ~2,5–4 s), le joueur est **vulnérable et immobile-ish**. D'où : on ne tire pas par réflexe, on tire quand **on a créé l'opportunité** (positionnement, coin, ennemi engagé).

**Option skill-based — le « Perfect Reload » :** un mini-timing (comme un *active reload* type Gears, mais habillé « rallumer la mèche au bon moment ») donne un rechargement plus rapide ou un tir surchargé. Récompense la maîtrise sans casser la lenteur.

**Impact de la contamination sur l'arme :** plus la jauge monte, plus la mèche est capricieuse (ratés, délai allongé) → le combat devient *littéralement* plus risqué quand on est corrompu. Cohérence parfaite avec le pilier de tension.

### 3.2 Économie du combat

- **Munitions rares** (poudre = loot). Chaque tir « coûte ». On compte ses balles.
- **Le corps-à-corps comme dernier recours** : une lame/canne courte pour finir un ennemi affaibli ou se dégager, mais risquée (proximité = contamination).
- **L'environnement comme arme** : pousser un ennemi dans une zone contaminée, faire tomber un lustre (l'Horloge, un brasier), déclencher des pièges → encourage à *ne pas* tirer.

### 3.3 Types d'ennemis (adaptés à un combat lent et tactique)

Chaque ennemi doit poser **un problème distinct** au reload long.

| Ennemi | Comportement | Rôle de design |
|---|---|---|
| **Les Conviés (foule)** | Aristocrates masqués, lents, en groupe | Pression de nombre ; punissent l'immobilité du reload → forcent le kiting et le placement |
| **Le Murmure** | Silhouette de texte, rapide, fragile | Ennemi « tueur de reload » : oblige à tirer au bon moment ou fuir |
| **Le Porteur** | Lourd, encaisse, émet une aura de contamination | Contrôle de zone ; tuer ≠ priorité, éviter son aura compte plus |
| **L'Horloger / le Sonneur** | Mini-boss qui accélère la contamination ambiante | Crée des « phases » d'urgence ; objectif optionnel à fort risque/récompense |
| **La Mort Rouge (présence)** | N'est pas tuable ; traque si on dépasse un seuil de contamination/temps | Le « Mr. X » du jeu : incarnation du compte à rebours, force l'extraction |

> **La Mort Rouge** comme **chasseur invincible déclenché par la contamination** est l'idée de combat la plus forte : elle fusionne le système de jauge et la menace physique. On ne la combat pas, on la **fuit** — fidèle à Poe (nul n'échappe à la Mort Rouge).

### 3.4 Règles d'équité

- Telegraphing clair de toute attaque (la lenteur du jeu l'exige).
- Jamais de mort instantanée hors contamination 100 %.
- Le joueur peut **toujours** choisir la fuite : aucun combat n'est strictement obligatoire (sauf scripts de boss optionnels).

---

## 4. DIRECTION ARTISTIQUE

L'identité visuelle = **monde isométrique crédible + calligraphie comme matière vivante**. Le risque n°1 est le **chaos illisible**. La DA se définit donc autant par ses **règles de retenue** que par ses effets.

### 4.1 Le concept fondateur : « Le monde s'écrit / se corrompt en temps réel »

La typographie n'est **pas un filtre par-dessus** le jeu : c'est **la substance de la peste**. Règle narrative interne :

> *La Mort Rouge n'est pas un virus, c'est un texte. Elle contamine en s'écrivant sur le monde et sur les corps.*

Cela justifie diégétiquement chaque effet typographique → cohérence totale.

### 4.2 Règles visuelles pour éviter le chaos (le plus important)

**Règle 1 — Hiérarchie en 3 couches, jamais mélangées :**
1. **Couche MONDE** (lisible, prioritaire) : géométrie iso, sols, murs, personnages. Toujours nette. La calligraphie n'y est que **gravée/intégrée** (basse intensité).
2. **Couche CONTAMINATION** (calligraphie active) : c'est *elle seule* qui bouge, rampe, flotte. Tout texte mobile = danger. **Le mouvement typographique est réservé à la menace.**
3. **Couche INTERFACE** (feedback joueur) : tirs, impacts, HUD. Calligraphie « propre », contrôlée, dans la couleur du joueur.

**Règle 2 — Le mouvement = information.** Si une lettre bouge, elle **signifie** quelque chose (contamination, ennemi, dégât). Jamais de typographie animée purement décorative. Le joueur apprend à « lire » le danger.

**Règle 3 — Lisibilité gameplay > beauté.** Les zones de jeu critiques (chemins, ennemis, loot) restent **dégagées**. La calligraphie envahit les **surfaces** (murs, plafonds, fonds), pas les **volumes jouables** tant que la contamination est basse. Elle n'empiète sur la zone jouable **qu'à dessein**, comme pénalité de haute contamination.

**Règle 4 — Palette restreinte et symbolique :**
- **Noir** (encre) = corruption, texte de la peste.
- **Rouge pourpre** = la Mort Rouge, le danger ultime, le sang.
- **Or fané / ivoire** = l'aristocratie, le luxe malade, les zones sûres.
- **Blanc froid** = le joueur, sa lumière, ses tirs (pureté assiégée).
> 4 couleurs. Toute la dramaturgie tient dans le **ratio noir/rouge vs or/blanc** à l'écran : plus c'est envahi de noir et rouge, plus le danger est grand. La DA *est* le HUD.

**Règle 5 — Le calme rend le chaos lisible.** Les espaces sûrs sont **typographiquement silencieux** (texte gravé, immobile). Le contraste fait que l'invasion typographique frappe d'autant plus fort.

### 4.3 Intégration concrète de la calligraphie

- **Tirs** : la balle laisse une **traînée d'une seule lettre/mot** stylisé (ex. trait qui « écrit » sa trajectoire), nette et blanche → lisible, pas brouillon.
- **Impacts** : à l'impact, la trace se **fragmente en éclats typographiques** qui retombent et s'effacent vite (≤ 0,5 s) → satisfaction sans pollution.
- **Contamination de surface** : sur les murs, du texte noir **croît comme du lierre** (croissance procédurale lente). Densité = niveau de contamination locale.
- **Ennemis-texte** (Murmures) : faits *de* calligraphie en mouvement → cohérence parfaite menace/forme.
- **Environnement** : inscriptions latines/françaises fanées sur le marbre (vers de Poe, épitaphes), **immobiles** = patrimoine du lieu, pas une menace. Distinction nette d'avec le texte vivant.

### 4.4 Exemples de scènes fortes

**Scène 1 — « L'Horloge d'Ébène » (set-piece signature).**
Une salle de bal en ruine. Au centre, l'horloge géante de Poe. À chaque heure, elle **sonne** : le son fige les Conviés une seconde, et un **raz-de-marée de calligraphie noire** balaie la pièce depuis l'horloge (montée brutale de contamination). Le joueur doit traverser entre deux sonneries. Iconique, mécanique, fidèle à la nouvelle.

**Scène 2 — « Les Sept Salles ».**
Hommage direct : sept salles colorées (bleu, pourpre, vert, orange, blanc, violet, **noire à vitraux rouges**). Chaque salle a une couleur dominante qui **teinte sa calligraphie** et module une mécanique (la salle noire = contamination max, meilleur loot, repaire potentiel de la Mort Rouge). Progression spatiale = montée dramatique intégrée au level design.

**Scène 3 — « Le Démasquage ».**
Quand le joueur retire sa combinaison (choix §2.2), la caméra se rapproche un instant : on voit le visage exposé, et l'air ambiant se met à **écrire sur sa peau**. Moment de vulnérabilité intime, fort visuellement et thématiquement.

**Scène 4 — « L'extraction terminale ».**
Décrite en §1.4-C : l'écran se referme en typographie noire, ne laissant qu'un tunnel de vision blanc vers la sortie. Le monde *finit littéralement de s'écrire* derrière le joueur.

---

## 5. IDÉES FORTES & DIFFÉRENCIATION

### 5.1 L'argument unique (USP)

> **« Un jeu où la peste est un texte, et où survivre c'est refuser de se laisser écrire. »**

Aucun shooter d'exploration ne fait de la **typographie la mécanique ET l'esthétique ET la narration** en même temps. C'est le triple-verrou qui rend Red Death inimitable : on ne peut pas copier le look sans copier le système.

### 5.2 Mécaniques signatures (différenciantes)

1. **La combinaison qui protège-et-condamne** (§2.2)
   Inversion du tropisme « armure = bien ». Ici, plus tu te protèges, plus tu te tues. Dilemme permanent, propre au thème du médecin de peste.

2. **La Mort Rouge comme compte à rebours incarné** (§3.3)
   Le chasseur invincible n'est pas un timer abstrait : c'est une présence qui *est* ta contamination. Fusion mécanique/fiction.

3. **Le texte comme danger lisible** (§4.2)
   Apprendre à « lire » la pièce — littéralement. Le langage visuel devient une compétence de survie. Skill ceiling unique.

4. **L'Horloge d'Ébène comme métronome de tension** (§4.4)
   Découpe chaque aile en mesures dramatiques. Rythme imposé, fidèle à Poe, mémorable.

5. **Le démasquage volontaire** (§2.2 / §4.4-Scène 3)
   Choix risqué et intime : sacrifier sa protection pour respirer. Peu de jeux laissent retirer son armure comme stratégie.

### 5.3 Idées d'expansion (réserve, post-vertical-slice)

- **Run-based / roguelite léger** : les ailes se recomposent, méta-progression sur le hub (réparations permanentes, nouvelles recettes de purge). Allonge la durée de vie, colle à la boucle d'expédition.
- **Le « Livre » de la Mort Rouge** : un codex qui se remplit du texte que le joueur survit — la mémoire des runs s'écrit. Méta-narration cohérente.
- **Mode « Lecture » accessibilité** : pour les sensibles à la lisibilité, réglages de densité/contraste typographique. À prévoir tôt (la DA repose sur du texte → enjeu d'accessibilité réel).

### 5.4 Garde-fous de production (faisabilité)

- **Vertical slice recommandé** : 1 aile (les Sept Salles condensées), 3 types d'ennemis (Conviés, Murmure, Porteur), l'arquebuse + 1 soupape (kit de purge), l'Horloge d'Ébène, et la Mort Rouge déclenchée. Suffisant pour prouver les 3 piliers.
- **Le système typographique est le risque technique n°1** : prototyper tôt la croissance procédurale de texte + la lisibilité en mouvement. Si trop coûteux, fallback : textures de calligraphie animées par shaders (moins émergent, mais fiable).
- **Une seule jauge, des effets multiples** : tenir la promesse « simple mais expressif ». Ne pas multiplier les barres.

---

## ANNEXE — Carte des cohérences (gameplay ⇄ esthétique)

| Pilier | Système (gameplay) | Traduction esthétique | Fidélité Poe |
|---|---|---|---|
| Tension temporelle | Jauge de contamination | Texte qui envahit l'écran | « Le Temps fuit » / Horloge d'Ébène |
| Risque du combat | Reload long de l'arquebuse | Fumée qui masque, traînée de lettres | Danger feutré, aristocratique |
| Survie / loot | Anneaux de profondeur | Ratio noir-rouge / or-blanc | Les Sept Salles |
| Vulnérabilité | Combinaison qui se dégrade | Calligraphie qui s'écrit sur la peau | Le médecin de peste, le masque |
| Mortalité inéluctable | La Mort Rouge (chasseur) | Présence rouge pourpre | « Et la Mort Rouge régna sans partage » |

---

*Tout dans ce document tient à une seule idée : le joueur lutte contre le temps qui s'écrit. Le gameplay le mesure, l'arme le ralentit, la DA le montre, et la Mort Rouge le clôt.*
