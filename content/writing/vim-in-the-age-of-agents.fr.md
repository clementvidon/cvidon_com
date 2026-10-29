+++
title = "Vim à l’ère des agents"
seo_title = "Vim à l’ère des agents — La personnalisation, enfin à portée de main"
description = "Comment les agents IA réduisent le coût de personnalisation de Vim et rendent les logiciels programmables et composables plus utiles à leurs utilisateurs."
social_description = "Pourquoi la configurabilité de Vim compte davantage à l’ère des agents."

date = 2026-09-19T13:00:00+02:00
category = "Essai"
tags = [
  "Vim",
  "agents IA",
  "éditeurs de texte",
  "personnalisation logicielle",
  "outils de développement",
  "composabilité",
  "philosophie Unix",
  "logiciel compatible avec les agents",
  "MCP"
]

draft = false
+++

*La personnalisation, enfin à portée de main*

En reprenant une configuration Vim qui prenait la poussière, j’ai voulu adapter ses anciens comportements à ma nouvelle façon de travailler. Avec un agent, je pouvais décrire le comportement souhaité, l’essayer, puis demander des ajustements.

Cette expérience m’a fait reconsidérer un vieux compromis de Vim : sa liberté de personnalisation et le temps nécessaire pour en profiter. Il ne sera question ici ni de plugins IA, ni de mappings ou de mémoire musculaire, mais de cette très grande configurabilité dont l’exploitation a longtemps demandé un investissement important.

Vim sert ici d’exemple, mais j’applique cette même approche à l’ensemble de mes outils configurables, dont je réunis les configurations dans un même dépôt pour les faire évoluer tout en conservant une ergonomie cohérente d’un outil à l’autre.


1. Les agents changent les critères de compétition
--------------------------------------------------------------------------------

*Vim n’a pas changé. Son environnement, si.*

### Un compromis historique

Le choix d’un éditeur implique un arbitrage entre bénéfices immédiats et possibilités d’adaptation à long terme.

- **S’en tenir aux fonctionnalités prêtes à l’emploi** : un gain de productivité immédiat, mais un potentiel d’optimisation plus limité à long terme.
- **Investir dans la personnalisation** : une perte de productivité initiale, mais un potentiel de gains plus important à long terme.

### Un nouvel intermédiaire

Avec les agents, l’humain n’est plus seul face au logiciel. Une partie de sa configuration et de son utilisation peut leur être déléguée, réduisant ainsi le coût initial de la personnalisation.

### Un nouveau critère

La compatibilité avec les agents devient alors un nouveau critère d’évaluation du logiciel : non seulement ce qu’il offre directement à l’humain, mais les primitives qu’il met à disposition d’un agent pour le configurer et l’utiliser.


2. La principale contrainte devient la principale force
--------------------------------------------------------------------------------

*Ce qui nous coûtait du temps devient un levier.*

### Le prix de la liberté

Comprendre, configurer et maintenir son environnement demande du temps, directement prélevé sur le travail que cette personnalisation est censée améliorer.[^1]

### De l’intention à la configuration

Les agents changent précisément cette équation. « Voilà comment je veux travailler » peut désormais suffire comme point de départ : l’utilisateur décrit le comportement recherché, l’agent se charge de sa traduction technique.

L’utilisateur n’a plus besoin d’identifier à l’avance toutes les capacités pertinentes du logiciel.

Dans mes notes, par exemple, je voulais un raccourci permettant de naviguer entre les titres de l’index et les sections correspondantes du document, tout en ajustant la vue pour que chaque destination soit correctement positionnée à l’écran. Je décrivais simplement ce comportement ; l’agent combinait recherche, navigation et positionnement de la vue pour l’implémenter.

Le faire moi-même aurait demandé de chercher des solutions existantes, d’identifier les bonnes primitives, d’implémenter et de déboguer.

### La profondeur devient accessible

La configurabilité cesse alors d’être une simple possibilité théorique. Des points d’adaptation explicites, stables et composables donnent à l’agent les leviers nécessaires pour traduire ces intentions en comportements.

L’effort d’implémentation est fortement réduit : l’essentiel de ce travail peut être délégué, tandis que l’utilisateur conserve l’évaluation du résultat.


3. La composabilité devient un avantage décisif
--------------------------------------------------------------------------------

*Quelques briques, une infinité de combinaisons.*

### Des primitives plutôt que des usages prédéfinis

Vim ne se contente pas d’être configurable : il expose des primitives programmables et composables. Commandes, opérateurs, motions, registres et capacités de scripting forment autant de briques pour construire de nouveaux usages.

Le raccourci de navigation décrit plus haut l’illustre : l’agent a combiné des mécanismes existants de recherche, de navigation et de positionnement de la vue pour créer un comportement qu’aucun ne proposait isolément.

Cette composabilité dépasse Vim lui-même. Fidèle à la philosophie Unix, il peut combiner ses propres primitives avec des outils externes pour construire des workflows plus riches.[^2]

### Une liberté balisée

Assez de liberté pour qu’un agent puisse l’adapter profondément, assez de structure pour que cette liberté reste sous contrôle.

Sans principes explicites, l’agent peut optimiser une demande locale au détriment de la cohérence générale de l’environnement.

J’ai donc progressivement fait évoluer les instructions et la documentation qui le guident afin de préciser les principes à respecter : privilégier les mécanismes natifs, préserver le rôle de chaque outil et n’ajouter des comportements personnalisés que lorsqu’un besoin concret le justifie.

Ce travail se poursuit au fil de l’usage : chaque amélioration de mes outils peut aussi être l’occasion d’affiner la manière dont l’agent intervient sur eux.


4. Vim n’est peut-être que le symptôme
--------------------------------------------------------------------------------

*Vim serait l’exemple d’un phénomène plus général.*

### Compatibilité accidentelle

Vim n’a pas été conçu pour les agents et il est loin d’être un modèle idéal pour eux. Pourtant, nombre des propriétés qui le rendent adaptable sont devenues particulièrement précieuses à l’ère des agents.

### Construire pour l’ère des agents

Le protocole MCP (*Model Context Protocol*) standardise aujourd’hui une manière d’exposer les capacités des logiciels aux agents. Mais une interface d’accès ne garantit pas une architecture malléable.

Et si l’enjeu n’était pas seulement de permettre aux agents d’utiliser le logiciel, mais aussi de leur permettre de l’adapter ?

Construire pour l’ère des agents pourrait ainsi consister moins à intégrer de l’IA dans chaque fonctionnalité qu’à concevoir des logiciels suffisamment malléables pour être continuellement adaptés aux usages.

*Cette idée est prolongée dans [Un autre regard sur l’AI-native](https://cvidon.com/fr/writing/another-take-on-ai-native/), consacré aux architectures logicielles conçues pour cette forme d’adaptation.*

---

[^1]: Wendy E. Mackay, *Triggers and Barriers to Customizing Software*, CHI, 1991. [Lire l’article](https://doi.org/10.1145/108844.108867)
[^2]: Rob Pike et Brian W. Kernighan, *Program Design in the UNIX Environment*, AT&T Bell Laboratories Technical Journal, 1984. [Lire l’article](https://lists.gnu.org/archive/html/nmh-workers/2012-11/pdfGsAjwogf3t.pdf)
