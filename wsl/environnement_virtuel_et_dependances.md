# Création et gestion d'un environnement virtuel Python sous Debian 12

## Créer un environnement virtuel

```bash
mkdir /chemin/du/dossier/venv/du/projet/
```

```bash
python3 -m venv /chemin/du/dossier/venv/du/projet/
```

## Activation de l'environnement virtuel

```bash
. .venv/bin/activate
```

## Installation de dépendances avec pip

### 1. Depuis un fichier requirements.txt

**⚠️ Toujours vérifier que l'environnement virtuel souhaité soit activé avant d'installer des dépendances**

Exemple de fichier `requirements.txt` :

```
asgiref==3.8.1
Django==5.1.7
django-cors-headers==4.7.0
djangorestframework==3.15.2
djangorestframework_simplejwt==5.4.0
psycopg==3.2.4
psycopg-binary==3.2.4
PyJWT==2.10.1
python-dotenv==1.0.1
sqlparse==0.5.3
typing_extensions==4.12.2
```

```bash
pip install -r /chemin/vers/le/fichier/requirements.txt
```

### 2. Installation manuelle d'une dépendance

**⚠️ Toujours vérifier que l'environnement virtuel souhaité soit activé avant d'installer des dépendances**

Exemple pour installer la bibliothèque Django:

```bash
pip install Django
```

En précisant la version :

```bash
pip install Django==5.1.7
```

### 3. Mise à jour du fichier requirements.txt

```bash
pip freeze > /chemin/vers/le/fichier/requirements.txt
```
