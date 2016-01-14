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

Ce role vous fourni emacs installe et configure ainsi que les paquets necessaire pour les differents modules C

### Role LAMP

Le role ``LAMP`` n'a pas besoin de variables pour fonctionner.

Ce role installe sur une machine virtuelle tout le necessaire pour travailler sur un environnement LAMP (linux apache mysql php).
Il vous permet de travailler simplement en vous fournissant une version d'apache fonctionnelle est configuree pour ne pas avoir de probleme de droits pendant les deploiements ou encore pour eviter la fameuse manie du ``chmod -R 777``

Il place donc le repertoire de travail apache a la racine de votre repertoire utilisateur sur vagrant (``/home/vagrant/www``)

Pour lancer la configuration et l'installation, il vous suffit de taper :

``ansible-playbook playbook.yml -i hosts --tags "lamp"``
