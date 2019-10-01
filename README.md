# Introduction à Cassandra

## Installation de Cassandra sur Windows

Prérequis pour l'installation de Cassandra sur Windows :

- l'archive de Cassandra, disponible sur http://cassandra.apache.org/download/, version 3.11.4
- JDK Oracle 8, disponible sur . Attention, cassandra en version 3.11.4 ne detecte pas les versions OpenJDK ou JDK 11 comme compatibles
- Python 2.7, disponible sur 

Le JDK Oracle est nécessaire pour faire tourner le serveur Cassandra. Python sert à lancer le client `cqlsh` pour se connecter au serveur.

### Installation d'un JDK Oracle

Télécharger le JDK Oracle sur https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html. Lancer l'installation et suivre les étapes pas à pas.

### Installation de Python 2.7

Télécharger python sur https://www.python.org/download/releases/2.7/ et lancer l'installation. Si le système est déjà équipé d'un Python en version 3, laisser l'option *mettre à jour le PATH* désactiver pour ne pas remplacer le Python 3 par défaut. Nous modifierons le PATH au besoin au moment de lancer les clients.

### Lancement du serveur Cassandra

Cassandra ne nécessite pas d'installation. Télécharger l'archive sur http://cassandra.apache.org/download/ et la décompresser.

L'archive contient un dossier `bin` dans lequel se trouve des scripts bat que nous allons utiliser pour lancer le serveur et le client. Les opérations suivantes se font dans une fenêtre cmd.

Avant toute chose, modifier la variable d'environnement `PATH` pour faire référence aux bonnes versions de Java et de Python :

    set PATH=C:\Python2.7;"c:\Program Files\Java\jdk1.8.0_221\bin";%PATH%

ensuite, dans le dossier `bin` de l'archive Cassandra, lancer le serveur à l'aide du script :

    cassandra.bat

Des logs doivent défiler à l'écran, c'est bon signe du démarrage du serveur.

### Vérification de l'état du serveur

Dans la même fenêtre cmd que précédement, ou dans une nouvelle en ayant précédement mis à jour le PATH, aller dans le dossier `bin` de l'archive Cassandra et lancer :

    nodetool status

Cette commande affiche le status des noeuds Cassandra, s'il affiche un serveur up, tout va bien !

### Lancement du client cqlsh

Toujours dans la même fenêtre cmd, ou dans une nouvelle en ayant spécifié le PATH qui va bien, lancer la commande :

    cqlsh.bat

Après un certains nombre de messages, le prompt doit devenir `cqlsh>`. Vous êtes maintenant prèt à lancer des commandes CQL !