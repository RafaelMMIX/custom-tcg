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
  - [Créer ses boosters](#créer-ses-boosters)
  - [Faire un match à deux](#faire-un-match-à-deux)
  - [Gérer sa collection](#gérer-sa-collection)
  - [Sauvegarder sa collection](#sauvegarder-sa-collection)
  - [Partager une carte](#partager-une-carte)
  - [Publier une carte sur NSI Hub](#publier-une-carte-sur-nsi-hub)
  - [Publier un booster sur NSI Hub](#publier-un-booster-sur-nsi-hub)
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
- 🗡️ **Attaques** : chaque carte a 2 ou 3 attaques (nom + puissance), avec une fourchette de puissance par rareté pour garder des matchs équilibrés.
- 💎 **7 raretés** : Commune, Rare, Épique, Légendaire, Super légendaire, Mythique et Perdue, chacune avec son apparence.
- 🃏 **Boosters de 5 cartes** : tirage pondéré par la rareté, avec au moins une carte Rare ou mieux par booster.
- 🎁 **Boosters personnalisés** : rangez vos cartes dans des boosters (nom, emoji, couleur), ouvrez celui de votre choix, publiez-les sur NSI Hub et ouvrez ceux des autres.
- ✨ **Animations de révélation** : retournement des cartes, aura de « charge » de plus en plus longue avant une carte rare, éclairs, étincelles, rayons, pluie dorée, secousse de l'écran… et une mise en scène propre à chaque rareté supérieure (braises rouges, étoiles en orbite, voile d'obscurité et feux follets).
- 📚 **Collection** : deux vues (cartes *obtenues* et cartes *créées*), avec recherche, filtres par rareté et par type, tri et compteur de doublons.
- 🔍 **Vue agrandie** : carte en grand avec navigation au clavier, par boutons ou par balayage sur mobile.
- ⚔️ **Match à deux** : deux joueurs (sur le même appareil, ou sur deux appareils avec un code à 4 chiffres) choisissent chacun 3 cartes différentes, puis les deux équipes sont dévoilées (pas encore de combat).
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

L'application comporte cinq onglets : **Tirer**, **Mes cartes**, **Boosters**, **Match** et **Créer une carte**.

### Créer une carte

Dans l'onglet **Créer une carte** :

| Champ | Détails |
|---|---|
| **Nom** | Obligatoire, 32 caractères maximum. |
| **Rareté** | De Commune à Perdue. Elle détermine l'apparence de la carte et sa probabilité de tirage. |
| **Type** | Neutre, 🔥 Feu, 💧 Eau, 🌿 Nature, 🌙 Ombre ou ✨ Lumière. Il donne une couleur au cadre et ajoute une icône à côté du nom. |
| **Image** | Facultative. Après l'import, **faites glisser** l'image pour choisir la zone visible et utilisez le curseur **Zoom** (×1 à ×3). L'image est enregistrée en 240 × 160 px. |
| **Description** | Facultative, 160 caractères maximum. Elle peut contenir un effet, une citation ou un texte d'ambiance. |
| **Attaques** | **2 attaques obligatoires**, une 3e facultative. Chacune a un nom (20 caractères maximum) et une puissance réglée avec un curseur, limitée par la fourchette de la rareté (voir ci-dessous). Si vous changez la rareté, les curseurs gardent leur position relative dans la nouvelle fourchette. |
| **Visibilité** | 🔒 **Privée** (la carte reste sur votre appareil) ou 🌍 **Publique** (elle est aussi proposée sur NSI Hub, avec votre pseudo). |
| **Responsabilité** | Case obligatoire : vous confirmez être seul·e responsable du contenu de la carte. Elle se décoche à chaque nouvelle carte. |

L'aperçu se met à jour à chaque modification. Cliquez sur **Enregistrer la carte** (ou **Enregistrer et publier**) : la carte rejoint vos créations.

Pour modifier une carte existante : **Mes cartes → Créées → Modifier**.

### Ouvrir un booster

Dans l'onglet **Tirer** :

1. Si vous avez des boosters personnalisés, choisissez celui à ouvrir au-dessus du booster (ou « Toutes mes cartes »).
2. Cliquez sur le **booster** pour l'ouvrir.
3. Cliquez sur la pile, ou appuyez sur `Entrée` ou `Espace`, pour **révéler** la carte du dessus.
4. Cliquez de nouveau pour la **mettre de côté** et passer à la suivante.
5. À la fin, les 5 cartes s'affichent ensemble. Cliquez sur **Ouvrir un autre booster** pour recommencer.

Les cartes sont révélées de la plus commune à la plus rare : la meilleure arrive toujours en dernier. Chaque carte révélée rejoint votre collection, et un message indique s'il s'agit d'une **nouvelle carte** ou d'un doublon (×2, ×3…).

> ⚠️ Une carte ne peut sortir d'un booster que si elle en fait partie : créez au moins une carte de chaque rareté que vous voulez pouvoir tirer.

### Créer ses boosters

Dans l'onglet **Boosters**, cliquez sur **＋ Nouveau booster** :

- donnez-lui un **nom** (32 caractères maximum), un **emoji** et une **couleur** (10 couleurs proposées ou une couleur personnalisée) : l'aperçu montre le booster tel qu'il apparaîtra ;
- cochez les **cartes** qui en font partie. Un filtre par rareté et les boutons **Tout cocher** / **Tout décocher** aident à aller vite. Le compteur indique le nombre de cartes et de raretés couvertes.

Une même carte peut faire partie de plusieurs boosters. Chaque booster de la liste peut être **ouvert**, **modifié**, **publié** ou **supprimé**. Supprimer un booster ne supprime pas ses cartes.

Deux raccourcis :

- dans **Créer une carte**, le champ **Ajouter au booster** range directement la nouvelle carte dans un booster ;
- dans **Mes cartes**, le filtre **Tous les boosters** affiche seulement les cartes d'un booster.

### Faire un match à deux

Dans l'onglet **Match**, chaque joueur choisit **3 cartes différentes** parmi ses cartes obtenues (il en faut au moins 3). Un joueur peut prendre une carte que l'autre a aussi. Il n'y a pas encore de combat : le match s'arrête au dévoilement des équipes, placées sur un **terrain de football** (une équipe de chaque côté, l'une en haut et l'autre en bas sur mobile). Cliquez sur une carte pour l'agrandir.

**Sur le même appareil** : cliquez sur **Sur le même appareil**, saisissez les pseudos, puis **C'est parti !**. Le joueur 1 choisit, un écran de passage cache son choix, puis le joueur 2 choisit à son tour.

**Sur deux appareils** (PC, téléphone…) : cliquez sur **Sur deux appareils**. Il faut une connexion internet sur les deux appareils, mais aucun compte.

1. Le joueur A tape son pseudo et clique sur **Je crée la partie** : un code à **4 chiffres** s'affiche.
2. Il le donne au joueur B (message, voix…).
3. Le joueur B tape son pseudo, clique sur **Je rejoins une partie** et tape le code. La connexion démarre toute seule dès que les 4 chiffres sont saisis.
4. Chacun choisit ses 3 cartes sur son appareil, en même temps. Quand les deux ont validé, les équipes sont dévoilées. **Rejouer** relance un tour chez les deux joueurs.

Le code sert à mettre les deux appareils en relation via le service gratuit [PeerJS](https://peerjs.com) (chargé uniquement quand on lance une partie à deux appareils). Les cartes, elles, passent directement d'un appareil à l'autre. Elles sont envoyées en entier (image comprise), car vos collections sont différentes.

*Pas d'internet ?* Le lien **Connexion manuelle** permet de jouer sur le même Wi‑Fi sans service externe : les deux joueurs s'échangent alors deux longs codes (celui de l'hôte, puis la réponse de l'invité).

Rien n'est enregistré : recharger la page met fin au match.

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

- **Exporter ma collection** télécharge un fichier `booster-perso-AAAA-MM-JJ.json` contenant toutes vos cartes créées, vos cartes obtenues (avec leurs exemplaires) et vos boosters.
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

#### Mettre à jour une carte déjà publiée

Chaque carte de la galerie a un **ID** (16 caractères, affiché sous la carte et utilisable dans la recherche). Pour modifier une carte déjà publiée (nom, description, image, attaques…) **sans en créer une deuxième** :

1. Modifiez-la dans **Mes cartes → Créées → Modifier**, puis cliquez sur **Publier**.
2. Dans le champ **ID de la carte à mettre à jour**, collez l'ID de la carte (il est pré-rempli si la carte a été publiée depuis cet appareil). Le bouton devient **Mettre à jour sur GitHub**.
3. Validez la demande : une fois approuvée, la carte est remplacée **en place** sur NSI Hub, boosters compris, et garde le même ID.

Laissé vide, le champ crée une nouvelle carte. L'ID d'une carte ne change jamais, même si son contenu change.

### Publier un booster sur NSI Hub

Un booster publié apparaît dans la section **Boosters de la communauté** de NSI Hub, où chacun peut voir ses cartes et l'**ouvrir** dans Booster perso. Conditions :

- au moins **10 cartes** ;
- au moins **une carte de chaque rareté** (de Commune à Perdue) ;
- **toutes ses cartes déjà publiques** sur NSI Hub.

Dans **Boosters → Publier**, une liste de vérification indique ce qui manque. Les cartes pas encore publiques sont listées avec un bouton **Publier** ; une fois qu'elles ont été validées, cliquez sur **Actualiser**. Quand tout est vert, **Envoyer le booster sur GitHub** ouvre une demande déjà remplie : le code du booster est court, car il ne contient que la liste des cartes. Après validation par Rafael, le booster est ajouté automatiquement.

Sur NSI Hub, le bouton **Ouvrir le booster** ouvre Booster perso et y ajoute le booster avec ses cartes (sans créer de doublons si vous les avez déjà). Il apparaît avec la mention « de NSI Hub » et peut être ouvert tout de suite.

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

### Attaques et fourchettes de puissance

Pour éviter les cartes trop fortes, la puissance de chaque attaque doit rester dans la fourchette de la rareté de la carte :

| Rareté | Puissance par attaque |
|---|---|
| Commune | 10 à 30 |
| Rare | 20 à 50 |
| Épique | 30 à 70 |
| Légendaire | 50 à 100 |
| Super légendaire | 70 à 130 |
| Mythique | 90 à 160 |
| Perdue | 120 à 200 |

La limite est aussi appliquée aux cartes importées par code, par sauvegarde ou reçues pendant un match : une valeur hors fourchette est ramenée dans la fourchette. Les cartes créées avant l'arrivée des attaques n'en ont pas : ouvrez **Mes cartes → Créées → Modifier** pour leur en ajouter. Il n'y a pas encore de combat, les attaques servent pour l'instant à comparer les cartes.

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
| `tcg-boosters-v1` | Les boosters personnalisés (nom, emoji, couleur, cartes). |
| `tcg-bsel-v1` | Le dernier booster choisi dans l'onglet Tirer. |
| `tcg-pseudo-v1` | Le dernier pseudo utilisé pour publier une carte ou un booster. |

Conséquences :

- les cartes sont **propres à chaque navigateur et à chaque appareil** ; utilisez la sauvegarde ou les codes de partage pour les transférer ;
- vider les données du site, ou naviguer en mode privé, **efface la collection** : exportez-la régulièrement ;
- le `localStorage` est limité à environ 5 Mo par site selon les navigateurs. Les images sont compressées en JPEG (240 × 160 px, qualité 70 %) pour en stocker un maximum. Si l'espace manque, un message vous invite à supprimer des cartes.

Seules les cartes et les boosters que vous publiez vous-même quittent votre navigateur : ils sont envoyés sur GitHub, avec votre pseudo, quand vous validez la demande.

---

## Format des codes de partage

Pour les curieux et les contributeurs :

```
TCG1-<données>   données compressées (deflate-raw), puis encodées en base64url
TCG0-<données>   données non compressées, encodées en base64url (navigateurs sans CompressionStream)
```

Une fois décodées, les données forment un tableau JSON :

```json
["Nom", "rarete", "Description", "data:image/jpeg;base64,...", "type", [["Attaque 1", 40], ["Attaque 2", 55]]]
```

Le type est omis pour une carte Neutre **sans attaques**. Les attaques forment un 6e élément facultatif : quand elles sont présentes, le type est toujours écrit (`"neutre"` si besoin). 
À l'import, l'application vérifie chaque champ : rareté connue, nom non vide, longueurs maximales, image limitée aux formats `data:image/jpeg|png|webp`, et type connu (sinon *Neutre*).

Les clés de rareté sont : `commune`, `rare`, `epique`, `legendaire`, `superlegendaire`, `mythique`, `perdue`.

Un **code de booster** suit le même principe avec le préfixe `BST1-` (ou `BST0-`). Une fois décodé :

```json
{"v": 1, "n": "Nom du booster", "e": "🐍", "c": "#3aa24a", "k": ["cc7a22a99e560518", "…"]}
```

`k` liste les cartes par leur **identifiant** : les 16 premiers caractères hexadécimaux du SHA-256 de `JSON.stringify([nom, rarete, description, image, type])` (description et image vides si absentes, type `neutre` par défaut). Le même calcul est fait dans Booster perso, sur NSI Hub (`tcg-share.js`) et par le script de publication.

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

**Changer les fourchettes d'attaque** : objet `ATK_RANGE` (min et max par rareté), ainsi que `ATK_MIN`, `ATK_MAX` et `ATK_STEP` (nombre d'attaques et pas du curseur).

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
- Une carte modifiée après sa publication change d'identifiant : elle ne compte plus comme publique tant que la nouvelle version n'est pas publiée.
- Publier un booster demande d'abord de publier chacune de ses cartes (une demande par carte).
- Le mode **Match** s'arrête au dévoilement des équipes : il n'y a pas encore de règles de combat (les cartes n'ont pas de points de vie, seulement des attaques).
- Une carte déjà publiée sur NSI Hub se met à jour en renseignant son **ID** au moment de publier (voir *Mettre à jour une carte déjà publiée*). Sans ID, une carte modifiée est publiée comme une nouvelle carte ; seule exception : si son contenu est identique à une carte existante et qu'elle a des attaques, ces attaques sont ajoutées à la carte existante.
- Le match sur deux appareils dépend du service PeerJS pour le code à 4 chiffres (internet requis), et la connexion est perdue si l'un des joueurs recharge la page. La connexion manuelle fonctionne sans service externe, mais seulement si les deux appareils peuvent se joindre directement (même Wi‑Fi, sans isolation des appareils).

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

La galerie communautaire et la publication automatique des cartes et des boosters se trouvent dans le dépôt [RafaelMMIX/nsi](https://github.com/RafaelMMIX/nsi) (`cartes.html`, `cartes.js`, `tcg-share.js`, `cartes-publiques.json`, `boosters-publics.json` et `.github/`).

---

## Contribuer

Les idées et les améliorations sont les bienvenues :

1. Forkez le dépôt.
2. Créez une branche : `git checkout -b ma-fonctionnalite`.
3. Testez vos modifications en ouvrant `tcg-cartes.html` dans un navigateur.
4. Ouvrez une *pull request* en décrivant le changement.

Quelques pistes : versions brillantes des cartes, album à compléter, statistiques de tirage, nouveaux types, cartes avec attaque et défense, mode hors ligne (PWA).
