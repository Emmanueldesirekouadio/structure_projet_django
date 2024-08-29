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

Une fois votre projet Django créé, vous pouvez initialiser un dépôt Git pour le contrôle de version.

1. **Initialiser Git :**

   ```bash
   git init
   ```

2. **Ajouter un `.gitignore` :**
   Créez un fichier `.gitignore` et ajoutez-y les fichiers et répertoires que vous ne souhaitez pas suivre avec Git, par exemple :

   ```plaintext
   *.pyc
   __pycache__/
   db.sqlite3
   .env
   ```

3. **Premier Commit :**
   ```bash
   git add .
   git commit -m "Initial commit"
   ```

### 3. Maintien d'un Statut Git Propre

Il est crucial de maintenir un statut Git propre pour une gestion efficace du code. Voici quelques pratiques recommandées :

- **Effectuez des commits réguliers** : enregistrez fréquemment vos changements avec des messages de commit clairs.
- **Utilisez `git revert` ou `git reset`** pour revenir en arrière en cas d'erreur.
- **Stashing** : utilisez `git stash` pour sauvegarder temporairement vos modifications non commit, vous permettant de travailler sur d'autres branches ou tâches sans perdre vos changements en cours.

### 4. Création et Gestion des Branches

Travailler sur des branches distinctes est une bonne pratique pour éviter les conflits et organiser le développement.

1. **Créer une Nouvelle Branche :**

   ```bash
   git checkout -b nouvelle_fonctionnalité
   ```

2. **Ne travaillez pas directement sur la branche `main`** : cela évite de pousser des modifications non testées sur la branche principale.

3. **Pousser une Branche vers GitHub :**
   ```bash
   git push -u origin nouvelle_fonctionnalité
   ```

### 5. Fusion et Conflits de Branches

Fusionner des branches peut entraîner des conflits qu'il est important de savoir résoudre.

1. **Vérifier la Branche Principale :**

   ```bash
   git checkout main
   git pull origin main
   ```

2. **Fusionner une Branche :**

   ```bash
   git merge nouvelle_fonctionnalité
   ```

3. **Résolution des Conflits :**
   En cas de conflit, Git indiquera les fichiers concernés. Ouvrez ces fichiers, corrigez les conflits, puis ajoutez et committez les modifications :
   ```bash
   git add fichier_conflit
   git commit -m "Résolution des conflits de fusion"
   ```

### 6. Navigation sur GitHub

Savoir naviguer sur GitHub est essentiel pour comprendre l'historique du projet et collaborer efficacement.

1. **Cloner un Dépôt :**

   ```bash
   git clone https://github.com/utilisateur/projet.git
   ```

2. **Télécharger en Zip :**
   Pour un aperçu rapide du code, vous pouvez télécharger un dépôt en format zip directement depuis GitHub.

3. **Comprendre l'Historique des Commits** : utilisez GitHub pour suivre les méthodes employées par d'autres contributeurs et apprendre de leur travail.

### 7. Clonage et Flux de Travail

Une fois le dépôt cloné, gérez efficacement votre flux de travail pour éviter les erreurs :

- **Cloner un Dépôt :** comme mentionné précédemment, assurez-vous de bien comprendre la différence entre cloner et récupérer (`fetch`) un dépôt.
- **Gérer les Dépôts Locaux et Distants :** utilisez des commandes comme `git fetch` et `git pull` pour synchroniser vos dépôts.

### 8. Résolution des Conflits de Fusion

La gestion des conflits est une compétence clé dans le travail collaboratif.

1. **Créer et Résoudre un Conflit de Fusion :**
   Après avoir modifié le même fichier sur deux branches différentes, une fusion peut entraîner un conflit. Résolvez-le en choisissant quelle version du code conserver, puis committez les changements.

2. **Commettre Avant de Fusionner :**
   Il est important de toujours commit vos modifications avant d'essayer de fusionner, pour éviter de perdre du travail.
