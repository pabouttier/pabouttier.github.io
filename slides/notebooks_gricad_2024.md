---
marp: true
theme: socrates
author: Pierre-Antoine Bouttier
paginate: true
footer: pierre-antoine.bouttier@univ-grenoble-alpes.fr - CC BY-SA 4.0
---

<!-- _transition: cover -->

<!-- _class: titlepage -->

# Jupyter@GRICAD
## **Comment travailler avec des notebooks dans un mésocentre de calcul ?**

### Webinaire GT notebooks, 04/10/2024
#### [Pierre-Antoine Bouttier](mailto:pierre-antoine.bouttier@univ-grenoble-alpes.fr), CNRS/GRICAD

---
# TOC

<!-- _class: cool-list -->

1. *GRICAD & Jupyter*
3. *Jupyter sur un supercalculateur*
4. *Remarques sur les notebooks et le HPC*

---

<!-- _transition: vertical-scroll -->

# TOC

<!-- _class: cool-list -->

1. ***GRICAD & Jupyter***
3. *Jupyter sur un supercalculateur*
4. *Remarques sur les notebooks et le HPC*

---

<!-- _transition: vertical-scroll -->

# Les missions de GRICAD

- **Accompagnement, conseils et formations** aux chercheurs sur leurs besoins liés au calcul scientifique, aux données de la recherche
- Mise à disposition **de services et d'infrastructures avancés et mutualisés** pour le calcul intensif et l’exploitation des données de la recherche...
- ...**Librement accessibles**, à destination de l'ensemble des **communautés de recherche grenobloises et de leurs collaborateurs**

---

<!-- _transition: vertical-scroll -->

# Notre offre de services numériques

<div align="center">

![center w:850](./fig/offre_services.png)

</div>

---

<!-- _transition: vertical-scroll -->

# JupyterHub@GRICAD

- Accessible à tous les personnels dans le référentiel UGA
- Quota de 20Go de données par utilisateur. Données persistantes.
- Usages : traitements de données légers, développement de notebooks, hébergement de notebooks pour formations, etc.
* Intérêt limité SAUF pour l'enseignement (mais hors périmètre GRICAD...)

---

<!-- _transition: vertical-scroll -->

# Le cloud computing

- Plateforme Openstack permettant de fournir des VM à la demande avec ressources ajustables (RAM, vCPU, éventuellement vGPUs)
- Possibilité d'avoir des centaines de GO, des dizaines de Go de RAM/vCPU et un vGPU.
- Installation et maintenance de la VM à charge des utilisateurs : JupyterLab/Hub, administration de la/des VM(s)
* Usages beaucoup plus diversifiés (en terme de ressources mais aussi de périmètre)
* ...au prix de plus d'efforts côté utilisateurs

---

<!-- _transition: vertical-scroll -->

# Les supercalculateurs

2 principaux clusters :
- ***Dahu***, orienté HPC classique, traitement massif de données
- ***Bigfoot***, orienté IA/calcul sur GPU.

<div align="center">

![w:500](./fig/infras.png)

</div>

---
<!-- _class: transition -->

<!-- _transition: cover -->

Pourquoi et comment exécuter des notebooks sur les supercalculateurs ?

---

<!-- _transition: vertical-scroll -->

# TOC

<!-- _class: cool-list -->

1. *GRICAD & Jupyter*
3. ***Jupyter sur un supercalculateur***
4. *Remarques sur les notebooks et le HPC*
