# cicd-projet

Membres du groupe: Nizar ACHOURI, Nolan VANDEN TORREN

Projet forké à partir de: https://github.com/Huldoser/console-snake

# Fonctionnement

Le projet fonctionne jusqu'au déploiement via Nexus, en effet le build Jenkins renvoie une erreur 401 Unauthorized, indiquant que Maven n'a pas pu autoriser la connection vers Nexus. Nous avons essayé de régler ça en vérifiant bien les fichiers settings.xml et le pom.xml du fichier pour vérifier que l'id du serveur et les identifiants sont bien présents et corrects, mais rien ne change. Nous nous sommes basés sur le Jenkinsfile Nexus du cours, donc il semble bien que l'erreur vient de notre installation Nexus, mais nous n'avons pas trouvé d'explication, même en recréeant l'installation de Nexus en repartant de zéro.

# Problèmes rencontrés

Durant la réalisation du projet nous avons rencontré notamment beaucoup de problèmes avex le script Jenkinsfile qui ne semblait pas reconnaître Maven comme installé, nous y avons donc remédié en ajoutant un code tools qui nous permet d'indiquer à Jenkins la présence de Maven en l'installant sur le serveur local via Apache, car il ne reconnaissait pas l'installation locale de l'ordinateur.

Malgré ces problèmes de déploiement via Nexus, le build, packaging et vérification de tests (dont certains ajoutés pour procéder à des vérifications) fonctionnent correctement, c'est bien l'utilisation de Nexus qui nous a posé problème.
