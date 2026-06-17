# RED DEATH — Document de Direction Créative

> Shooter d'exploration isométrique — survie, tension, loot
> Univers inspiré de *Le Masque de la Mort Rouge* d'Edgar Allan Poe

**Rôle du document :** transformer le concept en systèmes cohérents, lisibles et réalisables. Chaque proposition vise un équilibre entre **identité forte** (Poe + calligraphie vivante) et **faisabilité de production** (systèmes simples, expressifs, mesurables).

**Phrase-pilier (north star) :**
> *Plus tu restes, plus le monde t'écrit dedans.*

Le temps est la ressource centrale. Tout le design tourne autour d'une seule tension : **explorer vite mais incomplet, ou rester et se corrompre.**

**Univers & cadre.** Un voyageur arrive dans un **village de Toscane** dévasté par la peste, et doit atteindre puis **gravir le château du Prince Prospero**. Chaque étage du château se termine par une **chambre de couleur** (les sept salles de la nouvelle de Poe) qui, une fois sa **Mort de couleur** vaincue, ouvre l'escalier vers l'étage suivant — jusqu'à la chambre noire aux vitraux écarlates et la **Mort Rouge**. La structure complète est en §1.0 et §1.5.

---

## 1. GAMEPLAY

### 1.0 Structure générale : l'Ascension du château

Le jeu suit un **fil narratif et spatial unique** : un voyageur arrive dans un **village de Toscane** ravagé par la peste, et doit atteindre puis **gravir le château du Prince Prospero**, étage par étage.

```
VILLAGE DE TOSCANE (prologue / hub initial)
   └─ Peste, ruines, premiers indices, équipement de départ
      ↓
PORTES DU CHÂTEAU DE PROSPERO
      ↓
ÉTAGE 1 → ... → ÉTAGE 7  (ascension verticale)
   Chaque étage = un dédale à explorer (loot, contamination, ennemis)
   qui se termine par UNE CHAMBRE DE COULEUR.
      ↓
   CHAMBRE DE COULEUR (au bout de l'étage)
      └─ Mécanique de jeu UNIQUE propre à la couleur
      └─ BOSS : la MORT de cette couleur
      └─ Vaincre la Mort = l'escalier vers l'étage suivant s'ouvre
      ↓
SOMMET : la CHAMBRE NOIRE aux vitraux écarlates
   └─ Affrontement final avec la MORT ROUGE
```

**Les sept chambres reprennent les sept salles de la nouvelle de Poe** (bleu, pourpre, vert, orange, blanc, violet, noir), d'est en ouest chez Poe, ici de bas en haut. Voir la **section 1.5** pour le détail de chaque chambre.

**Principe d'or :** la progression ne se gagne pas par le combat de masse, elle se gagne par la **gestion du risque temporel** dans chaque étage, puis par la **maîtrise de la mécanique unique** de la chambre. Le joueur n'est jamais « bloqué par un mur d'ennemis » ; il est pressé par sa propre jauge, puis testé par un duel thématique.

### 1.1 Boucle minute par minute (micro) — l'expérience de tension

Objectif : que le joueur ressente une **pression croissante et lisible** pendant l'exploration d'un étage (~8–12 min) avant d'atteindre sa chambre de couleur.

| Temps | État de la combinaison | Ressenti visé | Décision typique du joueur |
|---|---|---|---|
| 0–2 min | Intacte, contamination basse | Confiance, exploration libre | « J'ouvre tout, je fouille » |
| 2–5 min | Premières dégradations | Vigilance | « Je priorise les bonnes salles » |
| 5–8 min | Combinaison usée, contamination ½ | Stress | « Je cherche une sortie ou une réparation » |
| 8–10 min | Visières fissurées, contamination haute | Urgence | « Je sacrifie du loot pour survivre » |
| 10+ min | Seuil critique | Panique contrôlée | « Je cours vers l'extraction » |

**Règle de design :** la tension doit être **auto-infligée**. Le joueur décide de rester pour le loot ; le jeu ne fait que rendre visible le coût. C'est le moteur émotionnel du jeu.

