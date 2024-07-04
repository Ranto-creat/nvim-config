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

### Tableau des Commandes de Déplacement dans Vim

| **Action**                        | **Commande**                   | **Description**                                              |
| --------------------------------- | ------------------------------ | ------------------------------------------------------------ |
| **Déplacer le curseur**           |                                |                                                              |
| Gauche                            | `h`                            | Déplace le curseur d'un caractère à gauche                   |
| Bas                               | `j`                            | Déplace le curseur d'une ligne vers le bas                   |
| Haut                              | `k`                            | Déplace le curseur d'une ligne vers le haut                  |
| Droite                            | `l`                            | Déplace le curseur d'un caractère à droite                   |
| **Mouvements par Mot**            |                                |                                                              |
| Avancer d'un mot                  | `w`                            | Déplace le curseur au début du mot suivant                   |
| Reculer d'un mot                  | `b`                            | Déplace le curseur au début du mot précédent                 |
| Fin du mot                        | `e`                            | Déplace le curseur à la fin du mot                           |
| **Mouvements par Ligne**          |                                |                                                              |
| Début de la ligne                 | `0`                            | Déplace le curseur au début de la ligne                      |
| Fin de la ligne                   | `$`                            | Déplace le curseur à la fin de la ligne                      |
| **Déplacements Avancés**          |                                |                                                              |
| Début du fichier                  | `gg`                           | Déplace le curseur au début du fichier                       |
| Fin du fichier                    | `G`                            | Déplace le curseur à la fin du fichier                       |
| Aller à une ligne spécifique      | `:{numéro de ligne}` + `Enter` | Déplace le curseur à une ligne spécifiée                     |
| Afficher la position actuelle     | `Ctrl + g`                     | Affiche la position actuelle du curseur                      |
| **Scrolling**                     |                                |                                                              |
| Avancer d'une page                | `Ctrl + f`                     | Fait défiler l'écran vers le bas                             |
| Reculer d'une page                | `Ctrl + b`                     | Fait défiler l'écran vers le haut                            |
| Avancer d'une demi-page           | `Ctrl + d`                     | Fait défiler l'écran vers le bas en demi-page                |
| Reculer d'une demi-page           | `Ctrl + u`                     | Fait défiler l'écran vers le haut en demi-page               |
| **Marques et Signets**            |                                |                                                              |
| Placer une marque                 | `m{lettre}`                    | Place une marque à la position actuelle (ex: `ma` pour 'a')  |
| Aller à une marque                | `'{lettre}`                    | Déplace le curseur à la ligne de la marque nommée (ex: `'a`) |
| **Recherche**                     |                                |                                                              |
| Rechercher un mot                 | `/motif`                       | Recherche un motif vers l'avant                              |
| Rechercher en arrière             | `?motif`                       | Recherche un motif en arrière                                |
| Aller à l'occurrence suivante     | `n`                            | Va à la prochaine occurrence du motif                        |
| Aller à l'occurrence précédente   | `N`                            | Va à l'occurrence précédente du motif                        |
| **Répétition et Macros**          |                                |                                                              |
| Répéter la dernière commande      | `.`                            | Répète la dernière action                                    |
| Exécuter une macro                | `@{lettre}`                    | Exécute la macro enregistrée dans le registre (ex: `@a`)     |
| Exécuter une macro plusieurs fois | `nombre@{lettre}`              |

## Renomer le fichier actuel

``:saveas nouveau_nom.txt``
