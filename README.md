# Runes & Remparts

Prototype jouable d’un survivor en heroic fantasy, pensé pour mobile **en portrait** (jouable d’un pouce).
Ce dépôt sert de terrain d’essai pour trouver le fun avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept (v0.5 : récolte et remparts)

- **Tu pilotes ton héros** au milieu de la horde (joystick au doigt, ou ZQSD / WASD / flèches). Les armes tirent toutes seules : ton travail, c’est le placement.
- **10 minutes de survie** : flux continu d’ennemis, marées chaque minute, encerclements, élites porteuses de coffres et **4 boss** aux attaques annoncées. Vaincre le boss de 10:00 gagne la run.
- **Gemmes d’XP** : chaque niveau propose 3 cartes (nouvelle arme, amélioration, passif). 6 armes et 6 passifs maximum.
- **Évolutions** : arme au niveau 5 + passif associé + 1 cristal (élites et boss) = arme légendaire.
- **Récolte** : rester dans le cercle d’un bosquet (bois) ou d’un rocher (pierre) remplit tes réserves, bien plus vite à l’arrêt. Les gisements s’épuisent puis repoussent.
- **Remparts** : trois ouvrages posés à tes pieds (boutons du bas ou touches 1, 2, 3).
  - **Palissade** (6 bois) : un mur en travers de ta course. La horde bute dessus, ton héros passe.
  - **Tour** (8 bois, 8 pierre) : tire sur les ennemis à portée ; ses dégâts suivent ton niveau.
  - **Piège** (5 pierre) : blesse et ralentit tout ce qui passe, jusqu’à usure.
  - Nombre limité par type : au-delà, le plus ancien s’effondre.
  - Contres : les harpies volent par-dessus, les torches des pillards brûlent les murs, les boss fracassent tout.
- **Asymétrie de factions** :
  - **Grukk** (orcs) récolte mal mais pille : 2 % des ennemis lâchent du bois ou de la pierre.
  - **Durgan** (nains) mine la pierre deux fois plus vite, et ses ouvrages sont 40 % plus solides et plus forts.
  - **Lyriel** (elfes) récolte le bois plus vite, et presque aussi vite en marchant.
- **Ultime de faction** rechargé par les kills : WAAAGH !, Barrage runique, Nuit des étoiles.
- Les coffres donnent une amélioration, du bois, de la pierre et une relance de cartes.

## Installer comme une appli (Android)

1. Ouvre le lien dans Chrome.
2. Menu ⋮ → **Ajouter à l’écran d’accueil** (ou **Installer l’application**).
3. Lance le jeu depuis l’icône : il s’ouvre en plein écran et en portrait, et fonctionne hors ligne.

Sur ordinateur, le jeu s’affiche dans un cadre au format téléphone.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Durée, débit d’ennemis, marées, PV et dégâts ennemis, XP, récolte, gisements, dégâts sur les ouvrages, boss |
| `HEROES`, `FACTIONS`, `ULTS` | Héros, armes de départ, bonus de récolte et de construction, ultimes |
| `BUILD` | Les 3 ouvrages : coût, maximum, PV, dégâts |
| `WEAPONS` | Les 13 armes : stats de base, gains par niveau, évolution |
| `PASSIVES` | Les 13 passifs (dont Récolteur et Maçonnerie) |
| `ENEMIES` | Bestiaire |

Le menu pause contient des **outils de test** (+1 niveau, +1 minute, bois et pierre, cristal, ultime, invincibilité), et la console expose `window.RR` pour simuler des runs.

## Historique

- v0.1 à v0.2 : tower defense sur chemins, puis héros, sorts et pixel art.
- v0.3 : citadelle assiégée à 360°.
- v0.4 : pivot vers un survivor, après des playtests où l’on « cliquait sans réfléchir ».
- v0.5 : récolte de bois et de pierre, remparts posés en pleine horde, passage en portrait.
