# custom-tcg — Booster perso

Faites vos propres cartes à collectionner, ouvrez des boosters et partagez vos créations.

**Booster perso** est un petit jeu de cartes à collectionner (TCG) qui tient dans **un seul fichier HTML**. Vous créez vos cartes avec vos images, puis vous ouvrez des boosters pour les obtenir au hasard. Les tirages sont pondérés selon la rareté et accompagnés d'animations. Aucune installation, aucun serveur, aucun compte : tout se passe dans le navigateur.

Les cartes que vous choisissez de rendre **publiques** rejoignent la galerie [Cartes communautaires de NSI Hub](https://rafaelmmix.github.io/nsi/cartes.html), après validation.

🎮 **[Jouer à Booster perso](https://rafaelmmix.github.io/custom-tcg/tcg-cartes.html)**

---

## Sommaire

- [Fonctionnalités](#fonctionnalités)
- [Démarrage rapide](#démarrage-rapide)
- [Utilisation](#utilisation)
  - [Créer une carte](#créer-une-carte)
  - [Ouvrir un booster](#ouvrir-un-booster)
  - [Gérer sa collection](#gérer-sa-collection)
  - [Sauvegarder sa collection](#sauvegarder-sa-collection)
  - [Partager une carte](#partager-une-carte)
  - [Publier une carte sur NSI Hub](#publier-une-carte-sur-nsi-hub)
- [Règles du jeu](#règles-du-jeu)
- [Données et stockage](#données-et-stockage)
- [Format des codes de partage](#format-des-codes-de-partage)
- [Personnalisation](#personnalisation)
- [Compatibilité](#compatibilité)
- [Limites connues](#limites-connues)
- [Responsabilité](#responsabilité)
- [Structure du projet](#structure-du-projet)
- [Contribuer](#contribuer)

---

## Fonctionnalités

- 🎨 **Création de cartes** : nom, rareté, type (élément), image recadrable et description, avec un aperçu en direct.
- 💎 **7 raretés** : Commune, Rare, Épique, Légendaire, Super légendaire, Mythique et Perdue, chacune avec son apparence.
- 🃏 **Boosters de 5 cartes** : tirage pondéré par la rareté, avec au moins une carte Rare ou mieux par booster.
- ✨ **Animations de révélation** : retournement des cartes, aura de « charge » de plus en plus longue avant une carte rare, éclairs, étincelles, rayons, pluie dorée, secousse de l'écran… et une mise en scène propre à chaque rareté supérieure (braises rouges, étoiles en orbite, voile d'obscurité et feux follets).
- 📚 **Collection** : deux vues (cartes *obtenues* et cartes *créées*), avec recherche, filtres par rareté et par type, tri et compteur de doublons.
- 🔍 **Vue agrandie** : carte en grand avec navigation au clavier, par boutons ou par balayage sur mobile.
- 💾 **Sauvegarde complète** : export et restauration de toute la collection dans un fichier, pour ne jamais perdre ses cartes.
- 🔗 **Partage par code** : chaque carte, image comprise, est encodée dans un code texte à copier-coller sur un autre appareil.
- 🌍 **Cartes privées ou publiques** : une carte publique est proposée à la galerie communautaire de NSI Hub.
- 🪞 **Effets visuels** : inclinaison 3D au survol, reflets holographiques sur les cartes les plus rares.
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

> 💡 Le jeu est publié avec **GitHub Pages** : chaque modification poussée sur la branche `main` met le site à jour automatiquement en une à deux minutes.

---

## Utilisation

L'application comporte trois onglets : **Tirer**, **Mes cartes** et **Créer une carte**.

### Créer une carte

Dans l'onglet **Créer une carte** :

| Champ | Détails |
|---|---|
| **Nom** | Obligatoire, 32 caractères maximum. |
| **Rareté** | De Commune à Perdue. Elle détermine l'apparence de la carte et sa probabilité de tirage. |
| **Type** | Neutre, 🔥 Feu, 💧 Eau, 🌿 Nature, 🌙 Ombre ou ✨ Lumière. Il donne une couleur au cadre et ajoute une icône à côté du nom. |
| **Image** | Facultative. Après l'import, **faites glisser** l'image pour choisir la zone visible et utilisez le curseur **Zoom** (×1 à ×3). L'image est enregistrée en 240 × 160 px. |
| **Description** | Facultative, 160 caractères maximum. Elle peut contenir un effet, une citation ou un texte d'ambiance. |
| **Visibilité** | 🔒 **Privée** (la carte reste sur votre appareil) ou 🌍 **Publique** (elle est aussi proposée sur NSI Hub, avec votre pseudo). |
| **Responsabilité** | Case obligatoire : vous confirmez être seul·e responsable du contenu de la carte. Elle se décoche à chaque nouvelle carte. |

L'aperçu se met à jour à chaque modification. Cliquez sur **Enregistrer la carte** (ou **Enregistrer et publier**) : la carte rejoint vos créations.

Pour modifier une carte existante : **Mes cartes → Créées → Modifier**.

### Ouvrir un booster

Dans l'onglet **Tirer** :

1. Cliquez sur le **booster** pour l'ouvrir.
2. Cliquez sur la pile, ou appuyez sur `Entrée` ou `Espace`, pour **révéler** la carte du dessus.
3. Cliquez de nouveau pour la **mettre de côté** et passer à la suivante.
4. À la fin, les 5 cartes s'affichent ensemble. Cliquez sur **Ouvrir un autre booster** pour recommencer.

Les cartes sont révélées de la plus commune à la plus rare : la meilleure arrive toujours en dernier. Chaque carte révélée rejoint votre collection, et un message indique s'il s'agit d'une **nouvelle carte** ou d'un doublon (×2, ×3…).

> ⚠️ Une carte ne peut sortir d'un booster que si elle existe dans votre collection : créez au moins une carte de chaque rareté que vous voulez pouvoir tirer.

### Gérer sa collection

Dans l'onglet **Mes cartes** :

- **Obtenues** : les cartes tirées dans les boosters, avec un badge ×N pour les doublons et un compteur de progression (cartes obtenues / cartes existantes).
- **Créées** : toutes vos créations, avec les boutons **Modifier**, **Partager**, **Publier** et **Supprimer**. La suppression demande un second clic de confirmation dans les 3 secondes. Les cartes déjà envoyées sur NSI Hub portent un badge « 🌍 Envoyée ».

Les outils disponibles dans les deux vues :

- recherche par nom ;
- filtre par rareté ;
- filtre par type ;
- tri : plus récentes, plus anciennes, nom (A → Z), rareté croissante ou décroissante ;
- lien vers les **cartes publiques** de NSI Hub.

Cliquez sur une carte pour l'afficher **en grand**. Dans cette vue :

| Action | Clavier | Souris / tactile |
|---|---|---|
| Carte suivante | `→` | bouton › ou balayage vers la gauche |
| Carte précédente | `←` | bouton ‹ ou balayage vers la droite |
| Fermer | `Échap` | bouton ✕ ou clic en dehors de la carte |

### Sauvegarder sa collection

Les cartes sont enregistrées dans le navigateur : vider ses données ou changer d'appareil les efface. Pour ne rien perdre, utilisez le panneau **💾 Sauvegarde de la collection** de l'onglet **Mes cartes** :

- **Exporter ma collection** télécharge un fichier `booster-perso-AAAA-MM-JJ.json` contenant toutes vos cartes créées et vos cartes obtenues (avec leurs exemplaires).
- **Restaurer une sauvegarde** réimporte ce fichier. Les cartes sont **fusionnées** avec la collection actuelle : rien n'est supprimé, les doublons sont ignorés et les compteurs d'exemplaires sont conservés.

Le jeu demande aussi au navigateur un **stockage persistant**, ce qui réduit le risque qu'il efface les données de lui-même.

### Partager une carte

1. **Mes cartes → Créées → Partager** : le code de la carte s'affiche et est copié dans le presse-papiers.
2. Envoyez ce code (il commence par `TCG1-` ou `TCG0-`) à qui vous voulez.
3. Sur l'autre appareil : **Mes cartes → Créées**, collez le code dans **Importer une carte avec un code**, puis cliquez sur **Importer la carte**.

Le code contient la carte entière, image comprise : aucun serveur n'est nécessaire. Si la même carte existe déjà dans la collection, l'import est refusé pour éviter les doublons.

### Publier une carte sur NSI Hub

Une carte publique est proposée à la galerie [Cartes communautaires](https://rafaelmmix.github.io/nsi/cartes.html) de NSI Hub. Il faut un compte GitHub (gratuit).

1. Créez la carte en choisissant **🌍 Publique** et un pseudo, ou cliquez sur **Publier** sur une carte déjà créée.
2. Cliquez sur **Envoyer sur GitHub** : une demande déjà remplie s'ouvre sur le dépôt [RafaelMMIX/nsi](https://github.com/RafaelMMIX/nsi). Si le champ du code est vide (carte avec une grande image), collez-le : il a été copié automatiquement.
3. Validez la demande sur GitHub.
4. Rafael vérifie la carte. S'il l'approuve, elle est ajoutée automatiquement à la galerie et vous recevez une réponse sur la demande.

Évitez d'utiliser votre nom complet comme pseudo : il est affiché publiquement sous la carte.

---

## Règles du jeu

### Probabilités de tirage

Chaque rareté a un poids :

| Rareté | Poids | Probabilité (si les 7 raretés existent) |
|---|---|---|
| Commune | 60 | ≈ 58,8 % |
| Rare | 25 | ≈ 24,5 % |
| Épique | 11 | ≈ 10,8 % |
| Légendaire | 4 | ≈ 3,9 % (1 sur 25) |
| Super légendaire | 1,4 | ≈ 1,4 % (1 sur 73) |
| Mythique | 0,45 | ≈ 0,44 % (1 sur 227) |
| Perdue | 0,12 | ≈ 0,12 % (1 sur 850) |

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
| `tcg-pseudo-v1` | Le dernier pseudo utilisé pour publier une carte. |

Conséquences :

- les cartes sont **propres à chaque navigateur et à chaque appareil** ; utilisez la sauvegarde ou les codes de partage pour les transférer ;
- vider les données du site, ou naviguer en mode privé, **efface la collection** : exportez-la régulièrement ;
- le `localStorage` est limité à environ 5 Mo par site selon les navigateurs. Les images sont compressées en JPEG (240 × 160 px, qualité 70 %) pour en stocker un maximum. Si l'espace manque, un message vous invite à supprimer des cartes.

Seules les cartes que vous publiez vous-même quittent votre navigateur : elles sont envoyées sur GitHub, avec votre pseudo, quand vous validez la demande.

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

Les clés de rareté sont : `commune`, `rare`, `epique`, `legendaire`, `superlegendaire`, `mythique`, `perdue`.

---

## Personnalisation

Tout se trouve dans `tcg-cartes.html`.

**Modifier les probabilités ou les noms des raretés** : objet `RAR` au début du `<script>`.

```js
const RAR = {
  commune:         { l: "Commune",          w: 60 },
  rare:            { l: "Rare",             w: 25 },
  epique:          { l: "Épique",           w: 11 },
  legendaire:      { l: "Légendaire",       w: 4 },
  superlegendaire: { l: "Super légendaire", w: 1.4 },
  mythique:        { l: "Mythique",         w: 0.45 },
  perdue:          { l: "Perdue",           w: 0.12 }
};
```

Pour ajouter une rareté, pensez aussi à l'ajouter dans `ORDER` (ordre de révélation), dans `FXC` (couleur des effets), dans la liste du formulaire et dans les styles CSS `.card[data-r="…"]`. Pour qu'elle soit acceptée sur NSI Hub, ajoutez-la aussi dans `tcg-share.js` et dans `.github/scripts/ajouter-carte.mjs` du dépôt `nsi`.

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

Elle utilise notamment `color-mix()` et `:has()` en CSS, l'API `CompressionStream` (avec un repli sur le format `TCG0` si elle est absente) et l'API Presse-papiers (avec un repli : le code reste affiché pour une copie manuelle).

Les polices Cinzel et Nunito sont chargées depuis Google Fonts. Hors ligne, l'application fonctionne avec des polices de remplacement.

---

## Limites connues

- Pas de synchronisation automatique entre appareils : utilisez l'export de la collection ou les codes de partage.
- Le nombre de cartes stockables dépend de l'espace `localStorage` disponible.
- Publier une carte nécessite un compte GitHub, et les cartes très lourdes doivent être collées à la main dans la demande.
- Les cartes publiques de NSI Hub ne sont pas encore tirables dans les boosters : il faut les importer avec leur code.
- Il n'y a pas de règles de combat : les cartes sont à collectionner, pas à jouer.

---

## Responsabilité

Booster perso a été créé par **Rafael**, qui n'est pas l'auteur des cartes créées, importées ou partagées par les utilisateurs. Chaque utilisateur est seul responsable des cartes qu'il crée ou publie (noms, descriptions, images) et de tout ce qui s'y rattache, notamment le respect des droits d'auteur, du droit à l'image et de la loi. Les cartes publiques sont vérifiées avant d'apparaître sur NSI Hub, et peuvent être refusées ou retirées à tout moment.

---

## Structure du projet

```
custom-tcg/
├── README.md          ce fichier
└── tcg-cartes.html    l'application complète (HTML + CSS + JavaScript)
```

La galerie communautaire et la publication automatique des cartes se trouvent dans le dépôt [RafaelMMIX/nsi](https://github.com/RafaelMMIX/nsi) (`cartes.html`, `cartes.js`, `tcg-share.js`, `cartes-publiques.json` et `.github/`).

---

## Contribuer

Les idées et les améliorations sont les bienvenues :

1. Forkez le dépôt.
2. Créez une branche : `git checkout -b ma-fonctionnalite`.
3. Testez vos modifications en ouvrant `tcg-cartes.html` dans un navigateur.
4. Ouvrez une *pull request* en décrivant le changement.

Quelques pistes : boosters avec les cartes publiques, échanges entre joueurs, monnaie et boutique, statistiques de tirage, nouveaux types, cartes avec attaque et défense, mode hors ligne (PWA).
