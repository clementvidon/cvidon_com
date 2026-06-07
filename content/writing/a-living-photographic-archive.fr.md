+++
title = "Reprendre le contrôle de ses images"
seo_title = "Reprendre le contrôle de ses images — Archive visuelle, cloud et workflow"
description = "Une photothèque n’est pas une archive. Une méthode simple pour garder ses fichiers média lisibles, portables et utilisables sans dépendre entièrement d’un cloud ou d’une application."

date = 2026-05-29T12:00:00+02:00
category = "Guide"
tags = [
  "photographie",
  "archive photo",
  "archive visuelle",
  "archive média",
  "workflow photo",
  "métadonnées",
  "fichiers numériques",
  "gestion des médias",
  "DAM",
  "cloud",
  "Bash"
]

draft = false
+++

Ce n’est pas parce qu’une image est visible dans une application ou sauvegardée dans le cloud qu’on
en garde réellement le contrôle.

Avec le temps, nos images s’accumulent sans véritable système.

On photographie avec un téléphone ou un appareil photo. On reçoit des images par message. On
conserve des captures d’écran. On télécharge, on exporte, on synchronise, on récupère d’anciens
dossiers depuis un ordinateur ou un disque externe. L’ensemble grandit continuellement, devient de
moins en moins lisible, et l’on en perd peu à peu le contrôle.

Le problème n’est pas seulement la quantité. C’est l’hétérogénéité. Ce que nous appelons simplement
nos images est en réalité une masse fragile de fichiers.

Des photos, des vidéos, des RAW, des JPG, des HEIC, des MOV, des exports, des captures d’écran, des
fichiers WhatsApp, Signal ou Telegram, des fichiers compressés, des versions alternatives, des
fichiers édités, des fichiers dupliqués, des fichiers dont le nom ne veut plus rien dire, des
fichiers dont les métadonnées sont incomplètes ou incohérentes, des fichiers corrompus ou
partiellement illisibles.

Les photothèques donnent une impression d’ordre. Elles permettent de parcourir, rechercher, classer,
sélectionner ou partager ses images. La synchronisation cloud donne une impression de sécurité et de
pérennité. Elle protège parfois contre la perte immédiate d’un appareil ou d’un disque.

Mais une masse synchronisée n’est pas forcément une archive maîtrisée. Le problème de fond est
simple : savoir ce que l’on possède, pouvoir le retrouver, l’utiliser, le copier, le déplacer, le
migrer, et garder cet ensemble exploitable aussi facilement aujourd’hui que dans cinq, dix ou vingt
ans.

La méthode que je propose ici repose sur une idée simple : avant de décider où ranger ses fichiers,
il faut d’abord les rendre lisibles, vérifiables et triables. Cela commence par des métadonnées
aussi cohérentes que possible, en particulier la date de création, par la vérification que les
fichiers ne sont pas cassés, et par un nommage stable.

Le but est de produire une base qui reste utile dans le temps, indépendamment de la machine ou de
l’application utilisée.

Dans mon cas, je distingue deux grands ensembles.

`Camera` correspond à mon flux photographique contrôlé : fichiers issus de mes appareils photo,
imports plus homogènes, séries, projets, shootings ou voyages.

`Personal` correspond à mon archive visuelle personnelle au sens large : téléphone, cloud,
messageries, captures d’écran, téléchargements, images reçues, références, fragments et souvenirs.

Sources hétérogènes :

```text
Nikon Zf/DCIM/100ND750/DSC_8421.NEF
Ricoh GR III/
├── DCIM/100RICOH/R0004387.DNG
└── DCIM/100RICOH/R0004386.DNG
iPhone 15/
├── DCIM/104APPLE/IMG_4821.HEIC
├── DCIM/104APPLE/IMG_4822.MOV
└── Downloads/export_001.jpg
Samsung Galaxy S23/
├── DCIM/Camera/20260526_194218.jpg
├── WhatsApp/Media/WhatsApp Images/IMG-20050518-WA0004.jpg
├── Telegram/Telegram Images/photo_2024-05-26_19-42-19.jpg
├── Pictures/Screenshots/Screenshot_20260521-114207.png
└── Download/
    ├── sticker_20260517_083102.webp
    └── 7f6c91e2a4f4d1d9.gif
```

Base stabilisée :

```text
Archive/
├── Camera/
│   ├── CV26_0412_212430_30071244.DNG
│   ├── CV26_0412_212501_30072132.DNG
│   └── CV26_0514_165930_29257528.NEF
└── Personal/
    ├── CV05_0518_214409_01288211.JPG
    ├── CV24_0526_194219_00322817.JPG
    ├── CV25_0113_192213_00591822.HEIC
    ├── CV26_0517_083102_00422819.WEBP
    ├── CV26_0520_163201_00482731.JPG
    ├── CV26_0521_114207_00118291.PNG
    └── CV26_0526_194220_00112763.GIF
```