### 1.2 Le « risk/reward » spatial : la Profondeur de l'étage

Chaque étage est conçu en **anneaux de profondeur** autour du chemin direct vers la chambre de couleur : plus on s'écarte du chemin et on fouille, plus le loot est riche **et** plus la contamination ambiante monte vite.

- **Chemin direct** : sûr-ish, loot commun, mène droit à la chambre.
- **Salles annexes** : loot intéressant, ennemis, contamination modérée.
- **Recoins scellés** : meilleur loot (ressources de réparation/purge), souvent gardés ou contaminés ; détour à haut risque temporel.

> Important : la chambre de couleur et son boss exigent d'arriver **en état de combattre**. Trop fouiller = arriver au duel déjà corrompu, combinaison usée. Le dilemme « explorer ou se préserver » se rejoue donc à chaque étage, avec le boss comme échéance.

### 1.3 Le tempo d'un étage : exploration → seuil → duel

Chaque étage suit un arc en trois temps, ce qui donne au jeu un **rythme de respiration régulier** sur les 7 étages :

1. **Exploration** (gestion du risque temporel, loot, ennemis mineurs).
2. **Le Seuil** : la grande porte de la chambre de couleur. Dernier point pour faire ses choix (réparer ? purger ? entrer maintenant ?). Franchir = on s'engage, retour fermé.
3. **Le Duel** : la chambre, sa mécanique unique, la Mort de couleur. Victoire = l'escalier s'ouvre, court répit, montée à l'étage suivant.

### 1.4 Exemples concrets de situations de jeu

**Situation A — « Le couloir qui s'écrit »**
Le joueur entre dans une galerie. Les murs sont vierges. À mesure qu'il avance, des lettres calligraphiques **sourdent du sol et grimpent les murs** (signal visuel = contamination locale qui monte). S'il s'attarde pour fouiller les coffres, le texte atteint le plafond et **déclenche** l'apparition d'un ennemi (un « Murmure », voir §3). Décision : fouiller vite et partir, ou tout prendre et combattre.

**Situation B — « Le choix du masque »**
Une salle contient un kit de réparation **et** un trésor de loot, mais une seule action possible avant qu'une horloge (l'Horloge d'Ébène, voir §5) ne sonne et ne ferme la salle. Réparer = survivre plus longtemps mais repartir les mains vides ; looter = richesse mais combinaison condamnée.

**Situation C — « L'extraction sous corruption »**
Contamination à 85 %. L'écran se couvre de typographie noire qui ronge les bords. Le joueur connaît le chemin de sortie mais sa vision se réduit. Course finale tendue : chaque seconde compte, le combat est suicidaire, seule la lecture du niveau sauve.

### 1.5 LES SEPT CHAMBRES — étages, mécaniques uniques & Morts de couleur

Le cœur structurel du jeu. Chaque étage culmine dans une chambre dont la **couleur** dicte à la fois l'ambiance, une **mécanique de gameplay unique** (un « verbe » différent par étage, pour que le jeu ne se répète jamais) et une **Mort de couleur** comme boss. Vaincre la Mort ouvre l'escalier suivant.

> **Règle de cohérence :** la mécanique unique de la chambre **prépare** le combat contre sa Mort. On apprend la règle de la salle en la traversant, puis la Mort l'exploite contre nous. Tutoriel implicite intégré au level design.

