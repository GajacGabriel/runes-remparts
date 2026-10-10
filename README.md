# Runes & Remparts

Prototype jouable d’un jeu d’action roguelite heroic fantasy pour **PC (clavier et souris)**, dans l’esprit du mode Swarm de League of Legends.
Ce dépôt sert de terrain d’essai pour trouver le fun avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.10 : un champion, une mécanique)

**Fini les armes génériques.** Chaque champion a une mécanique signature unique, et toutes ses cartes de niveau la font évoluer.
Lyriel est le premier champion jouable ; Grukk (la Hache liée) et Durgan (la Forge vivante) suivront.

### Lyriel, Tisseuse d’étoiles
- **Clic gauche** : ses flèches lunaires partent en continu vers le curseur (C : visée automatique). ZQSD / WASD / flèches pour bouger.
- **Étoile filante** (**clic droit** ou E, 3 charges) : une comète plante une étoile au point visé.
- **Constellation** : dès 3 étoiles, elles se relient. Les **fils d’argent** brûlent ce qui les traverse, une **pluie d’astres** frappe l’intérieur.
- **Prisme** : une flèche qui traverse une étoile se divise en 3. On vise à travers ses propres étoiles.
- **Pas lunaire** (**Espace**) : dash invulnérable. **Traverser sa constellation la fait exploser en supernova** (le dash est rendu).
- **Voûte céleste** (**R**) : trois étoiles autour d’elle et, pendant 7 s, jusqu’à 6 étoiles toutes reliées.
- **Arbre de talents** (les seules cartes de niveau, plus quelques bénédictions mineures) : trois branches, **Astronome** (constellations), **Archère** (flèches), **Danseuse** (mobilité, supernova). 5 cartes dans une branche débloquent sa **légendaire** : *Zodiaque* (supernova automatique), *Pluie d’argent* (les flèches se dédoublent sur les fils), *Étoile du berger* (chaque supernova recharge tout et soigne).

### La Nuit des étoiles filantes
Une mission rythmée par des **événements**, puis un **boss** dans son arène :
- **Chute d’étoiles** : des étoiles tombent du ciel ; leurs éclats rechargent l’Étoile filante.
- **Lune de sang** : la horde enrage (plus rapide, plus nombreuse), chaque kill vaut double XP.
- **Hérauts du Dévoreur** : trois élites qui foncent sur tes étoiles pour les dévorer et grossir.
- **L’Éclipse : le Dévoreur d’étoiles.** Une arène dont on ne sort pas. Il **mange tes étoiles** pour se soigner, mais une supernova déclenchée par ton Pas lunaire **sur lui** le blesse ×2,5. Trois phases : rayon du Néant, puits gravitationnels, puis **éclipse** où seules tes étoiles éclairent l’arène.

### Le reste
- **Trois difficultés** (Normal, Héroïque, Légendaire) et **le camp** : runes gagnées à chaque mission, améliorations permanentes, défis de déblocage. Progression sauvegardée dans le navigateur.
- **Rendu** : éclairage dynamique, sol peint par morceaux, forêts et ruines, braseros, halos, fumée, brume.
- L’armée (v0.9) est désactivée, et les anciennes missions à objectifs sont mises de côté.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Débit et PV des ennemis, marées, XP, élites, encerclements, rythme des objectifs, PV des boss, runes gagnées |
| `HEROES`, `FACTIONS`, `ULTS` | Champions, arme signature, sorts, ultimes |
| `STAR`, `TREE` | Kit de Lyriel (étoiles, constellation, supernova, flèches) et son arbre de talents |
| `SPELLS` | Sorts (dont Étoile filante et Pas lunaire) |
| `MAPS`, `EVENTS`, `DIFFS` | Missions (chronologie d’événements, boss), difficultés |
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
- v0.10 : refonte centrée champion : Lyriel et ses constellations (étoiles, prisme, supernova), arbre de talents à 3 branches, mission à événements, boss Dévoreur d’étoiles en 3 phases. Armes génériques et armée retirées.
