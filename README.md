# Runes & Remparts

Prototype jouable d’un jeu d’action roguelite heroic fantasy pour **PC (clavier et souris)**, dans l’esprit du mode Swarm de League of Legends.
Ce dépôt sert de terrain d’essai pour trouver le fun avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.9 : la Horde retournée)

**USP : tu pars seul, et tu retournes la horde.** Les ennemis vaincus rejoignent ton armée ; tu la mènes contre la marée ennemie.
C’est la première des trois couches du concept complet : **Runes** (sorts forgés, à venir), **Horde** (l’armée, pendant la mission), **Remparts** (citadelle ambulante, à l’échelle de la campagne, à venir).

- **Contrôles** : ZQSD / WASD / flèches pour bouger, **souris pour viser**. L’attaque du champion tire en continu vers le curseur (C bascule en visée automatique).
- **Sorts** : **clic droit** (ou E) et **Espace**, chacun avec sa recharge. **Ultime** : **R**, rechargé par les kills.
- **Ton armée** : chaque faction recrute à sa manière. Les **orcs** soumettent un quart des ennemis achevés ; les **nains** forgent un **golem runique** tous les 9 kills ; les **elfes** envoûtent des **esprits** rapides mais fragiles. L’armée suit le héros et attaque tout ce qui approche. **Clic gauche** (ou F) : assaut sur le point visé. **Maj** : ralliement (soin, résistance). Cartes d’armée : effectif, ferveur, bannière, vétérans, tambours.
- **Trois champions** :

| Champion | Attaque (visée) | Clic droit | Espace | Ultime |
|---|---|---|---|---|
| **Grukk** (orc, mêlée) | Lancer de haches | **Charge** : fonce, renverse tout, retombe en onde de choc (un kill rembourse 60 % de la recharge) | **Tourbillon** : avance en aspirant la horde, finit en éruption | WAAAGH ! |
| **Durgan** (nain, contrôle) | Marteau qui revient | **Tourelle runique** lancée en cloche : impact étourdissant, tir rapide, explosion finale | **Séisme** : une faille de pics de roche court vers le curseur et explose | Barrage runique au curseur |
| **Lyriel** (elfe, distance) | Arc perçant | **Roulade** d’esquive : les 2 flèches suivantes sont chargées (énormes, perforantes) | **Volée** au curseur : les ennemis touchés sont marqués | Nuit des étoiles |

- **Synergies** : un ennemi étourdi subit +30 % de dégâts, un ennemi marqué +25 %. Enchaîner ses sorts paie.
- **Build en partie** : chaque niveau propose 3 cartes : armes automatiques, passifs, et **talents** qui transforment les sorts (par exemple, une Charge qui laisse une traînée de braises, des Tourelles jumelles, une Volée de givre). Les évolutions d’armes restent : arme au niveau 5 + passif indiqué + 1 cristal.
- **Missions** : chaque carte enchaîne 5 objectifs, puis un boss final. Les flèches dorées guident vers l’objectif.
  - **Libérer les prisonniers** : brise la cage gardée, 8 miliciens rejoignent ton armée.
  - **Prendre un fort** : abats le capitaine, toute sa garnison passe dans ton camp.
  - **Détruire les nids** qui crachent la horde.
  - **Tenir la rune** : rester dans le cercle pour la charger, pendant que la horde afflue.
  - **Traquer le porteur** de runes qui s’enfuit.
  - **Escorter la caravane**, qui n’avance que si le champion reste près d’elle. Si elle tombe, la mission est perdue.
  - Un **boss intermédiaire** arrive au milieu de la mission : vaincu, il **devient ton général**.
  - Les boss frappent aussi ton armée (charge, onde de choc).
- **Deux missions** : *Les Marches cendrées* (boss : Chef de guerre cendré) et *Le Col du Néant* (boss : Seigneur du Néant), en trois difficultés : Normal, Héroïque, Légendaire.
- **Le camp, entre les missions** : chaque mission rapporte des **runes**, même en cas de défaite. On les dépense en améliorations permanentes (PV, dégâts, vitesse, recharge des sorts, XP, aimant, or de départ). Des **défis** débloquent des armes, une mission, un passif et les difficultés supérieures.
- La progression est sauvegardée dans le navigateur.
- **Rendu** : sol peint par morceaux (sentiers, fleurs, fissures du Néant), forêts, ruines et braseros, cristaux luminescents, éclairage dynamique (pénombre, lumière des sorts, projectiles et explosions), halos, fumée, brume, corps qui tombent, images rémanentes.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Débit et PV des ennemis, marées, XP, élites, encerclements, rythme des objectifs, PV des boss, runes gagnées |
| `HEROES`, `FACTIONS`, `ULTS` | Champions, arme signature, sorts, ultimes |
| `SPELLS` | Les 6 sorts : recharge, dégâts, talents |
| `MAPS`, `DIFFS`, `OBJ` | Missions (objectifs, boss), difficultés |
| `CAMP`, `CHALLENGES` | Améliorations permanentes et défis de déblocage |
| `WEAPONS`, `PASSIVES`, `ENEMIES` | Armes, passifs, bestiaire |

Le menu pause contient des **outils de test** (+1 niveau, +1 minute, or, cristal, sorts prêts, objectif suivant, invincibilité), et la console expose `window.RR` pour simuler des missions.

## Historique

- v0.1 à v0.2 : tower defense sur chemins, puis héros, sorts et pixel art.
- v0.3 : citadelle assiégée à 360°.
- v0.4 : pivot vers un survivor, après des playtests où l’on « cliquait sans réfléchir ».
- v0.5 à v0.6 : récolte, butin et remparts, en portrait mobile. Pas concluant : « un survivor comme les autres ».
- v0.7 : virage PC à la Swarm : visée à la souris, sorts actifs et talents, missions à objectifs, camp de progression.
- v0.8 : grosse passe graphique (éclairage dynamique, décors, effets) et sorts plus amusants (charges, onde de choc, faille, flèches chargées, marques et synergies).
- v0.9 : USP « la Horde retournée » : armée convertie par faction, ordres d’assaut et de ralliement, prisonniers, prise de fort, boss vaincu devenu général.
