# custom-tcg — Booster perso

Faites vos propres cartes à collectionner, ouvrez des boosters et partagez vos créations.

**Booster perso** est un petit jeu de cartes à collectionner (TCG) qui tient dans **un seul fichier HTML**. Vous créez vos cartes avec vos images, puis vous ouvrez des boosters pour les obtenir au hasard. Les tirages sont pondérés selon la rareté et accompagnés d'animations. Aucune installation, aucun serveur, aucun compte : tout se passe dans le navigateur.

---

## Sommaire

- [Fonctionnalités](#fonctionnalités)
- [Démarrage rapide](#démarrage-rapide)
- [Utilisation](#utilisation)
  - [Créer une carte](#créer-une-carte)
  - [Ouvrir un booster](#ouvrir-un-booster)
  - [Gérer sa collection](#gérer-sa-collection)
  - [Partager une carte](#partager-une-carte)
- [Règles du jeu](#règles-du-jeu)
- [Données et stockage](#données-et-stockage)
- [Format des codes de partage](#format-des-codes-de-partage)
- [Personnalisation](#personnalisation)
- [Compatibilité](#compatibilité)
- [Limites connues](#limites-connues)
- [Structure du projet](#structure-du-projet)
- [Contribuer](#contribuer)

---

## Fonctionnalités

- 🎨 **Création de cartes** : nom, rareté, type (élément), image recadrable et description, avec un aperçu en direct.
- 🃏 **Boosters de 5 cartes** : tirage pondéré par la rareté, avec au moins une carte Rare ou mieux par booster.
- ✨ **Animations de révélation** : retournement des cartes, aura de « charge » avant une carte rare, éclairs, étincelles, rayons, pluie dorée et secousse de l'écran pour une Légendaire.
- 📚 **Collection** : deux vues (cartes *obtenues* et cartes *créées*), avec recherche, filtres par rareté et par type, tri et compteur de doublons.
- 🔍 **Vue agrandie** : carte en grand avec navigation au clavier, par boutons ou par balayage sur mobile.
- 🔗 **Partage par code** : chaque carte, image comprise, est encodée dans un code texte à copier-coller sur un autre appareil.
- 🪞 **Effets visuels** : inclinaison 3D au survol, reflet holographique sur les cartes Épiques et Légendaires.
- 🌗 **Thème clair et sombre** automatique, selon les réglages du système.
- ♿ **Accessibilité** : navigation au clavier, rôles ARIA, et animations désactivées si le système demande de réduire les mouvements.

---

## Démarrage rapide

1. Téléchargez ou clonez le dépôt :
   ```bash
   git clone https://github.com/RafaelMMIX/custom-tcg.git
   ```
2. Ouvrez `tcg-cartes.html` dans votre navigateur (double-clic sur le fichier).

C'est tout. Il n'y a ni dépendance à installer ni étape de compilation.

> 💡 Pour y jouer en ligne, publiez le fichier sur n'importe quel hébergement statique, par exemple **GitHub Pages** : *Settings → Pages*, choisissez la branche `main`, puis ouvrez `https://<utilisateur>.github.io/custom-tcg/tcg-cartes.html`. Vous pouvez aussi renommer le fichier en `index.html` pour que l'adresse racine suffise.

---

## Utilisation

L'application comporte trois onglets : **Tirer**, **Mes cartes** et **Créer une carte**.

### Créer une carte

Dans l'onglet **Créer une carte** :

| Champ | Détails |
|---|---|
| **Nom** | Obligatoire, 32 caractères maximum. |
| **Rareté** | Commune, Rare, Épique ou Légendaire. Elle détermine la couleur de la carte et sa probabilité de tirage. |
| **Type** | Neutre, 🔥 Feu, 💧 Eau, 🌿 Nature, 🌙 Ombre ou ✨ Lumière. Il donne une couleur au cadre et ajoute une icône à côté du nom. |
| **Image** | Facultative. Après l'import, **faites glisser** l'image pour choisir la zone visible et utilisez le curseur **Zoom** (×1 à ×3). L'image est enregistrée en 240 × 160 px. |
| **Description** | Facultative, 160 caractères maximum. Elle peut contenir un effet, une citation ou un texte d'ambiance. |

L'aperçu à droite se met à jour à chaque modification. Cliquez sur **Enregistrer la carte** : la carte rejoint vos créations et son code de partage est copié automatiquement.

Pour modifier une carte existante : **Mes cartes → Créées → Modifier**.

### Ouvrir un booster

Dans l'onglet **Tirer** :

1. Cliquez sur le **booster** pour l'ouvrir.
2. Cliquez sur la pile, ou appuyez sur `Entrée` ou `Espace`, pour **révéler** la carte du dessus.
3. Cliquez de nouveau pour la **mettre de côté** et passer à la suivante.
4. À la fin, les 5 cartes s'affichent ensemble. Cliquez sur **Ouvrir un autre booster** pour recommencer.

Les cartes sont révélées de la plus commune à la plus rare : la meilleure arrive toujours en dernier. Chaque carte révélée rejoint votre collection, et un message indique s'il s'agit d'une **nouvelle carte** ou d'un doublon (×2, ×3…).

> ⚠️ Il faut avoir créé au moins une carte pour pouvoir ouvrir un booster.

### Gérer sa collection

Dans l'onglet **Mes cartes** :

- **Obtenues** : les cartes tirées dans les boosters, avec un badge ×N pour les doublons et un compteur de progression (cartes obtenues / cartes existantes).
- **Créées** : toutes vos créations, avec les boutons **Modifier**, **Partager** et **Supprimer**. La suppression demande un second clic de confirmation dans les 3 secondes.

Les outils disponibles dans les deux vues :

- recherche par nom ;
- filtre par rareté ;
- filtre par type ;
- tri : plus récentes, plus anciennes, nom (A → Z), rareté croissante ou décroissante.

Cliquez sur une carte pour l'afficher **en grand**. Dans cette vue :

| Action | Clavier | Souris / tactile |
|---|---|---|
| Carte suivante | `→` | bouton › ou balayage vers la gauche |
| Carte précédente | `←` | bouton ‹ ou balayage vers la droite |
| Fermer | `Échap` | bouton ✕ ou clic en dehors de la carte |

### Partager une carte

1. **Mes cartes → Créées → Partager** : le code de la carte s'affiche et est copié dans le presse-papiers.
2. Envoyez ce code (il commence par `TCG1-` ou `TCG0-`) à qui vous voulez.
3. Sur l'autre appareil : **Mes cartes → Créées**, collez le code dans **Importer une carte avec un code**, puis cliquez sur **Importer la carte**.

Le code contient la carte entière, image comprise : aucun serveur n'est nécessaire. Si la même carte existe déjà dans la collection, l'import est refusé pour éviter les doublons.

---

## Règles du jeu

### Probabilités de tirage

Chaque rareté a un poids :

| Rareté | Poids | Probabilité (si les 4 raretés existent) |
|---|---|---|
| Commune | 60 | 60 % |
| Rare | 25 | 25 % |
| Épique | 11 | 11 % |
| Légendaire | 4 | 4 % |

Le tirage se fait en deux temps : l'application choisit d'abord une **rareté** selon ces poids, puis une **carte au hasard** parmi celles de cette rareté. Seules les raretés présentes dans vos cartes comptent. Par exemple, si vous n'avez créé que des Communes et des Légendaires, une Légendaire sort avec une probabilité de 4 / (60 + 4), soit environ 6 %.

### Composition d'un booster

- **4 cartes** tirées normalement ;
- **1 carte garantie Rare ou mieux**, à condition qu'au moins une carte non commune existe ;
- les cartes sont ensuite triées par rareté croissante pour la révélation.

---

## Données et stockage

Toutes les données restent **dans votre navigateur**, dans le `localStorage` :

| Clé | Contenu |
|---|---|
| `tcg-cartes-v1` | La liste des cartes créées ou importées (nom, rareté, type, description, image en base64). |
| `tcg-owned-v1` | Les cartes obtenues et leur nombre d'exemplaires. |

Conséquences :

- les cartes sont **propres à chaque navigateur et à chaque appareil** ; utilisez les codes de partage pour les transférer ;
- vider les données du site, ou naviguer en mode privé, **efface la collection** ;
- le `localStorage` est limité à environ 5 Mo par site selon les navigateurs. Les images sont compressées en JPEG (240 × 160 px, qualité 70 %) pour en stocker un maximum. Si l'espace manque, un message vous invite à supprimer des cartes.

---

## Format des codes de partage

Pour les curieux et les contributeurs :

```
TCG1-<données>   données compressées (deflate-raw), puis encodées en base64url
TCG0-<données>   données non compressées, encodées en base64url (navigateurs sans CompressionStream)
```

Une fois décodées, les données forment un tableau JSON :

```json
["Nom", "rarete", "Description", "data:image/jpeg;base64,...", "type"]
```

Le type est omis pour une carte Neutre. À l'import, l'application vérifie chaque champ : rareté connue, nom non vide, longueurs maximales, image limitée aux formats `data:image/jpeg|png|webp`, et type connu (sinon *Neutre*).

---

## Personnalisation

Tout se trouve dans `tcg-cartes.html`.

**Modifier les probabilités ou les noms des raretés** : objet `RAR` au début du `<script>`.

```js
const RAR = {
  commune:    { l: "Commune",    w: 60 },
  rare:       { l: "Rare",       w: 25 },
  epique:     { l: "Épique",     w: 11 },
  legendaire: { l: "Légendaire", w: 4 }
};
```

**Ajouter ou modifier un type** : objet `TYPES` (`l` = libellé, `i` = icône, `c` = couleur du cadre).

```js
const TYPES = {
  // ...
  foudre: { l: "Foudre", i: "⚡", c: "#f0c419" }
};
```

**Changer les couleurs** : variables CSS dans `:root`, par exemple `--c-commune`, `--c-rare`, `--c-epique`, `--c-legendaire` pour les raretés et `--accent` pour la couleur principale.

**Changer la taille d'un booster** : fonction `makeBooster()`, qui tire 4 cartes puis 1 carte garantie. Pensez aussi à mettre à jour le texte « 5 cartes » sur le booster.

> ⚠️ Si vous renommez une clé de rareté ou de type, les cartes déjà enregistrées et les codes déjà partagés qui l'utilisent ne seront plus reconnus.

---

## Compatibilité

L'application fonctionne sur les versions récentes de **Chrome, Edge, Firefox et Safari**, sur ordinateur comme sur mobile.

Elle utilise notamment `color-mix()` en CSS, l'API `CompressionStream` (avec un repli sur le format `TCG0` si elle est absente) et l'API Presse-papiers (avec un repli : le code reste affiché pour une copie manuelle).

Les polices Cinzel et Nunito sont chargées depuis Google Fonts. Hors ligne, l'application fonctionne avec des polices de remplacement.

---

## Limites connues

- Pas de synchronisation entre appareils, à part les codes de partage.
- Pas d'export ou d'import de toute la collection en une seule fois.
- Le nombre de cartes stockables dépend de l'espace `localStorage` disponible.
- Il n'y a pas de règles de combat : les cartes sont à collectionner, pas à jouer.

---

## Structure du projet

```
custom-tcg/
├── README.md          ce fichier
└── tcg-cartes.html    l'application complète (HTML + CSS + JavaScript)
```

---

## Contribuer

Les idées et les améliorations sont les bienvenues :

1. Forkez le dépôt.
2. Créez une branche : `git checkout -b ma-fonctionnalite`.
3. Testez vos modifications en ouvrant `tcg-cartes.html` dans un navigateur.
4. Ouvrez une *pull request* en décrivant le changement.

Quelques pistes : export et import de la collection complète, statistiques de tirage, nouveaux types, cartes avec attaque et défense, mode hors ligne (PWA).
