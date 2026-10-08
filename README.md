# Runes & Remparts

Prototype jouable d’un survivor en heroic fantasy, pensé pour mobile (paysage).
Ce dépôt sert de terrain d’essai pour trouver le fun avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.4 : survivor)

- **Tu pilotes ton héros** au milieu de la horde (joystick au doigt, ou ZQSD / WASD / flèches). Les armes tirent toutes seules : ton travail, c’est le placement.
- **10 minutes de survie** : flux continu d’ennemis, marées chaque minute, encerclements, élites porteuses de coffres et **4 boss** aux attaques annoncées (invocations, charge, onde de choc, cercles de projectiles). Vaincre le boss de 10:00 gagne la run.
- **Gemmes d’XP à ramasser** : chaque niveau propose 3 cartes (nouvelle arme, amélioration, passif). 6 armes et 6 passifs maximum.
- **Évolutions** : arme au niveau 5 + passif associé + 1 cristal (lâché par les élites et les boss) = arme légendaire.
- **3 héros** : Grukk l’orc (haches tournoyantes, soif de sang), Durgan le nain (marteau, tourelles, mines), Lyriel l’elfe (arc, lames, ronces), plus 4 armes communes.
- **Ultime de faction** rechargé par les kills : WAAAGH !, Barrage runique, Nuit des étoiles.
- L’or sert à relancer les cartes.

## Installer comme une appli (Android)

1. Ouvre le lien dans Chrome.
2. Menu ⋮ → **Ajouter à l’écran d’accueil** (ou **Installer l’application**).
3. Lance le jeu depuis l’icône : il s’ouvre en plein écran et en paysage, et fonctionne hors ligne.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Durée, débit d’ennemis, marées, PV et dégâts ennemis, XP, élites, boss, encerclements |
| `HEROES`, `FACTIONS`, `ULTS` | Héros, armes de départ, ultimes |
| `WEAPONS` | Les 13 armes : stats de base, gains par niveau, évolution |
| `PASSIVES` | Les 12 passifs |
| `ENEMIES` | Bestiaire |

Le menu pause contient des **outils de test** (+1 niveau, +1 minute, or, cristal, ultime, invincibilité), et la console expose `window.RR` pour simuler des runs.

## Historique

- v0.1 à v0.2 : tower defense sur chemins, puis héros, sorts et pixel art.
- v0.3 : citadelle assiégée à 360°.
- v0.4 : pivot vers un survivor, après des playtests où l’on « cliquait sans réfléchir ».
