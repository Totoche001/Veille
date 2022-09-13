Je vais vous parler des différentes solution de détection et de réponse contre les menaces

Qu'est ce que c'est: ce sont différentes outils qui permettant d'analyser un appareil

Que ce soit pour chaque terminaux ou dans le réseau, prévenir d'une action dangereuse
permet de vérifié les logs, analyser le comportement si l'appareil est attaqué
Offrir une vue d'ensemble sur l'infrastructure de l'entreprise; etc...

Les principales solutions sont 
l'Endpoint Protection Plateform
l'Endpoint Detection and Response
Network Detection and Response
Security Information and Event Management
Security Orchestration, Automation and Response

L'endpoint Protection Plateform
La plate-forme de protection des terminaux fonctionne de manière très similaire à un antivirus. 
se base sur une méthode d'analyse par signature et analyse heuristique
mais on lui a rajouter

    Analyse comportementale : Grâce à un moteur d'apprentissage automatique, l'EPP sera capable d'identifier les actions et les fichiers qui peuvent être considérés comme malveillants.
    Surveillance de la mémoire : Le logiciel de protection va analyser en temps réel pendant l'utilisation d'un programme si ce dernier ne corrompt pas la mémoire du système ou d'un autre programme.
    Vérification des IOC ou indicateur de compromission : l'EPP va identifier sur la machine tout fichier ou clé de registre qui pourrait être lié à une attaque grâce à la threat intelligence (recherche humaine des derniers types d'attaques connues).

EPP est-il suffisant ?

EPP est un logiciel de protection des terminaux de nouvelle génération. Cependant, bien qu'il dispose de nombreuses fonctionnalités, il n'est pas infaillible. En effet, il peut détecter beaucoup plus de malwares qu'un antivirus mais ne les bloque pas et ne détecte pas certains types d'attaques ou de tentatives de corruption du système ou des données. Il reste néanmoins un produit plus pertinent qu'un antivirus pour la protection des ordinateurs et des serveurs.

L'EDR 
L'objectif principal de l'edr est la détection de manière proactive des menaces nouvelles ou inconnues mais aussi la détection d’infections non identifiées antérieurement et qui s’infiltrent dans l’organisation en passant directement par les terminaux et les serveurs.
EDR a de bien meilleures chances de détecter les souches d’un malware inconnu en zero-day, et les attaques au niveau de l’APT, parce qu’il utilise des technologies de détection avancées comme les règles YARA, le sandboxing, un scan des IoCs (indicateurs de compromission), la découverte et validation d’activités suspectes, une analyse rétrospective avec une corrélation des événements selon un apprentissage automatique dynamique, l’analyse et le confinement des incidents, l’automatisation de la réponse, des fonctionnalités de remédiation,
Pour avoir une protection fiable et efficace contre les menaces avancées, l’EPP et l’EDR travaillent ensemble. L’EPP gèrent les menaces connues, et l’EDR s’occupe des menaces inconnues plus complexes. Les plateformes EDR puissantes peuvent aider les analystes à étudier et améliorer leurs défenses, plutôt que de simplement réagir aux dégâts déjà causés par une menace avancée que les solutions traditionnelles de protection des points de terminaison pourraient ne pas détecter.

XDR
C'est une plateforme qui va centraliser tous les données venant des terminaux, intègre les données les données de sécurité provenant des outils de gestion des siem, d'edr, des analyses de réseaux et de gestion des identité et des accès (IAM), elle offre une vue d'ensemble sur l'environnement de l'entreprise dans une interface unifié

L'objectif ultime de la plateforme XDR est d'améliorer la productivité des équipes de sécurité, de permettre des enquêtes plus rapides et plus complètes, et de réduire les délais de réponse aux incidents.


Centralise et externalise toute la détection des menaces

Un XDR est une plateforme intégrée de sécurité et de réponse aux incidents qui peut collecter et corréler automatiquement les données provenant des points d'extrémité et de nombreuses autres parties de l'environnement informatique. Il s'agit d'une plateforme permettant d'intégrer les données de sécurité provenant des outils de gestion des SIEM, d'EDR, d'analyse des réseaux et de gestion des identités et des accès (IAM). Elle offre une vue d'ensemble de la cybersécurité de l'ensemble de l'environnement de l'entreprise dans une interface unifiée.

Un XDR peut fournir une normalisation des opérations de sécurité, permettant une analyse cohérente et fiable dans n'importe quel environnement. Elle enrichit les sources de données existantes et consolide les informations pour une analyse plus efficace.


(C’est l’outil le plus complet actuellement sur le marché. Il centralise toute la détection, la réponse à incident, et intègre du marchine learning. L’XDR peut intégrer toutes les sources de log (réseau, endpoints, cloud, emails…). Une équipe externe peut s’occuper d’investiguer et de répondre aux alertes, on parle alors de MDR (Managed Detection and Response). L’outil offre aussi un service de CTI (Cyber Threat Intelligence). Le budget sera souvent le point bloquant, toutefois l’offre est de plus en plus flexible : une entreprise disposant déjà de certaines solutions ou n’ayant pas les fonds pour l’offre complète peut louer une partie des services de l’XDR. Pour les entreprises ne disposant pas d’équipe d’investigation (CSIRT, SOC…) en interne c’est une solution très intéressante. Il est important de garder à l’esprit que l’XDR offre une simplicité de mise en place et une réduction des coûts, mais cela est au détriment de la qualité. La prise en main de l’outils et sa configuration par les équipes internes sera plus complexe.)

SOAR
Le SOAR n’est pas un outil de détection : c’est un outil d’orchestration d’automatisation de la réponse à incident. Sur la base d’alertes, il déclenche une série d’actions à réaliser adaptées à chaque situation. Ces actions peuvent être d’investigation dans le but de compléter les informations de l’alerte, de la contextualiser, mais elles peuvent aussi être de répondre à l’incident. La flexibilité de l’outil fait de lui un réel support pour les analystes.


« Un outil AV d’entreprise identifie les malwares sur un système et envoie une alerte au système SOAR », explique M. Gamblin. « Le workflow du système SOAR peut être écrit pour faire ce qui suit :

    Faire en sorte que le système AV lance une analyse de correction.
    Récupérer les résultats de la remédiation.
    Si le malware a été supprimé : Envoyez un message Slack à l’équipe qui gère le système audiovisuel, pour l’informer.
    Si le malware n’a pas été supprimé : Déplacez le système vers un VLAN isolé ou désactivez l’accès à Internet.
    Envoyez un message Slack à l’équipe qui gère le système audiovisuel, pour l’en informer.
    Envoyer une alerte à l’utilisateur du système, lui demandant de ne pas utiliser le système avant d’en avoir reçu l’instruction.
    Ouvrir un ticket d’assistance avec toutes les informations nécessaires pour que les bonnes équipes puissent poursuivre leur enquête.

si vos professionnels de la sécurité travaillent avec des informations obsolètes ou incomplètes, des outils de patchwork ou une culture d’entreprise qui traite la sécurité comme un obstacle plutôt que comme une priorité – eh bien, SOAR ne résoudra pas ces problèmes de manière modulaire.

« Si la sécurité est éloignée des applications, verrouillée à la fin, et peut produire des perturbations involontaires, SOAR ne résoudra rien de tout cela », déclare M. Korren d’Aqua Security. « Il ne fait qu’empirer les choses.

