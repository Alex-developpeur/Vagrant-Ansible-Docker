# vagrant ansible docker

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

* Création du fichier **.pre-commit-config.yml** pour le lancement des vérifications des fichiers **yaml** locaux.
  * Création du fichier **.ansible-lint** pour les règles de vérification des fichiers **ansible**.
  * Création du fichier **.yamllint** pour les règles de vérification des fichiers **yaml**.
* Création du fichier **.gitlab-ci.yml** pour le lancement des vérifications des fichiers **yaml** côté serveur.
  * Implémentation de l'image **quay.io/ansible/creator-ee:latest** pour les vérifications **ansible**.
  * Implémentation de **sdesbure/yamllint** pour les vérifications **yaml**