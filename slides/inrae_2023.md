---
marp: true
theme: socrates
author: Pierre-Antoine Bouttier
paginate: true
footer: GitLab@CNRS, 29/06/2023 - pierre-antoine.bouttier@univ-grenoble-alpes.fr
---

<!-- _class: titlepage -->


![bg left:33% fit](fig/jupgiter.png)
# Notebooks Jupyter et GitLab
## Retour d'expérience

### GitLab@CNRS - 29/06/2023
#### [Pierre-Antoine Bouttier](mailto:pierre-antoine.bouttier@univ-grenoble-alpes.fr)

---
# D'où je parle

- Ingénieur de recherche, expert en ingénieurie logicelle, spécialisé en mathématiques appliquées, ...
- ...directeur adjoint de **l'UAR GRICAD**, basée à Grenoble, fournissant **services, infrastructures et expertise** en soutien à toutes les communautés de recherche grenobloises autour du **calcul scientifique**, du **développement logiciel** et de la **gestion des données de la recherche**.  
- Je ne suis pas...
  - ...un ASR
  - ...un chercheur en informatique

---
# TOC

<!-- _class: cool-list -->

1. *Les notebooks jupyter, qu'est-ce que c'est ?*
2. *Quelques considérations pratiques*
3. *GitLab pour partager vos notebooks*

---
# TOC

<!-- _class: cool-list -->

1. ***Les notebooks jupyter, qu'est-ce que c'est ?***
2. *Quelques considérations pratiques*
3. *GitLab pour partager vos notebooks*

---
# Les notebooks Jupyter, en bref

Les notebooks Jupyter peuvent être vus comme :
  - des cahiers électroniques...
  - ... accessibles via un **navigateur**...
  - ... constitués de différentes **cellules**

---
# Les notebooks Jupyter, en bref

Les cellules peuvent contenir :
  - du texte formatté (markdown)
  - des images 
  - des formules mathématiques
  - du code logiciel exécutable

---
# Les notebooks Jupyter, en bref

Initialement développés pour les langages Julia, Python et R (Jupyter), aujourd'hui, plus de 40 langages sont supportés. 
- Un notebook peut être exporté sous différents formats (HTML, PDF, LaTeX, etc.)
- Il est facile d'extraire uniquement les cellules de code d'un notebook
- Vous pouvez installer `jupyter-notebook` sur votre machine et ainsi, les notebooks s'exécuteront sur votre machine (accès par navigateur)

---
<!-- _class: transition -->

### [Une démo vaut mille mots](https://gtdonnees-gitlab2023.gricad-pages.univ-grenoble-alpes.fr/rexp-notebooks/jupyterlite)

---
# À quoi ça peut servir ? 

Les notebooks sont des outils vraiment pertinents pour *transmettre* de la connaissance : 
* Documenter l'usage d'un code logiciel 
* Exposer un raisonnement, une méthodologie incluant du code logiciel
* Écrire des articles enrichis, des tutos, des HOWTO
* etc.


---
# À quoi ça ne devrait pas servir ?

* **Développer du code logiciel !** : Code dans les notebooks difficilement maintenable, modulaire, lisible, etc. 
* **Fournir un notebook ne garantit pas, en soi, la reproductibilité du travail ainsi présenté !**
* Selon l'environnement d'exécution, performances médiocres

---
# TOC

<!-- _class: cool-list -->

1. *Les notebooks jupyter, qu'est-ce que c'est ?*
2. ***Quelques considérations pratiques***
3. *GitLab pour partager vos notebooks*

---
# Comment exécuter un notebook ? 

Sur son ordinateur, la méthode classique

- On installe `jupyterlab` sur son ordinateur
- On installe les librairies logicielles dont notre code, dans nos notebooks, a besoin
- On lance un serveur jupyter sur notre ordinateur
- On accède aux notebooks via le navigateur 

---
# Quelques freins

