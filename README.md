# ansible-playbook-etna
Une collections de roles ansible pour la configuration de box vagrant pour les projets ETNA

## Requirements

* ansible
* vagrant

## Introduction

Ce repo a pour but de contenir un ensemble de roles ansible afin de configurer facilement vos VM pour vos differents projet
ETNA

## How to

### Global

Si vous souhaitez utiliser le Vagrantfile fourni dans ce repos, vous aurez besoin de modifier la ligne suivante :

``ansible.playbook = "~/ansible-playbook-etna/playbook.yml"``

Afin d'indiquer le repertoire ou vous avez colone ce repo

Une fois fait, la commande ``vagrant up`` vous generera la ligne necessaire a place dans votre fichier host ansible

[La doc de ansible pour vagrant](http://docs.ansible.com/ansible/guide_vagrant.html#running-ansible-manually)

NB: chaque roles possedera un tags specifique afin de vous permettre de les installer de maniere independante

### Role DEVC

Le role ``DEVC`` n'a besoin que de deux variables pour fonctionner.
Il s'agit des variables ``login`` et ``name`` situees dans le fichier ``ansible-playbook-etna/group_vars/all``

Une fois ces variables en place il vous suffit de lancer la commande :

``ansible-playbook playbook.yml -i hosts --tags "devc"``
