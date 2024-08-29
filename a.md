## Tutoriel: Création d'un Projet Django et Gestion Git/GitHub

# Installer Django
pip install django
   3. ** Creer un  environnenment virtuel***
```bash
# Créer un environnement virtuel
python3 -m venv env

# Activer l'environnement virtuel
# Sur Windows
env\Scripts\activate
# Sur macOS/Linux
source env/bin/activate

# Installer Django
pip install django
```

### Étape 2: Créer un projet Django

Un projet Django est un conteneur pour votre application ou vos applications Django. Pour créer un projet Django, exécutez la commande suivante:

```bash
django-admin startproject myproject
```

Cela créera un répertoire `myproject` avec les fichiers et répertoires suivants:

- `manage.py`: Un utilitaire pour gérer votre projet Django.
- Un répertoire `myproject` contenant les paramètres du projet, les URLs, etc.

### Étape 3: Créer une application Django

Une application dans Django est un module spécifique qui gère un aspect particulier du projet. Pour créer une application, exécutez la commande suivante dans le répertoire de votre projet:

```bash
cd myproject
python manage.py startapp myapp
```

Cela créera un répertoire `myapp` avec la structure suivante:

- `models.py`: Contient les modèles de données.
- `views.py`: Contient les vues qui gèrent la logique de votre application.
- `urls.py`: (à créer) Contient les URL de votre application.
- `admin.py`: Contient les configurations pour l'interface d'administration de Django.
- `apps.py`: Contient la configuration de votre application.
- `migrations/`: Contient les migrations de votre base de données.

### Étape 4: Configurer l'application dans le projet

Pour que Django reconnaisse votre application, ajoutez-la dans le fichier `settings.py` de votre projet:

1. Ouvrez `myproject/settings.py`.
2. Trouvez la liste `INSTALLED_APPS`.
3. Ajoutez votre application à cette liste, par exemple:

```python
INSTALLED_APPS = [
    ...
    'myapp',
    ...
]
```

### Étape 5: Créer un modèle de données

Un modèle de données dans Django représente une table dans votre base de données. Voici un exemple simple d'un modèle:

```python
# myapp/models.py
from django.db import models

class Article(models.Model):
    title = models.CharField(max_length=200)
    content = models.TextField()
    published_at = models.DateTimeField(auto_now_add=True)

    def __str__(self):
        return self.title
```

### Étape 6: Créer et appliquer les migrations

Après avoir défini votre modèle, vous devez créer et appliquer les migrations pour générer les tables correspondantes dans la base de données.

```bash
python manage.py makemigrations
python manage.py migrate
```

### Étape 7: Créer une vue et un template

Une vue dans Django reçoit les requêtes HTTP, traite les données, et renvoie une réponse. Vous pouvez également créer des templates HTML pour rendre les vues plus dynamiques.

1. **Créer une vue simple**:

```python
# myapp/views.py
from django.http import HttpResponse

def home(request):
    return HttpResponse("Hello, Django!")
```

2. **Créer un template**:

Dans le répertoire de votre application `myapp`, créez un dossier `templates` et un fichier `home.html`:

```html
<!-- myapp/templates/home.html -->
<!DOCTYPE html>
<html>
<head>
    <title>Home</title>
</head>
<body>
    <h1>Bienvenue sur mon application Django!</h1>
</body>
</html>
```

3. **Rendre un template depuis une vue**:

Modifiez la vue pour qu'elle rende le template:

```python
# myapp/views.py
from django.shortcuts import render

def home(request):
    return render(request, 'home.html')
```

### Étape 8: Configurer les URLs

Pour que Django sache quelle vue afficher pour quelle URL, vous devez configurer les URLs.

1. **Créer un fichier `urls.py` dans l'application**:

```python
# myapp/urls.py
from django.urls import path
from .views import home

urlpatterns = [
    path('', home, name='home'),
]
```

2. **Inclure les URLs de l'application dans le projet**:

Modifiez `myproject/urls.py` pour inclure les URLs de l'application:

```python
# myproject/urls.py
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('myapp.urls')),
]
```

### Étape 9: Démarrer le serveur de développement

Vous pouvez maintenant démarrer le serveur de développement pour voir votre application en action:

```bash
python manage.py runserver
```

Visitez `http://127.0.0.1:8000/` dans votre navigateur pour voir la page d'accueil.

### Étape 10: Continuer le développement

À partir de là, vous pouvez ajouter plus de fonctionnalités à votre application Django, comme la gestion de formulaires, l'authentification des utilisateurs, l'intégration d'une base de données, etc. Django est très flexible et extensible, donc les possibilités sont vastes.

N'hésitez pas à demander si vous avez des questions spécifiques ou si vous voulez approfondir certaines parties du processus!