* L'interface client/serveur perturbante pour les débutants
* Beaucoup de choses à installer...
* ...qui peuvent faire intervenir diffrents outils, plus ou moins disponible selon les ordinateurs

---
# Et pour une formation ? 

Si vous voulez proposer des supports de formations à plusieurs étudiants :
* Il faudra qu'ils fassent tout de leur côté :  
  * Avec des OS potentiellement hétérogènes
  * Avec des compétences hétérogènes
* Ou alors, il va falloir proposer un serveur de notebooks vous-même accessible aux étudiants : fastideux et qui peut-être compliqué.

---
# TOC

<!-- _class: cool-list -->

1. *Les notebooks jupyter, qu'est-ce que c'est ?*
2. *Quelques considérations techniques*
3. ***GitLab pour partager vos notebooks***

---
# GitLab à la rescousse

Grâce à GitLab, il est possible de fournir des notebooks ET leur environnement d'exécution simplement !

Nous allons parcourir deux options pour ce faire : 
- [BinderHub](https://binderhub.readthedocs.io/en/latest/)
- [JupyterLite](https://jupyterlite.readthedocs.io/en/latest/)

---
# BinderHub

BinderHub est un service web qui permet, à la volée, à partir d'un projet GitLab publique, de déployer à la volée des environnements d'exécution de notebooks. 

- [Un site basé sur ce service accessible au grand public](https://mybinder.org)
- [Le site basé sur ce service pour le site ESR grenoblois](jupyterhub.univ-grenoble-alpes.fr) (VPN UGA requis)

---
<!-- _class: transition -->

### [Un petit tour sur le projet GitLab...](https://gricad-gitlab.univ-grenoble-alpes.fr/gtdonnees-gitlab2023/rexp-notebooks)

### [...BinderHub en action](https://binderhub.univ-grenoble-alpes.fr)

---
# Jupyterlite

JupyterLite permet de fournir un environnement d'exécution JupyterLab sans l'architecture client/serveur (et donc sans les complications qui vont avec)

* En une commande, jupyterlite génère un site statique (des pages html simples), accompagné de vos notebooks et d'autres fichiers si vous le souhaitez
* À l'aide d'un serveur web, **ce site s'exécutera comme une interface jupyterlab dans le navigateur de l'étudiant**

---
# En quoi c'est plus simple ? 

Mais comment j'installe et je configure un serveur web ? 

* GitLab peut le faire pour vous !...
* À l'aide de la CI/CD, dans le `.gitlab-ci.yml`, il suffit de générer le site avec JupyterLite et de le publier avec GitLab Pages.  

---
<!-- _class: transition -->

### [Retour sur le projet GitLab...](https://gricad-gitlab.univ-grenoble-alpes.fr/gtdonnees-gitlab2023/rexp-notebooks)

### [...JupyterLite en live](https://gtdonnees-gitlab2023.gricad-pages.univ-grenoble-alpes.fr/rexp-notebooks/jupyterlite/)

---
# TL;DR (1/3)

Les notebooks sont de chouettes outils : 
- Pour exposer une méthodologie
- En tant que support de cours
- Pour expliquer le fonctionnement d'un code logiciel/d'une chaîne de traitement de données

---
# TL;DR (2/3)

Les notebooks ne sont pas adaptés pour : 
- La reproductibilité (ils ne la garantissent pas)
- Le développement logiciel
- La performance (calcul et IO)

---
# TL;DR (3/3)

Vous avez à votre disposition au moins 2 méthodes pour déployer simplement un environnement d'exécution pour vos notebooks, facilement diffusables et partageables (une url simple à transmettre) :
* BinderHub
* JupyterLite

[N'hésitez pas à vous inspirer de ce dépôt pour déployer vos environnements d'exécution de notebooks !](https://gricad-gitlab.univ-grenoble-alpes.fr/gtdonnees-gitlab2023/rexp-notebooks)

---
<!-- _class: transition -->

# Merci de votre attention !