# vagrant ansible docker

## Cahier des charges

### TP : Construction et manipulation de rôle
Objectif : Construire ses propres **rôles** pour déployer un **wordpress** sous **docker**  
Travail d'équipe : oui  
Besoin :
- Création d'un serveur sous **debian 11** avec vagrant
* Création des **rôles ansible** suivants :
  * **sys-common** : ce rôle doit regrouper toutes vos pratiques d'installation par défaut (création d'utilisateur, mise à jour système, paramétrage de la timezone, hostname...)
  * **sys-docker** : ce rôle doit vous permettre l'installation de **docker** et **docker-compose**
  * **dck-wordpress** : ce rôle vous permet de déployer un **wordpress** sous **docker** (penser à utiliser le **docker-compose** du précédent TP)
- L'ensemble des **rôles** peuvent être appelé par le **playbook** principale **main.yml**
- Essayer d'utiliser le **provisionner ansible** local pour vous permettre d'exécuter les **playbooks** directement sur la machine guest

Rendu :
- Versionner votre code dans un projet **GitLab**
- Documenter son usage dans un document **README.md**

## Réalisation
- Création d'un fichier **Vagrantfile** avec une image **Debian**.
```bash
vagrant up
```
- Création des roles ansible
```bash
sudo ansible-galaxy init sys-common
sudo ansible-galaxy init sys-docker
sudo ansible-galaxy init dck-wordpress
```
- Création du playbook **deploy.yml**
```bash
sudo ansible-palybook deploy.yml
```

## Cahier des charges
test
### TP : Configurer un projet git ansible
Objectif : Améliorer le projet Git ansible  
Travail d'équipe : semi  
Besoin :
- Découvrir la notion de pre-commit
- **Ajouter** un fichier .pre-commit-config.
* yaml pour :
  * vérifier la syntax yaml --> yamllint
  * vérifier ansible --> ansible-lint
* Ajouter une intégration continue avec 2 jobs :
  * ansible_lint
  * yaml_lint

Rendu :
- Versionner votre code dans un projet GitLab
- Documenter son usage dans un document README.md

## Réalisation
* Création du fichier **.pre-commit-config.yml** pour le lancement des vérifications des fichiers **yaml** locaux.
  * Création du fichier **.ansible-lint** pour les règles de vérification des fichiers **ansible**.
  * Création du fichier **.yamllint** pour les règles de vérification des fichiers **yaml**.
* Création du fichier **.gitlab-ci.yml** pour le lancement des vérifications des fichiers **yaml** côté serveur.
  * Implémentation de l'image **quay.io/ansible/creator-ee:latest** pour les vérifications **ansible**.
  * Implémentation de **sdesbure/yamllint** pour les vérifications **yaml**