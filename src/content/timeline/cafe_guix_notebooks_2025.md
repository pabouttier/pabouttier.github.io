---
author:
  name: "P.-A. Bouttier"
date: 2025-03-25
linktitle: notebooks_cafe_guix
type:
- post
- posts
title: Comment travailler avec des notebooks avec Guix à GRICAD ?
eventname: Café Guix Notebooks
eventlocation: Remote
weight: 10
---

[**Les slides HTML**](/talks/cafe_guix_notebooks_2025.html) - [**Les slides PDF**](/talks/cafe_guix_notebooks_2025.pdf)

## Abstract

Un bloc-notes Jupyter contient du code qui fait appel à des outils extérieurs : un interprète, un compilateur, des bibliothèques, etc. Cependant, ces dépendances ne sont pas explicites dans le bloc-notes. Dans ces conditions, comment garantir que deux personnes exécutant le bloc-notes dans un environnement différent obtiendront le même résultat ?

Autour d’un café ou autre breuvage de votre choix, nous verrons deux manières de régler ce problème : celle utilisée au GRICAD où Guix est utilisé pour déployer Jupyter Notebook et son environnement, et l’approche Guix-Jupyter qui consiste à ajouter des super-pouvoirs de déploiement reproductible à Jupyter
