# TP Noté sur docker

Le but est de conteneuriser une application avec un frontend en React, un backend Flask, une base de données MySQL et le tout servi derrière un reverse proxy NGINX

Voici un diagramme résumant la structure des différents services de l'application :

![diagramme de la stack de l'application](http://url/to/img.png)

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