| # | Chambre | Atmosphère (Poe) | Mécanique de jeu unique | La Mort de couleur (boss) |
|---|---|---|---|---|
| 1 | **Bleue** (l'Aube / les eaux) | Aube froide, vitraux bleus, eaux dormantes à l'orient | **La lumière & la montée des eaux** : pénombre, on explore à la lanterne ; l'eau monte et restreint l'espace jouable au fil du temps | **La Mort Bleue** : noyée, lente, éteint les lumières et inonde l'arène — il faut la garder éclairée et combattre sur les hauteurs |
| 2 | **Pourpre** (la cour / le sang) | Salle de bal des Conviés, luxe sanglant | **La foule & le masque** : se fondre parmi les invités masqués pour ne pas être repéré ; rompre le bal déclenche la nuée | **La Mort Pourpre** : saigne le décor, commande la foule des Conviés — la séparer de ses sujets, frapper dans les fenêtres d'isolement |
| 3 | **Verte** (la serre pourrie) | Végétation morte, spores, contamination galopante | **L'envahissement** : le texte-lierre pousse vite et ferme les chemins ; zones de spores à éviter, course contre la corruption | **La Mort Verte** : empoisonneuse, fait croître le décor pour vous enfermer — détruire les foyers de croissance avant qu'ils ne saturent l'arène |
| 4 | **Orange** (les feux / la forge) | Braseros, fonte, lumière incandescente | **Le feu** : on peut enflammer (la mèche de l'arquebuse prend tout son sens), mais le feu se propage et **accélère la contamination** ; manier l'incendie sans s'y prendre | **La Mort Orange** : incandescente, sème des brasiers et des traînées — la noyer/l'éteindre, exploiter les zones déjà brûlées comme refuge |
| 5 | **Blanche** (l'ossuaire / le silence) | Os, marbre, lumière aveuglante, silence | **La privation sensorielle** : aveuglement blanc, on s'oriente au **son** (pas, respiration, calligraphie qui chuchote) | **La Mort Blanche** : silencieuse, invisible quand on la fixe, frappe dans l'angle mort — la « lire » à l'oreille et au texte qu'elle laisse |
| 6 | **Violette** (le délire) | Couleur de la folie, perceptions trompées | **L'hallucination** : faux ennemis, faux loot, faux murs (reprise de l'effet de contamination haute) ; douter de tout ce qu'on voit | **La Mort Violette** : illusionniste, se démultiplie en leurres — distinguer la vraie au comportement, pas à l'apparence |
| 7 | **Noire** aux vitraux écarlates (la fin) | La chambre que nul n'osait habiter, l'Horloge d'Ébène | **La synthèse** : toutes les mécaniques combinées, aucune soupape, l'Horloge scande des phases ; rien n'est sûr | **LA MORT ROUGE** : boss final, **non « tuable » au sens classique** — il faut survivre/désamorcer ses phases au lieu de la vaincre de front (voir §3.3 et §5) |

**Notes de design :**
- **Sept couleurs, sept verbes** : lumière, foule/discrétion, envahissement, feu, son, illusion, synthèse. Aucun étage ne se joue comme un autre → variété garantie sans multiplier les systèmes (chaque verbe réutilise des briques existantes : contamination, lanterne, mèche, audio).
- **Courbe de difficulté = l'ordre des couleurs de Poe.** Le bleu (est, l'aube) introduit ; le noir (ouest, le couchant/la mort) conclut. La progression spatiale *est* la courbe dramatique.
- **Le village de Toscane** sert de prologue jouable (apprentissage des bases : déplacement, lanterne, arquebuse, première montée de contamination) avant la première chambre — pas un simple menu.
- **Production :** un boss par étage est ambitieux. Pour un vertical slice, prototyper **2 chambres contrastées** (ex. Bleue = lumière/eau, et Verte = envahissement/contamination) + la Mort Rouge, afin de prouver la formule « mécanique unique + Mort de couleur ».

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
- **Sanctuaires** : salles « propres » (vitraux intacts, encens) au sein d'un étage où la contamination **redescend lentement** si on s'arrête → mais on perd du temps/loot ailleurs.
- **Le palier de l'escalier** : après avoir vaincu une Mort de couleur, le sas vers l'étage suivant est un bref répit où la jauge **redescend à un niveau de base**. C'est la récompense de progression et le rythme de respiration entre deux étages.

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

**Ennemis communs (peuplent les étages) :**

| Ennemi | Comportement | Rôle de design |
|---|---|---|
| **Les Conviés (foule)** | Aristocrates masqués, lents, en groupe | Pression de nombre ; punissent l'immobilité du reload → forcent le kiting et le placement |
| **Le Murmure** | Silhouette de texte, rapide, fragile | Ennemi « tueur de reload » : oblige à tirer au bon moment ou fuir |
| **Le Porteur** | Lourd, encaisse, émet une aura de contamination | Contrôle de zone ; tuer ≠ priorité, éviter son aura compte plus |
| **L'Horloger / le Sonneur** | Mini-boss qui accélère la contamination ambiante | Crée des « phases » d'urgence ; objectif optionnel à fort risque/récompense |

**Les boss : les Morts de couleur (une par chambre).**
Chaque étage culmine sur une Mort de couleur dont le combat **exploite la mécanique unique de sa chambre** (détail complet en §1.5). Principe partagé : ce ne sont pas des sacs à PV, mais des **énigmes de combat** où il faut retourner la règle de la salle contre la Mort (éteindre/éclairer, isoler de la foule, contenir l'envahissement, maîtriser le feu, écouter dans le noir, démasquer l'illusion).

| Boss d'étage | Chambre | Clé du combat |
|---|---|---|
| **La Mort Bleue** | Bleue | Garder l'arène éclairée, combattre sur les hauteurs hors de l'eau |
| **La Mort Pourpre** | Pourpre | La séparer de la foule des Conviés, frapper dans les fenêtres d'isolement |
| **La Mort Verte** | Verte | Détruire les foyers de croissance avant saturation de l'arène |
| **La Mort Orange** | Orange | L'éteindre/la noyer, utiliser les zones déjà brûlées comme refuge |
| **La Mort Blanche** | Blanche | La localiser au son, frapper dans l'angle mort |
| **La Mort Violette** | Violette | Identifier la vraie au comportement, ignorer les leurres |

**Le boss final : LA MORT ROUGE** (chambre noire, §1.5).
On ne la « tue » pas au sens classique — fidèle à Poe, *nul n'échappe à la Mort Rouge*. Le combat consiste à **survivre et désamorcer ses phases**, scandées par l'Horloge d'Ébène, en mobilisant tout ce que les six chambres ont enseigné. Sa présence peut aussi se manifester en amont comme **héraut/pression** (apparitions fugaces dans les étages quand la contamination est haute), pour installer la menace avant le duel final.

> **La Mort Rouge** fusionne le système de jauge et la menace physique : elle *est* la contamination incarnée. C'est l'idée de boss la plus forte du jeu, et l'aboutissement logique de l'ascension.

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

**Scène 2 — « Les Sept Chambres » (la colonne vertébrale du jeu, détaillée en §1.5).**
Les sept salles colorées de Poe (bleu, pourpre, vert, orange, blanc, violet, **noire à vitraux rouges**) sont les sept étages du château. Chaque chambre **teinte sa calligraphie** de sa couleur, porte une mécanique de jeu unique et abrite sa Mort de couleur en boss. La progression spatiale (de la chambre bleue de l'aube à la chambre noire de la fin) *est* la montée dramatique : level design et dramaturgie ne font qu'un.

**Scène 3 — « Le Démasquage ».**
Quand le joueur retire sa combinaison (choix §2.2), la caméra se rapproche un instant : on voit le visage exposé, et l'air ambiant se met à **écrire sur sa peau**. Moment de vulnérabilité intime, fort visuellement et thématiquement.

**Scène 4 — « L'ouverture de l'escalier ».**
À la mort d'une Mort de couleur, le silence retombe ; la calligraphie de la chambre se **fige puis se rétracte**, révélant l'escalier vers l'étage suivant qui s'illumine. Moment de catharsis et de répit, contraste fort avec la tension du duel — la récompense émotionnelle de l'ascension.

---

## 5. IDÉES FORTES & DIFFÉRENCIATION

### 5.1 L'argument unique (USP)

> **« Un jeu où la peste est un texte, et où survivre c'est refuser de se laisser écrire. »**

Aucun shooter d'exploration ne fait de la **typographie la mécanique ET l'esthétique ET la narration** en même temps. C'est le triple-verrou qui rend Red Death inimitable : on ne peut pas copier le look sans copier le système.

### 5.2 Mécaniques signatures (différenciantes)

1. **La combinaison qui protège-et-condamne** (§2.2)
   Inversion du tropisme « armure = bien ». Ici, plus tu te protèges, plus tu te tues. Dilemme permanent, propre au thème du médecin de peste.

2. **Les sept chambres, sept verbes, sept Morts de couleur** (§1.5)
   Une ascension où chaque étage se joue différemment et culmine sur un duel thématique fidèle à Poe. Variété intégrée au level design, sans surcharge de systèmes.

3. **La Mort Rouge comme aboutissement incarné** (§3.3)
   Boss final qu'on ne tue pas mais qu'on survit ; en amont, présence/héraut qui *est* ta contamination. Fusion mécanique/fiction.

4. **Le texte comme danger lisible** (§4.2)
   Apprendre à « lire » la pièce — littéralement. Le langage visuel devient une compétence de survie. Skill ceiling unique.

5. **L'Horloge d'Ébène comme métronome de tension** (§4.4)
   Scande l'étage final en mesures dramatiques. Rythme imposé, fidèle à Poe, mémorable.

6. **Le démasquage volontaire** (§2.2 / §4.4-Scène 3)
   Choix risqué et intime : sacrifier sa protection pour respirer. Peu de jeux laissent retirer son armure comme stratégie.

### 5.3 Idées d'expansion (réserve, post-vertical-slice)

- **New Game + / Mode Cauchemar** : réascension du château avec chambres recombinées, Morts plus agressives, contamination plus rapide. Préserve la structure narrative tout en offrant de la rejouabilité (plutôt qu'un roguelite qui casserait le fil Toscane → sommet).
- **Le « Livre » de la Mort Rouge** : un codex qui se remplit du texte que le joueur survit, chambre après chambre — la mémoire de l'ascension s'écrit. Méta-narration cohérente.
- **Mode « Lecture » accessibilité** : pour les sensibles à la lisibilité, réglages de densité/contraste typographique. À prévoir tôt (la DA repose sur du texte → enjeu d'accessibilité réel).

### 5.4 Garde-fous de production (faisabilité)

- **Vertical slice recommandé** : le prologue de Toscane + 2 chambres contrastées (ex. Bleue = lumière/eau et Verte = envahissement) avec leurs deux Morts de couleur, 3 types d'ennemis communs (Conviés, Murmure, Porteur), l'arquebuse + 1 soupape (kit de purge). Suffisant pour prouver la formule « exploration tendue → mécanique unique → Mort de couleur » et les 3 piliers.
- **Le système typographique est le risque technique n°1** : prototyper tôt la croissance procédurale de texte + la lisibilité en mouvement. Si trop coûteux, fallback : textures de calligraphie animées par shaders (moins émergent, mais fiable).
- **Une seule jauge, des effets multiples** : tenir la promesse « simple mais expressif ». Ne pas multiplier les barres.

---

## ANNEXE — Carte des cohérences (gameplay ⇄ esthétique)

| Pilier | Système (gameplay) | Traduction esthétique | Fidélité Poe |
|---|---|---|---|
| Tension temporelle | Jauge de contamination | Texte qui envahit l'écran | « Le Temps fuit » / Horloge d'Ébène |
| Risque du combat | Reload long de l'arquebuse | Fumée qui masque, traînée de lettres | Danger feutré, aristocratique |
| Progression / variété | Ascension des 7 chambres (1 mécanique + 1 boss par couleur) | Calligraphie teintée de la couleur de l'étage | Les sept salles du château de Prospero |
| Survie / loot | Anneaux de profondeur dans chaque étage | Ratio noir-rouge / or-blanc | Le luxe malade, les Conviés |
| Vulnérabilité | Combinaison qui se dégrade | Calligraphie qui s'écrit sur la peau | Le médecin de peste, le masque |
| Mortalité inéluctable | La Mort Rouge (boss final non tuable) | Présence rouge pourpre, vitraux écarlates | « Et la Mort Rouge régna sans partage » |

---

*Tout dans ce document tient à une seule idée : le joueur lutte contre le temps qui s'écrit. Le gameplay le mesure, l'arme le ralentit, la DA le montre, l'ascension des sept chambres le met en scène, et la Mort Rouge le clôt — au sommet du château de Prospero, là où nul n'échappe à la Mort Rouge.*
