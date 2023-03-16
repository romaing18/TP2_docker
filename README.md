## Compléter le Dockerfile afin de builder correctement l’application contenu dans src/

Voir le commit Question 1

### Une option de npm vous permet de n’installer que ce qui est nécessaire. Quelle est cette option ? Quelle bonne pratique Docker permet t-elle de respecter ?

_**L’option permettant de pouvoir installer seulement les dépendances nécessaires est : --production.**_

### A l’aide de la commande docker build, créer l’image ma_super_app

Commande qui permet de créer l’image ma_super_app : “docker build -t ma_super_app .”

### Compléter le fichier docker-compose.yml afin d’éxécuter ma_super_app avec sa base de données.

-   fichier “docker-compose.yml” :

```
version:  '3.9'
services:
	node:
		image:  nod
		environment:
			-  NODE_ENV=${NODE_ENV}
			-  PORT=${PORT_NODE}
		ports:
			-  "${PORT_NODE}:${PORT_NODE}"
		depends_on:
			-  mysql
	mysql:
		image:  mysql:8.0
		environment:
			-  MYSQL_DATABASE=${MYSQL_DATABASE}
			-  MYSQL_USER=${MYSQL_USER}
			-  MYSQL_PASSWORD=${MYSQL_PASSWORD}
		ports:
```

-   fichier “.env” :

```
#var env NODE
NODE_ENV=production
PORT_NODE=8080

#var env MYSQL
MYSQL_DATABASE=tp02
MYSQL_USER=romain
MYSQL_PASSWORD=romaing
MYSQL_PORT=3000
```