Organisation flexible :

```text
Archive/
├── Camera/
│   └── 2026/
│       ├── 0412-elvis-party/
│       └── 0514-palermo-weekend/
└── Personal/
    └── 2026
        ├── Gallery/
        ├── Memories/
        ├── Clippings/
        ├── Inspo/
        └── Other/
```

## Une photothèque n’est pas une archive

Une photothèque peut rendre une collection consultable sans rendre les fichiers eux-mêmes plus
lisibles, cohérents ou durables.

Elle est très utile pour consulter ses images. Elle permet de parcourir, rechercher, classer,
sélectionner, partager, parfois éditer. Elle peut reconnaître des visages, regrouper des lieux,
faire remonter des souvenirs ou rendre une grande collection plus facile à explorer.

Mais elle reste une couche d’abstraction. Elle donne accès aux images à travers une interface, selon
sa propre logique. Tant que l’on reste dans cette interface, le système paraît ordonné. Dès que l’on
veut exporter, migrer, comparer, dédupliquer, sauvegarder soi-même ou travailler sur plusieurs
supports, les fichiers réapparaissent : noms incohérents, dates ambiguës, versions multiples,
formats différents, métadonnées absentes ou contradictoires.

Le problème n’est donc pas d’utiliser une photothèque, mais d’en faire le seul endroit où
l’organisation existe. Elle peut rester l’endroit où l’on consulte, sélectionne ou partage ses
images ; les fichiers, eux, doivent rester compréhensibles en dehors d’elle.

## Ce que j’entends par archive

Je ne parle pas d’un stockage froid où les fichiers prennent la poussière. Je parle plutôt d’une
structure de travail : un système qui garde les images passées et présentes accessibles,
compréhensibles, faciles à retrouver et à utiliser.

Une archive vivante n’a pas vocation à grossir indéfiniment. Elle doit aussi pouvoir se réduire.

Avec le temps, certains fichiers perdent leur intérêt, des doublons deviennent visibles, des
catégories se précisent, certains fichiers peuvent être retirés. Le but n’est donc pas seulement
d’accumuler, mais de rendre ces opérations de tri, de sélection et de réduction aussi simples et
sûres que possible.

Une bonne archive doit rester simple à maintenir. Si elle devient trop complexe, elle cesse d’être
utilisée. Elle doit être lisible sans dépendre d’une application dédiée, vérifiable, portable, et
assez souple pour accueillir de nouvelles sources.

Dans l’esprit, cela rejoint certaines idées classiques de gestion des données : rendre les fichiers
retrouvables, accessibles, interopérables et réutilisables.

Je voulais ramener ces principes à l’échelle d’une archive personnelle, sous la forme d’un système
simple :

* un système que je peux comprendre en ouvrant un dossier.
* un système qui tient dans ma tête plutôt que dans une application.
* un système qui continue à avoir du sens même si je change de logiciel, de machine ou de service cloud.

## Réunir sans tout mélanger

Réunir ses fichiers ne veut pas dire tout verser dans un même dossier.

Dès le départ, je préfère garder quelques grands ensembles lisibles. Dans mon cas, `Camera` reçoit
tous les fichiers issus de mes appareils photo : imports plus homogènes, séries, projets, shootings
ou voyages.

`Personal` rassemble mon archive visuelle personnelle au sens large. Elle peut contenir des fichiers
venus de téléphones, de messageries, d’exports cloud, de captures d’écran, de téléchargements,
d’anciens ordinateurs ou de disques externes.

Chez moi, `Personal` contient plusieurs catégories qui correspondent à ma manière de conserver les
fichiers : `Gallery` pour mes images et vidéos du quotidien que je choisis pour leur qualité ou leur
intérêt visuel ; `Memories` pour les souvenirs personnels, même imparfaits ou sans valeur esthétique
particulière ; `Clippings` pour les fragments visuels qui documentent mon époque et mon regard ;
`Inspo` pour les références et inspirations ; et enfin `Other` pour ce qui ne rentre nulle part.

Ces catégories ne sont ni universelles ni figées. Quelqu’un d’autre pourrait avoir `DIY`, `Outfits`,
`Cooking` ou autre chose. L’important est de ne pas perdre les contextes qui rendent les fichiers
compréhensibles.

Cette logique vaut autant pour une première mise en ordre que pour une routine régulière. Dans les
deux cas, il s’agit de réunir les fichiers sans perdre les contextes qui les rendent
compréhensibles.

## La date comme point d’ancrage

Pour qu’une archive reste lisible, les fichiers doivent pouvoir être rangés dans un ordre qui a du
sens. Le plus simple est souvent l’ordre chronologique : une date permet de retrouver une période,
une session, un événement, ou simplement de regrouper des fichiers proches.

Mais cette information n’est pas toujours évidente. Un même fichier peut contenir plusieurs champs
permettant de le situer dans le temps, comme `DateTimeOriginal`, `CreateDate` ou `MediaCreateDate`,
parfois absents, modifiés ou contradictoires.

