# Runes & Remparts

Prototype jouable d’un tower defense rogue-like en heroic fantasy, pensé pour mobile (paysage), en solo et bientôt en coop.
Ce dépôt sert de terrain d’essai avant le passage sur Unity.

**Jouer :** https://gajacgabriel.github.io/runes-remparts/

## Le concept

- **3 factions asymétriques**, à la StarCraft : Orcs (bon marché, nombreux), Nains (économie et ingénierie), Elfes (chers, précis, dépendants du cristal).
- **Économie à deux ressources** : or et cristal, exploités sur des gisements dont certains sont exposés aux pillards.
- **Rogue-like** : chaque niveau gagné propose 3 cartes d’amélioration (puissance, effets, économie, héroïque, faction), avec des synergies.
- **Héros et sorts** : un héros déplaçable par faction et deux sorts à recharge pour agir pendant les vagues.
- 20 vagues, 4 boss, environ 12 minutes par run.

## Installer comme une appli (Android)

1. Ouvre le lien dans Chrome.
2. Menu ⋮ → **Ajouter à l’écran d’accueil** (ou **Installer l’application**).
3. Lance le jeu depuis l’icône : il s’ouvre en plein écran et en paysage, et fonctionne hors ligne.

## Itérer sur l’équilibrage

Tout tient dans `index.html`. Les réglages de design sont regroupés en haut du script :

| Bloc | Contenu |
|---|---|
| `BAL` | Vies, pauses entre vagues, courbe de PV, XP, combo, héros |
| `FACTIONS` | Ressources de départ, revenu passif, niveau max des tours |
| `HEROES`, `SPELL1`, `SPELL2` | Héros et sorts de chaque faction |
| `BUILD` | Tours, casernes et mines (coûts, dégâts, portée…) |
| `ENEMIES`, `WAVES` | Bestiaire et composition des 20 vagues |
| `CARDS` | Les cartes d’amélioration et leurs effets |

En jeu, le menu pause contient des **outils de test** (or, niveau, vague suivante, vies infinies), et la console expose `window.RR` pour simuler des runs.
