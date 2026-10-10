# Runes & Remparts

Prototype jouable d’un jeu d’action roguelite heroic fantasy pour **PC (clavier et souris)**, dans l’esprit du mode Swarm de League of Legends et de Ravenswatch.
Ce dépôt sert de terrain d’essai pour trouver le fun avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.11 : un champion, une carte, des quêtes)

**Un champion, une mécanique.** Chaque champion a une mécanique signature unique, et son arbre de talents la fait évoluer.
Lyriel est le premier champion jouable ; Grukk (la Hache liée) et Durgan (la Forge vivante) suivront.
**Une carte fixe** (le Val d’Astrée) remplace le terrain infini : des régions nommées, des lieux de quête, un cycle jour/nuit.

### Lyriel, Tisseuse d’étoiles
- **Clic gauche** : ses flèches lunaires partent en continu vers le curseur (C : visée automatique). ZQSD / WASD / flèches pour bouger.
- **Étoile filante** (**clic droit** ou E, 3 charges) : une comète plante une étoile au point visé.
- **Constellation** : dès 3 étoiles, elles se relient. Les **fils d’argent** brûlent ce qui les traverse, une **pluie d’astres** frappe l’intérieur.
- **Prisme** : une flèche qui traverse une étoile se divise en 3. On vise à travers ses propres étoiles.
- **Pas lunaire** (**Espace**) : dash invulnérable. **Traverser sa constellation la fait exploser en supernova** (le dash est rendu).
- **Voûte céleste** (**R**) : trois étoiles autour d’elle et, pendant 7 s, jusqu’à 6 étoiles toutes reliées.
- **L’arbre de Lyriel** (**T**) : chaque niveau donne un point de talent. Trois branches, **Astronome** (constellations), **Archère** (flèches), **Danseuse** (mobilité, supernova), à 4 paliers ouverts par les points investis dans la branche (3, 6, puis 10 pour la **légendaire** : *Zodiaque*, *Pluie d’argent* ou *Étoile du berger*).

### Le Val d’Astrée
- **Une carte de 4800 × 3600** bordée de forêts et de falaises : la Clairière du Guet, le Bois d’Argent, le Lac de Lune et sa rivière (deux ponts), le Hameau des Lucioles, le Marais cendré, le Camp des Pillards, les Ruines d’Astrée, les Hauts du Chef de guerre et l’Observatoire. L’eau et la roche bloquent le passage ; la horde contourne les obstacles (champ de chemins).
- **Minicarte** (**Tab** pour l’agrandir), **brouillard de guerre**, région affichée en cours de route.
- **Cycle jour/nuit** : Jour 1 (2:30), Nuit 1 (1:30, chute d’étoiles puis hérauts), Jour 2, Nuit 2 (lune de sang), puis **l’Éclipse**. La nuit, les étoiles de Lyriel frappent plus fort et durent plus longtemps, mais la horde se lève.
- **Quête principale : les Phares d’Astrée.** Trois phares gardés ; on plante ses étoiles sur leurs trois socles (elles s’y accrochent) et on protège le rituel contre les vagues et les hérauts. Chaque phare rallumé offre une relique et retire 15 % des PV du boss final.
- **Quêtes secondaires** : défendre le feu du Hameau des Lucioles (40 s), raser le Camp des Pillards (3 tentes et leur chef), abattre le Chef de guerre des Hauts (relique légendaire et point de talent), trouver les 6 **Menhirs de lune** (un point de talent chacun). À chaque aube et à chaque nuit, deux **nids de cendres** percent dans le val (un coffre chacun).
- **Reliques** (14, en trois raretés) : récompenses de quête, coffres, et le **colporteur** (**F**), qui vend aussi des potions et des parchemins de savoir.
- **L’Éclipse : le Dévoreur d’étoiles** attend à l’Observatoire. Il **mange tes étoiles** pour se soigner, mais une supernova déclenchée par ton Pas lunaire **sur lui** le blesse ×2,5. Trois phases : rayon du Néant, puits gravitationnels, puis **éclipse** où seules tes étoiles éclairent l’arène.

### Le reste
- **Trois difficultés** (Normal, Héroïque, Légendaire) et **le camp** : runes gagnées à chaque mission, améliorations permanentes, défis de déblocage. Progression sauvegardée dans le navigateur.
- **Rendu** : éclairage dynamique (jour doré, nuit bleue), sol peint par morceaux (marais, routes, dallages, eau, ponts, falaises), décor placé à la main par région, halos, fumée, brume.
- L’armée (v0.9) est désactivée, et les anciennes missions (objectifs, nuit des étoiles filantes) sont mises de côté.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Débit et PV des ennemis, XP, élites, PV des boss, runes gagnées |
| `HEROES`, `FACTIONS`, `ULTS` | Champions, arme signature, sorts, ultimes |
| `STAR`, `TREE`, `TIERS`, `TIER_NEED` | Kit de Lyriel (étoiles, constellation, supernova, flèches), son arbre de talents et ses paliers |
| `VAL` | La carte : lac, rivière, ponts, falaises, routes, régions, lieux de quête |
| `CYCLE`, `NIGHT`, `PHARE`, `QUESTS` | Durées du jour et de la nuit, bonus de nuit, rituel des phares, quêtes |
| `RELICS`, `RARITY` | Reliques et prix chez le colporteur |
| `SPELLS` | Sorts (dont Étoile filante et Pas lunaire) |
| `MAPS`, `EVENTS`, `DIFFS` | Missions, événements de nuit, difficultés |
| `CAMP`, `CHALLENGES` | Améliorations permanentes et défis de déblocage |
| `WEAPONS`, `PASSIVES`, `ENEMIES` | Armes, passifs, bestiaire |

Le menu pause contient des **outils de test** (+1 niveau, +1 minute, or, cristal, sorts prêts, invincibilité), et la console expose `window.RR` pour simuler des missions.

## Historique

- v0.1 à v0.2 : tower defense sur chemins, puis héros, sorts et pixel art.
- v0.3 : citadelle assiégée à 360°.
- v0.4 : pivot vers un survivor, après des playtests où l’on « cliquait sans réfléchir ».
- v0.5 à v0.6 : récolte, butin et remparts, en portrait mobile. Pas concluant : « un survivor comme les autres ».
- v0.7 : virage PC à la Swarm : visée à la souris, sorts actifs et talents, missions à objectifs, camp de progression.
- v0.8 : grosse passe graphique (éclairage dynamique, décors, effets) et sorts plus amusants (charges, onde de choc, faille, flèches chargées, marques et synergies).
- v0.9 : USP « la Horde retournée » : armée convertie par faction, ordres d’assaut et de ralliement, prisonniers, prise de fort, boss vaincu devenu général.
- v0.10 : refonte centrée champion : Lyriel et ses constellations (étoiles, prisme, supernova), arbre de talents à 3 branches, mission à événements, boss Dévoreur d’étoiles en 3 phases. Armes génériques et armée retirées.
- v0.11 : une carte fixe façon Ravenswatch, le Val d’Astrée (régions, eau et falaises, minicarte, brouillard de guerre), cycle jour/nuit, quête principale des Phares et quêtes secondaires, reliques et colporteur, arbre de talents en écran dédié avec paliers.
