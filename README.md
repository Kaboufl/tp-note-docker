# TP Noté sur docker

Le but est de conteneuriser une application avec un frontend en React, un backend Flask, une base de données MySQL et le tout servi derrière un reverse proxy NGINX

Voici un diagramme résumant la structure des différents services de l'application :

![diagramme de la stack de l'application](https://github.com/Kaboufl/tp-note-docker/blob/main/docs/diagramme.png)

## Gestion des états des différents services

L'application a besoin d'avoir une base de données fonctionnelle ainsi que d'un backend connectée de manière effective à celle ci. C'est pour cela qu'un contrôle de l'état des conteneurs a été mis en place et segmente la mise en route de la pile de conteneurs.

Voici un détail de la séquence de démarrage (une étape est complétée quand le contrôle du fonctionnement du conteneur a été validé) :
1. Démarrage de la base de données
2. Démarrage du backend
3. Application des migrations
4. Démarrage de PHPmyAdmin
5. Démarage du frontend
6. Démarrage du reverse proxy

## Lancer l'application

En premier lieu, il faut paramétrer l'environnement de l'application, pour ce faire, dupliquez `.env.example` vers `.env`, et éditez les variables à votre convenance

> ```bash
>  cp .env.example .env 
> ```

Ensuite, construisez les images des conteneurs :

```bash
docker compose build
```

Enfin, lancez l'application :

```bash
docker compose up

# Ou lancer l'application en mode deamon en ajoutant le flag -d
docker compose up -d
```
Sinon, vous pouvez faire les deux étapes en même temps : 

```bash
docker compose up --build
```
