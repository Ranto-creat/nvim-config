# Commandes

| Action                               | Commande                       |
| ------------------------------------ | ------------------------------ |
| **Copier une ligne entière**         | `yy`                           |
| **Copier plusieurs lignes**          | `3yy` (pour 3 lignes)          |
| **Copier une section de texte**      | `v` + `y` (sélection + copier) |
| **Copier un mot**                    | `yw`                           |
| **Copier jusqu’à la fin du fichier** | `yG`                           |
| **Coller après le curseur**          | `p`                            |
| **Coller avant le curseur**          | `P`                            |
| **Annuler la dernière action**       | `u`                            |
| **Refaire une action annulée**       | `Ctrl + r`                     |
| **Copier en mode visuel**            | `v` + `y`                      |
| **Coller en mode visuel**            | `p` / `P`                      |

## Some other Commandes with Vim

| Action                                                             | Commande                             |
| ------------------------------------------------------------------ | ------------------------------------ |
| **Mode Visuel Caractères** : Sélectionner des caractères un par un | `v`                                  |
| **Mode Visuel Lignes** : Sélectionner des lignes entières          | `V`                                  |
| **Mode Visuel en Bloc** : Sélectionner un bloc de texte            | `Ctrl + V`                           |
| **Copier Texte Sélectionné**                                       | `y` (ou `d` pour couper)             |
| **Coller Texte Copié**                                             | `p` (ou `P` pour coller avant)       |
| **Annuler Action**                                                 | `u`                                  |
| **Refaire Action**                                                 | `Ctrl + r`                           |
| **Rechercher un Mot**                                              | `/mot`                               |
| **Remplacer du Texte**                                             | `:%s/ancien/nouveau/g`               |
| **Enregistrer une Macro**                                          | `q` + lettre (ex: `qa`)              |
| **Jouer une Macro**                                                | `@` + lettre (ex: `@a`)              |
| **Jouer une Macro Plusieurs Fois**                                 | `nombre` + `@` + lettre (ex: `10@a`) |

## Astuces Supplémentaires

- **Sélectionner un Bloc de Texte :** Pour copier un bloc de texte, utilise le mode visuel avec `Ctrl + v` pour une sélection en bloc, puis `y` pour copier.

- **Afficher l’historique des actions :** Utilise `:undolist` pour voir l’historique des actions et choisir ce que tu veux annuler ou refaire.