La méthode cherche donc à établir la meilleure date possible à partir des informations
disponibles. Cette étape devient rapidement irréaliste à la main lorsqu’on traite beaucoup de
fichiers. Elle repose sur quelques automatisations simples : lire plusieurs champs, choisir la
meilleure information disponible, normaliser certaines métadonnées et vérifier que les fichiers ne
sont pas abîmés.

L’objectif n’est pas de produire une vérité parfaite dans tous les cas, mais de créer une base
stable et cohérente pour organiser l’archive.

Une fois cette date établie, elle peut devenir le point d’ancrage du nom de fichier.

## Le nom comme infrastructure minimale

J’utilise un format de nommage simple :

```text
PREFIXYY_MMDD_HHMMSS_FILESIZE.EXT
```

Par exemple :

```text
CV26_0320_025038_31188070.DNG
```

J’utilise ici mes initiales, `CV`, comme préfixe pour indiquer que ce sont mes fichiers.

La date et l’heure inscrites dans le nom permettent d’abord un tri chronologique simple. Les
fichiers proches dans le temps se retrouvent naturellement côte à côte. Une série, un voyage, une
soirée ou une session de travail redeviennent lisibles sans dépendre d’aucune application. Comme la
date de création est l’une des informations les plus importantes d’une archive média, l’inscrire
dans le nom du fichier, et pas seulement dans les métadonnées, réduit aussi le risque de la perdre
au fil des exports, des copies ou des migrations futures.

La taille du fichier permet de réduire les collisions lorsque plusieurs fichiers partagent le même
horodatage. Elle aide aussi à repérer certains doublons, exports, compressions, versions modifiées
ou copies de moindre qualité.

Il ne s’agit pas ici d’un nommage élégant, mais d’un nommage opérationnel. Le nom du fichier devient
une petite infrastructure : avant même de choisir une arborescence définitive, chaque fichier porte
déjà son préfixe, sa date, son heure, son poids et son format. Il devient alors plus facile à trier,
à comparer, à déplacer, à sauvegarder et à réorganiser plus tard. Même un simple explorateur de
fichiers redevient utile.

## Dernier contrôle

Avant d’archiver ou de sauvegarder, je vérifie que les fichiers sont lisibles.

Ce contrôle permet de repérer les fichiers abîmés assez tôt pour les isoler et tenter de les
réparer.

## Rester simple

Je voulais que ce système reste volontairement ennuyeux.

Des dossiers ordinaires. Des noms de fichiers lisibles. De petits scripts. Des outils
standards. Rien qui ne soit indispensable à une application précise ou à une base de données cachée.

Ce n’est pas une question de pureté technique. C’est une question de maintenance. Plus un système
est simple, plus il a de chances d’être réellement utilisé. Plus il est lisible, plus il est facile
à reprendre après plusieurs mois. Plus il repose sur des conventions explicites, moins il dépend de
ma mémoire.

Dans mon cas, l’archive reste vivante parce qu’elle continue d’évoluer. J’y ajoute régulièrement de
nouveaux fichiers et je profite de ces moments pour revoir l’existant, trier ce qui n’a plus
d’intérêt et affiner progressivement son organisation.

## Pour qui c’est utile

Ce système s’adresse aux personnes qui veulent reprendre le contrôle sur leur archive média avec des
conventions simples, lisibles et durables, sans dépendre entièrement d’un cloud ou d’une
application.

Cela peut être quelqu’un qui accumule des années de photos, qui sent que son cloud est devenu trop
dense pour être encore maîtrisable, ou qui retrouve ses fichiers éparpillés entre plusieurs
appareils, disques et services.

Le but n’est pas de conserver des fichiers comme des objets morts, mais de garder une archive
visuelle vivante : lisible par des machines, compréhensible par des humains, et assez utile pour
continuer à travailler avec elle dans plusieurs années.

## Application concrète

J’ai transformé cette méthode en guide pratique, accompagné de quelques scripts Bash :

[photography-archiving-workflow](https://github.com/clementvidon/photography-archiving-workflow)

Le guide explique le workflow étape par étape. Les scripts prennent en charge les parties qui ne
sont pas réalistes à faire manuellement à grande échelle : lire et normaliser les métadonnées,
renommer les fichiers, et vérifier que les fichiers médias restent lisibles.

Les scripts fournis sont simplement les outils que j’utilise pour appliquer cette méthode.

D’autres outils peuvent remplir le même rôle, tant que les principes restent les mêmes : établir une
date fiable, nommer les fichiers clairement, vérifier leur lisibilité, puis les organiser dans des
dossiers ordinaires.

## Discussion

- Article: [Substack](https://cl3don.substack.com/p/a-living-photographic-archive)
- Workflow: [GitHub Discussions](https://github.com/clementvidon/photography-archiving-workflow/discussions)
