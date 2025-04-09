# Installation de Git sous debian

## 1. Installation de Git [^1]

1. Se connecter en super-utilisateur

2. Saisir la commande `apt install git-all` 

    ![](./images/git_debian/ps_001.png)

3. Saisir `o` pour confirmer l'installation

    ![](./images/git_debian/ps_002.png)

4. Git est maintenant installé! Nous pouvons vérifier la version en saisissant `git --version`

    ![](./images/git_debian/ps_003.png)

5. Nous pouvons également nous déconnecter du compte root avec "Ctrl + D"

## 2. Configuration de git [^2]

1. Configurer le nom d'utilisateur en saisissant `git config --global user.name "<votre_nom>"`

    ![](./images/git_debian/ps_004.png)

2. Configurer l'email en saisissant `git config --global user.email <votre_email>`

    ![](./images/git_debian/ps_005.png)

3. Vérifier la configuration existante avec `git config --list`
    
    ![](./images/git_debian/ps_006.png)

    Nous voyons le nom et l'email saisis précedemment.

4. Optionnel: Définir le nom de branche par défaut à main avec `git config --global init.defaultBranch main`

5. Les autres options de configuration sont disponibles en saisissant `git config --help`

## 3. Connecter un compte github

1. Générer un Token sur Github

    _Si vous ne voulez pas créer de token, l'authentification via un navigateur web est aussi possible_
    
    - Se connecter à github

    - Cliquer sur l'icone de profil en haut à droite

        ![](./images/git_debian/firefox_002.png)

    - Aller dans "Settings"

        ![](./images/git_debian/firefox_003.png)

    - Aller dans "Developer settings"

        ![](./images/git_debian/firefox_004.png)

    - Cliquer sur "Personal access tokens"

        ![](./images/git_debian/firefox_005.png)

    - Puis sur "Tokens (classic)"

        ![](./images/git_debian/firefox_006.png)

    - Cliquer sur "Generate Token"

        ![](./images/git_debian/firefox_007.png)

    - Puis sur "Generate new token (classic)"

        ![](./images/git_debian/firefox_009.png)

    - Entrer un nom pour le token et sélectionner une durée d'expiration

        ![](./images/git_debian/firefox_010.png)

    - Sélectionner au minimum les autorisations suivantes: repo, workflow, read:org

        ![](./images/git_debian/firefox_014.png)

    - Cliquer sur "Generate Token"

        ![](./images/git_debian/firefox_011.png)

    - Copier le token généré

        ![](./images/git_debian/firefox_012.png)

2. Installer Github CLI `apt install gh`

3. Saisir `gh auth login`

    - Sélectionner "GitHub.com"

    - Sélectionner "HTTPS"

    - Entrer `y` pour confirmer

    - Sélectionner "Paste an authentication token"

    - Coller le token

    ![](./images/git_debian/ps_github.png)