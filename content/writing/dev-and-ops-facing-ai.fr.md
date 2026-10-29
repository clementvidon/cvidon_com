+++
title = "Dev et Ops face aux agents"
seo_title = "Dev et Ops face aux agents — une transformation asymétrique"
description = "Les agents IA transforment différemment le Dev et l’Ops : ils prennent en charge la production de code pour les développeurs tout en étendant des pratiques établies d’automatisation et d’orchestration des Ops."
social_description = "Avec les agents, le Dev évolue vers l’orchestration ; l’Ops prolonge sa logique d’automatisation."

date = 2026-09-19T12:00:00+02:00
category = "Essai"
tags = [
  "agents IA",
  "développement logiciel",
  "développeurs",
  "Ops",
  "DevOps",
  "automatisation",
  "orchestration",
  "infrastructure",
  "SRE"
]

draft = false
+++

*Une transformation asymétrique*

Les agents IA prennent déjà en charge une part du travail quotidien des développeurs et des Ops.

Mais cette automatisation ne transforme pas les deux métiers de la même manière.

Côté Dev, elle touche directement une activité centrale : l'écriture du code.

Côté Ops, elle ajoute surtout une nouvelle couche d’abstraction à une logique déjà fondée sur l’automatisation et l’orchestration.


Le Dev passe de la production à l’orchestration
--------------------------------------------------------------------------------

### Produire le logiciel →

Le développement s’est historiquement organisé autour de l’écriture du code : le développeur traduisait directement les besoins en logiciel.

Malgré l’évolution des outils et des niveaux d’abstraction, il restait généralement l’auteur du code source, ses outils facilitant cette production sans prendre en charge l’essentiel des choix d’implémentation.

### → Orchestrer sa production

Avec les agents, cette relation change.

Le développeur peut décrire une intention, fournir du contexte, définir des contraintes, déléguer l’implémentation puis valider le résultat.

L’écriture du code peut désormais être partiellement, voire entièrement déléguée. Le développeur peut alors se concentrer davantage sur ce qui précède et encadre cette production : comprendre le besoin métier, définir l’architecture, décomposer le problème et contrôler le résultat.

Il conserve la responsabilité du logiciel sans nécessairement en écrire lui-même le code : il orchestre de plus en plus le système qui le produit.[^1]


L’Ops étend sa logique d’orchestration
--------------------------------------------------------------------------------

### Orchestrer via des automatisations →

Pour l’Ops, ce rapport indirect au résultat est beaucoup moins nouveau.

La distinction n’est toutefois pas absolue : les Ops écrivent aussi du code et les développeurs pratiquent déjà l’orchestration. C’est surtout la place de ces activités dans chaque métier qui diffère.

Administrer une infrastructure consiste déjà largement à piloter des systèmes par l’intermédiaire d’autres systèmes.

On ne configure plus nécessairement chaque élément à la main : on décrit un état attendu, puis des mécanismes automatisés se chargent de l’appliquer et de le maintenir.

L’Ops s’éloigne ainsi depuis longtemps de l’exécution directe, sans que la logique fondamentale de son métier change.

### → Orchestrer via des agents

Les agents ajoutent un niveau supplémentaire à cette chaîne.

L’Ops peut désormais décrire un résultat attendu et laisser un agent déterminer les actions nécessaires pour l’atteindre. Lors d’un incident, il peut également lui déléguer une partie du diagnostic et de la remédiation.

Leur autonomie et leur comportement moins déterministe exigent des garde-fous adaptés.[^2] Cette incertitude diffère de celle des infrastructures classiques, mais elle mobilise des pratiques familières à l’Ops : définir des limites, observer et garder le contrôle.

Cette continuité n’exclut pas une transformation importante du travail quotidien.


Conclusion — Deux trajectoires qui convergent
--------------------------------------------------------------------------------

Le Dev voit une activité centrale de son métier se transformer, tandis que l’Ops poursuit un mouvement d’abstraction déjà engagé.

L’expérience de l’Ops suggère qu’un métier peut déléguer une grande partie de son exécution sans disparaître : l’orchestration et le contrôle deviennent alors d’autant plus importants.

À mesure que les agents prennent en charge l’exécution, le développement se rapproche ainsi d’une logique depuis longtemps familière à l’Ops : **ne plus seulement produire, mais orchestrer ce qui produit.**

[^1]: Birgitta Böckeler, [*Harness engineering for coding agent users*](https://martinfowler.com/articles/harness-engineering.html), Martin Fowler, 2026.
[^2]: Ioannis Papapanagiotou et al., [*AI in SRE: How Google is Engineering the Future of Reliable Operations*](https://sre.google/resources/practices-and-processes/ai-engineering-reliable-operations/), Google SRE.
