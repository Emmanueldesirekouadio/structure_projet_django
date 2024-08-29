## Tutoriel: Création d'un Projet Django et Gestion Git/GitHub

### 1. Initialiser un Nouveau Projet Django

Pour commencer, vous devez installer Django et créer un nouveau projet. Suivez les étapes ci-dessous :

1. **Installer Django :**

   ```bash
   pip install django
   ```

2. **Créer un Projet Django :**

   ```bash
   django-admin startproject mon_projet
   cd mon_projet
   ```

3. **Créer une Nouvelle Application Django :**

   ```bash
   python manage.py startapp mon_application
   ```

4. **Configurer l'Application :**
   Ajoutez votre application au fichier `settings.py` dans la section `INSTALLED_APPS`.

### 2. Initialisation d'un Dépôt Git

Une fois votre projet Django créé, vous pouvez initialiser un dépôt Git

1. **Initialiser Git :**

   ```bash
   git init
   ```

2. **Ajouter un `.gitignore` :**
   Créez un fichier `.gitignore` et ajoutez les fichiers et répertoires :

   ```plaintext
   *.pyc
   __pycache__/
   db.sqlite3
   .env
   ```
