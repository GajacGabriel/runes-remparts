# Runes & Remparts

Prototype jouable d’un jeu de siège rogue-like en heroic fantasy, pensé pour mobile (paysage), en solo et bientôt en coop.
Ce dépôt sert de terrain d’essai avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.3 : la citadelle assiégée)

- **Siège de 10 minutes** : la horde sort de la forêt **de tous les côtés** et fonce sur la citadelle, au centre de la carte. Le flux est continu, avec une **marée** chaque minute, une **élite** chaque minute et **4 boss** (2:30, 5:00, 7:30, 10:00). Vaincre le boss final gagne la run.
- **Des centaines d’ennemis fragiles** (jusqu’à 400 à l’écran) et des chiffres de dégâts : la sensation survivor.
- **La citadelle tire elle-même** à 360° ; les tours se construisent sur **trois anneaux** d’emplacements autour d’elle.
- **3 factions asymétriques**, à la StarCraft : Orcs (bon marché, nombreux), Nains (artillerie, économie), Elfes (chers, précis, dépendants du cristal).
- **Économie à deux ressources** : or (kills, mines) et cristal (élites, boss, extracteurs exposés aux pillards).
- **Rogue-like** : chaque niveau propose 3 cartes d’amélioration, avec synergies.
- **Évolutions de tours** : une tour au niveau max + une carte précise devient légendaire (Tempête de haches, Baliste runique, Prisme stellaire…).
- **Ultime de faction** rechargé par les kills : WAAAGH !, Barrage runique, Nuit des étoiles.
- **Héros et sorts** pour agir pendant le siège.

## Installer comme une appli (Android)

1. Ouvre le lien dans Chrome.
2. Menu ⋮ → **Ajouter à l’écran d’accueil** (ou **Installer l’application**).
3. Lance le jeu depuis l’icône : il s’ouvre en plein écran et en paysage, et fonctionne hors ligne.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Vies, coûts d’amélioration, XP, combo, héros, ultime |
| `HORDE` | Débit d’ennemis, marées, courbe de PV, élites, boss |
| `FACTIONS` | Ressources de départ, revenu passif, niveau max des tours |
| `HEROES`, `SPELL1`, `SPELL2`, `ULTS` | Héros, sorts et ultimes de chaque faction |
| `BUILD`, `CIT_DEF`, `EVOS` | Tours, casernes, mines, citadelle et évolutions |
| `ENEMIES` | Bestiaire |
| `CARDS` | Les cartes d’amélioration et leurs effets |

En jeu, le menu pause contient des **outils de test** (or, niveau, +1 minute, recharge des sorts et de l’ultime, vies infinies), et la console expose `window.RR` pour simuler des runs.
