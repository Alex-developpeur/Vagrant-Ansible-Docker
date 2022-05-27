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