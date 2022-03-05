# django-best-video-games- CREDIT: Taylor White

# Steps to create a basic two page Django Project using poetry

### Step 1 - Creating the Project

- Create a project folder(make sure to use '-' and not '_' in the file name)
- A key thing to remember is the difference between your project folder and your app folder.
  - Example: mkdir django-project

- cd into project folder and run these commands:
  - poetry init -n
  - poetry add django
  - poetry shell

- In Terminal run:  
  - django-admin startproject django_things . <--- Do not forget the '.' or do, I cant tell you what to do, i'm just text.
  - python manage.py migrate

- Run the server by using:
  - python manage.py runserver

In your browser navigate to <http://127.0.0.1:8000> (Port number may differ)

### Step 2 - Define the App

- Create a folder for the App
  - python manage.py startapp project-name-here

- Open your project by using 'code .' inside of your terminal.

- Navigate to settings.py and locate a list named 'INSTALLED_APPS'
  - At the end of the list add your project name. (Don't forget the comma at the end)

### NOTE: From here the steps can be completed in any order as long as they are all completed  

### Step 3 - Add Views

- Navigate to views.py onside of your app folder
- Remove the default code
Add in the code below:

```
from django.views.generic import TemplateView

class HomePageView(TemplateView):
  template_name ='home.html'
```

### Step 4 - Add urlpattens

- Navigate to the app folder and create a file named urls.py
- Add in the code below:

```
from django.urls import path
from .views import HomePageView, AboutPageView

urlpatterns = [
  path('', HomePageView.as_view(), name='home'),
  path('about', AboutPageView.as_view(), name='about')
]
```

- Navigate to urls.py file inside of the project folder and add the code below:

```
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('best_games.urls')),
]
```

### Step 5 - Create Templates

- Navigate to the project folder in Terminal
- Run:
  - touch templates/home.html
  - touch templates/base.html
  - touch templates/about.html
- Open the base.html and add:

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</head>
<body>
  <header>
    <nav>
      <a href={%url 'home' %}>Home</a>
      <a href={%url 'about' %}>about</a>
    </nav>
  </header>
  {% block content  %}
  {% comment %} content goes here {% endcomment %}
  {% endblock content %}
</body>
</html>
```

- Open home.html and add:

```
{%extends 'base.html'%}

{% block content  %}
<h1>Home Page</h1>
{% endblock content %}
```

- Open about.html and add:

```
{%extends 'base.html'%}

{% block content  %}
<h1>About Page</h1>
{% endblock content %}
```

- Navigate to settings.py inside the project folder
  - Locate the TEMPLATES list of objects and find the 'DIRS' list
  - Add BASE_DIR/'templates' to that list

- Now run the server and you should she your new page. You're doing great!

### This section is for setting up testing and is considered seperate to the steps above

- Navigate to your app folder, and create a file named 'tests.py'
- Insert the code below for basic tests:

```
from django.test import SimpleTestCase
from django.urls import reverse

class ThingsTests(SimpleTestCase):
  def test_home_page_status_code(self):
  url = reverse('home')
  response = self.client.get(url)
  self.assertEqual(response.status_code, 200)
 def test_home_base_template(self):
  url =reverse('home')
  response = self.client.get(url)
  self.assertTemplateUsed(response, 'home.html')
  self.assertTemplateUsed(response, 'base.html')
```

- Now run python manage.py test in terminal and they should pass.
