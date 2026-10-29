+++
title = "Un autre regard sur l’AI-native"
seo_title = "Un autre regard sur l’AI-native — Des logiciels façonnables"
description = "Et si l’AI-native désignait aussi des logiciels que leurs utilisateurs peuvent adapter avec des agents ? Un essai sur la malléabilité et les adaptations durables."
social_description = "Des logiciels qui permettraient à leurs utilisateurs de les reconfigurer avec des agents."

date = 2026-09-19T14:00:00+02:00
category = "Essai"
tags = [
  "AI-native",
  "agents IA",
  "logiciel malléable",
  "architecture logicielle",
  "personnalisation logicielle",
  "composabilité",
  "automatisation",
  "MCP",
  "autonomie des utilisateurs"
]

draft = false
+++

*Des logiciels façonnables*

Le terme « AI-native » désigne généralement des produits conçus autour de l’IA plutôt que simplement enrichis de fonctionnalités d’IA, mais ses contours restent encore mouvants.

« AI-native » pourrait aussi désigner des logiciels conçus pour que leurs utilisateurs les adaptent à leurs besoins avec l’aide d’agents.

Les agents pourraient ainsi rendre la malléabilité, vieille ambition du logiciel[^1], plus facile à mettre en pratique. Chaque adaptation pourrait servir de point de départ à la suivante, à condition que l’architecture du logiciel le permette.


1\. L’IA dans, devant ou sur le logiciel
--------------------------------------------------------------------------------

*L’IA peut faire partie du logiciel, l’utiliser, ou le transformer.*

### Dans le logiciel

C’est aujourd’hui la forme la plus visible : chatbots intégrés, systèmes de recommandation, génération de contenu ou recherche assistée deviennent des fonctionnalités du produit.

L’IA se cantonne à une capacité prévue par ses concepteurs.

### Devant le logiciel

Avec les agents, l’IA devient utilisatrice du logiciel : CLI, API ou MCP lui permettent d’en exploiter directement les fonctions pour produire un résultat.

L’IA n’est plus une fonctionnalité interne : elle agit désormais comme opératrice du logiciel.

### Sur le logiciel

Ces mêmes interfaces peuvent aller plus loin lorsqu’elles permettent à l’agent d’agir sur l’outil lui-même : configuration, automatisations, workflows, extensions ou nouvelles combinaisons de primitives rendues persistantes.[^2]

L’objectif n’est alors plus seulement de produire avec le logiciel, mais de faire évoluer la manière dont il sera ensuite utilisé.

Ces trois formes peuvent coexister. C’est la troisième qui nous intéresse ici.


2\. De la productivité consommée à la productivité capitalisée
--------------------------------------------------------------------------------

*Un résultat se consomme. Un outil s’améliore.*

**Un gain ponctuel**

Lorsqu’un agent génère une image, écrit un document ou réalise une opération dans une application, le gain est principalement attaché à cette tâche.

`intention → agent → résultat`

L’outil, lui, reste inchangé pour la tâche suivante.

**Un gain persistant**

Lorsque l’agent adapte l’outil lui-même, une partie de son travail reste disponible pour les usages futurs.

`intention → agent → adaptation de l’outil → usages futurs`

Une automatisation, une configuration ou une extension bénéficie alors aux tâches suivantes.

**Du contexte qui s’accumule**

Chaque adaptation intègre une part du contexte propre à l’utilisateur : ses habitudes, ses préférences, ses contraintes ou ses workflows.

Le contexte partagé avec l’agent se matérialise progressivement dans l’outil lui-même.

L’environnement s’adapte ainsi progressivement à son utilisateur, tout en devenant plus efficace pour les agents qui y interviennent.


3\. Cette boucle repose sur l'architecture
--------------------------------------------------------------------------------

*L’interface ne suffit pas.*

### Des primitives plutôt que des usages prédéfinis

Pour rester adaptable, un logiciel doit exposer suffisamment de matière à l’agent :

```text
Pouvoir transformer
- primitives stables
- composition
- configuration
- extension

Pouvoir comprendre
- capacités documentées ou découvrables
- état et comportement observables

Pouvoir connecter
- données accessibles
- interopérabilité

Pouvoir capitaliser
- persistance des adaptations
```

L’objectif n’est plus d’anticiper chaque usage, mais de fournir assez de briques pour que de nouveaux usages puissent être construits.

### Un espace de liberté balisé

La malléabilité repose aussi sur une frontière claire entre ce qui peut être adapté et ce qui reste stable.

```text
- surface configurable / extensible
- invariants / frontières stables
- permissions
- isolation
- validation
- undo
- versioning
```

Dans un logiciel comme [Vim](https://cvidon.com/fr/writing/vim-in-the-age-of-agents/), une grande partie du comportement peut être personnalisée sans avoir à modifier le cœur de l’éditeur lui-même. Cette séparation permet d’offrir beaucoup de liberté tout en conservant une base prévisible.

La malléabilité ne suppose pas l’absence de limites, mais des limites bien placées.

### Et MCP dans tout ça ?

MCP (*Model Context Protocol*) standardise une manière d’exposer les capacités d’un logiciel aux agents.[^3] Pour situer son rôle, distinguons trois couches :

```text
Architecture
→ ce que le logiciel permet de transformer

Interface
→ la manière dont l’agent accède à ces possibilités
  fichiers, shell, CLI, API, MCP, scripting…

Agent
→ sa capacité à comprendre et combiner ces possibilités
```

MCP intervient au niveau de l’interface. La puissance de MCP dépend donc moins du protocole lui-même que de ce que l’architecture du logiciel permet d’exposer.


4\. Co-construire son environnement
--------------------------------------------------------------------------------

*De l’intention à la transformation.*

### Du logiciel livré au logiciel façonné

Dans sa forme la plus simple, le modèle classique peut se résumer ainsi :

`conception → logiciel → utilisation`

Le modèle proposé ici conduit plutôt à :

`conception → espace de possibilités → humain + agent → adaptation continue`

Les développeurs définissent les primitives, les règles et les garde-fous.  L’utilisateur apporte ses besoins et son contexte. L’agent les traduit en modifications concrètes et prend en charge leur implémentation.

### L’humain reste dans la boucle

Il ne s’agit donc pas d’un logiciel qui se réécrit continuellement de façon autonome.

L’humain garde l’intention et le jugement ; l’agent se charge de la mise en œuvre.

Le besoin pourrait aussi émerger de l’observation des usages : un agent repérant une suite d’actions répétées pourrait proposer de l’automatiser. L’adaptation partirait alors d’un besoin implicite, tout en restant guidée ou validée par l’utilisateur.

### Un autre critère pour l’AI-native

Et si l’AI-native se définissait aussi par la capacité d’un logiciel à être façonné par ses utilisateurs avec l’aide d’agents ?

La question porterait alors autant sur la place de l’IA dans le logiciel que sur ce que son architecture permet aux utilisateurs de transformer avec elle.

---

[^1]: Geoffrey Litt et al., *Malleable Software*, Ink & Switch, 2025. [Lire l’article](https://www.inkandswitch.com/essay/malleable-software/)
[^2]: Andy Matuschak, *A startling glimpse of malleable software: LLM-generated Obsidian plugins*, 2025. [Lire l’article](https://andymatuschak.org/files/2025-03-31.html)
[^3]: Model Context Protocol, *Understanding MCP servers*. [Lire la documentation](https://modelcontextprotocol.io/docs/learn/server-concepts)
