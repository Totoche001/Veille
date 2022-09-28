Suite a la veille de benjamin sur les siem, une solution de détection au niveau des logs, alors j'ai voulu voir ce qu'il y avait d'autre comme outils de detection et de réponse contre les menaces

C'est Différent outils qui permet détecter les différentes menaces présentent dans les endpoint (Un endpoint désigne tout type de terminal qui se connecte au réseau de l’entreprise) soit en prévenant, soit en analysant le comportement d'un terminal, soit en analysant les logs, analyser le réseau, etc....

ca été développé  pour soulager les centre de sécurité face aux alertes à répétition, a détecter plus rapidement ces alertes et les résoudres

Les principales solutions sont
l'Endpoint Protection Plateform
l'Endpoint Detection and Response
Network Detection and Response
Security Information and Event Management
Extended detection and response
Security Orchestration, Automation and Response

### L'endpoint Protection Plateform

c'est une plate-forme de protection des terminaux qui fonctionne de manière très similaire à un antivirus.
ça se base sur une méthode d'analyse par signature comme les antivirus
mais on lui a rajouter

de l'analyse comportementale (identifier les actions et les fichiers qui peuvent être considérés comme malveillants), l'analyse heuristique, de la surveillance de mémoire (verifier pendant l'utilisation du programme si ça corrompt pas la mémoire), vérification d’IOCs

Mais il ne détecte pas tous, il ne bloque pas et ne détecte pas certains types d'attaques ou tentatives de corruption du système ou des données.

### L'EDR

est une technologie de sécurité des terminaux qui combine surveillance continue et en temps réel, collecte de données et d'informations sur les terminaux, fonctionnalités de détection et actions automatisées.

donc l'edr permet de mieux détecter les menaces connues comme inconnue (zeroday) et les attaques au niveau de l'apt (advanced persistent thread ou menaces persistantes avancées comme des enregistreurs de frappes) parce qu'il utilisent des technologies de détection avancées comme les règles Yara (créer des règles a partir de l'analyse d'un malware), le sandboxing, un scan des IoCs  (indicateurs de compromission), la découverte et validation d’activités suspectes, analyse avec apprentissage automatique dynamique, le confinement des incidents, l'automatisation des réponses

un exemple de ce qu'on appelle le processus de gestion des incidents 

Identification. si l'edr a trouver une menace courante ou sérieuse et si elle nécessite une réponse, sur la base du contexte et des détails du problème.

Confinement si elle doit isoler l’hôte, prévenir l’exécution ou mettre les fichiers suspects en quarantaine ?

Élimination. Utilisation de l’analyse d’un IoC pour trouver et supprimer les fichiers liés, ainsi que tout autre processus requis pour éradiquer la menace.

Rétablissement. Retour du réseau à la normale : par exemple, l’isolation d’un hôte infecté pour prévenir la propagation de l’infection permet de rétablir le réseau.

Analyse des leçons apprises. Comme l’intégration des données sur les IoC aux outils de sécurité existants, l’analyse des contrôles d’accès et du Web, le blocage de l’accès à des adresses IP ou emails spécifiques ou la sensibilisation à la sécurité pour aider les entreprises à mieux comprendre et repérer les menaces de sécurité modernes.

~~(Généralement pour avoir une protection fiable et efficaces contre les menaces avancées, on ajoute l'edr a l'epp, L’EPP gèrent les menaces connues, et l’EDR s’occupe des menaces inconnues plus complexes. Les plateformes EDR puissantes peuvent aider les analystes à étudier et améliorer leurs défenses, plutôt que de simplement réagir aux dégâts déjà causés par une menace avancée que les solutions traditionnelles de protection des points de terminaison pourraient ne pas détecter.)~~

### XDR

C'est une plateforme qui va centraliser tous les données venant des terminaux, intègre les données de sécurité provenant des outils de gestion des siem, d'edr, de gestion des identité et des accès (IAM) et des données télémétriques provenant d'autre sources (visibilité sur le réseau, sécurité des e-mails, sécurité du cloud, etc.) elle offre une vue d'ensemble sur l'environnement de l'entreprise dans une interface unifié

L'objectif ultime de la plateforme XDR est d'améliorer la productivité des équipes de sécurité, de permettre des enquêtes plus rapides et plus complètes, et de réduire les délais de réponse aux incidents.

~~Le XDR optimise la détection des menaces, les recherches et la chasse aux menaces en temps réel. C’est une solution MDR unifiée, comme son nom l’indique (XDR = extended MDR, détection et réponse infogérées étendues). Un SOC complet capable de compiler et de corréler des données provenant de multiples sources.
mdr: Managed Detection & Response (service managé de détection et de réponse)
le système de détection et de réponse est géré par un prestataire dans les cas du MDR.Un XDR peut fournir une normalisation des opérations de sécurité, permettant une analyse cohérente et fiable dans n'importe quel environnement. Elle enrichit les sources de données existantes et consolide les informations pour une analyse plus efficace.)(C’est l’outil le plus complet actuellement sur le marché. Il centralise toute la détection, la réponse à incident, et intègre du marchine learning. L’XDR peut intégrer toutes les sources de log (réseau, endpoints, cloud, emails…). Une équipe externe peut s’occuper d’investiguer et de répondre aux alertes, on parle alors de MDR (Managed Detection and Response). L’outil offre aussi un service de CTI (Cyber Threat Intelligence). Le budget sera souvent le point bloquant, toutefois l’offre est de plus en plus flexible : une entreprise disposant déjà de certaines solutions ou n’ayant pas les fonds pour l’offre complète peut louer une partie des services de l’XDR. Pour les entreprises ne disposant pas d’équipe d’investigation (CSIRT, SOC…) en interne c’est une solution très intéressante. Il est important de garder à l’esprit que l’XDR offre une simplicité de mise en place et une réduction des coûts, mais cela est au détriment de la qualité. La prise en main de l’outils et sa configuration par les équipes internes sera plus complexe.~~

### NDR

Network Detection and Response

La solution NDR (network detection and response) est une solution permettant de détecter des flux réseaux inhabituals au sein du SI en se basant sur des critères précis comme le volume, la fréquence, la date, ou encore la source des échange. En cas de comportement suspect, le NDR est également en mesure de mener des actions sur le réseau pour endiguer une éventuelle menace (mise en quarantaine d’une partie du réseau, coupure de certains types d’échanges, etc.).
Les solutions NDR utilisent l'intelligence artificielle pour analyser le réseau 

et si il y a une grande quantité de donnée cette solution est plus adaptée que le siem


Champ d'application : Trafic réseau et inter-appareils
Intention : Visibilité/transparence du trafic réseau, détection des menaces connues et inconnues et des mouvements latéraux, alerte et réponse.
Méthodes : Indicateur d'attaque (IoA), détection des anomalies, comportement de l'utilisateur, apprentissage automatique.
Défis : Attaques et intrusions avancées, attaques sans logiciels malveillants.

### SOAR

Le SOAR n’est pas un outil de détection : c’est un outil d’orchestration d’automatisation de la réponse à incident. Sur la base d’alertes, il déclenche une série d’actions à réaliser adaptées à chaque situation. soit c'est de compléter les informations de l’alerte, de la contextualiser, mais elles peuvent aussi répondre à l’incident. La flexibilité de l’outil fait de lui un réel support pour les analystes.

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

bref automatiser des taches dès qu'une menace est détecter 