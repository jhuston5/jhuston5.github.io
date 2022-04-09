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

python manage.py makemigration
python manage.py migrate
python manage.py createsuperuser

### DOCKER

Create a new project with no templates or views, just a desired model.

poetry add djangorestframework
Add to settings
INSTALLED APPS add 'rest_framework',
REST_FRAMEWORK = {
    'DEFAULT_PERMISSION_CLASSES' : [
        'rest_framework.permissions.AllowAny',
    ]
}

Set app urls
from django.urls import path
from .views import DockerizeList, DockerizeDetail

urlpatterns = [
  path('', DockerizeList.as_view(), name='dockerize_list'),
  path('<int:pk>/', DockerizeDetail.as_view(), name='dockerize_detail'),
  ]

set up views file
from django.shortcuts import render
from rest_framework import generics
from .serializer import DockerizeSerializer
from .permissions import IsOwnerOrReadOnly
from .models import Dockerize

# Create your views here

# class DockerizeList(generics.ListAPIView)

# queryset = Dockerize.objects.all()

# serializer_class = DockerizeSerializer

```Python
class DockerizeList(generics.ListCreateAPIView):
  permission_classes = (IsOwnerOrReadOnly,)
  queryset = Dockerize.objects.all()
  serializer_class = DockerizeSerializer

class DockerizeDetail(generics.RetrieveUpdateDestroyAPIView):
  permission_classes = (IsOwnerOrReadOnly,)
  queryset = Dockerize.objects.all()
  serializer_class = DockerizeSerializer
```

create serializer.py inside the app folder

```Python
from rest_framework import serializers
from .models import Dockerize

class DockerizeSerializer(serializers.ModelSerializer):
  class Meta:
    fields = ('id', 'owner', 'name', 'description', 'created_at', 'updated_at')
    model = Dockerize
```

In base directory:
Create Dockerfile
Create docker-compose.yml

#### Dockerfile

```Python
FROM python:3
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
RUN mkdir /code
WORKDIR /code
COPY requirements.txt /code/
RUN pip install -r requirements.txt
COPY . /code/
```

#### docker-compose.yml

```Python
version: '3'

services:
  web:
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
    depends_on:
      - db
  db:
    image: postgres
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres

```

DOCKERFILE
poetry export -f requirements.txt -o requirements.txt --without-hashes

VENV
pip freeze >> requirements.txt

docker compose up
docker compose down
docker nuke
docker container stop $(docker container ls -a -q); docker system prune -a -f --volumes
docker compose run web python manage.py migrate [Use this to migrate after installing postgres]

Other useful commands
docker compose start
docker compose stop

to do a "reset"
nuke
migrate
up

### Permissions

Add to urlpatterns:
 path('api-auth', include('rest_framework.urls'))

Change REST_Framework to 'rest_framework.permissions.IsAuthenticated',

Create permissions.py folder in app

``` Python

from math import perm
from rest_framework import permissions
class IsOwnerOrReadOnly(permissions.BasePermission):
  def has_object_permission(self, request, view, obj):
      if request.method in permissions.SAFE_METHODS:
        return True
  
      if obj.owner is None:
        return True

      return obj.owner == request.user
```

### POSTGRES

 <!-- Updated -->
 DATABASES = {
     'default': {
         'ENGINE': 'django.db.backends.postgresql',
         'NAME': 'postgres',
         'USER': 'postgres',
         'PASSWORD': 'postgres',
         'HOST': 'db',
         'PORT': 5432,
     }
 }

<!-- docker-compose.yml -->
version: '3'

services:
  web:
    build: .
    command: python manage.py runserver 0.0.0.0:8000
    volumes:
      - .:/code
    ports:
      - "8000:8000"
     depends_on:
       - db
   db:
     image: postgres
     environment:
       - POSTGRES_DB=postgres
       - POSTGRES_USER=postgres
       - POSTGRES_PASSWORD=postgres

- under depends on might need to add a links: -db
poetry add psycopg2-binary
Update the requirements.txt file
poetry export -f requirements.txt -o requirements.txt --without-hashes

use

### JWT

poetry add djangorestframework_simplejwt
update requirements.txt

##### In project settings.py - Rest Framework section add

'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework_simplejwt.authentication.JWTAuthentication',
        'rest_framework.authentication.SessionAuthentication',
        'rest_framework.authentication.BasicAuthentication',
    ]

##### In Project urls.py - urlpatterns import and add

from rest_framework_simplejwt import views as jwt_views
    path('api/token/', jwt_views.TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh', jwt_views.TokenRefreshView.as_view(), name='token_refresh'),

### In App views.py import and change

- from rest_framework.permissions import IsAuthenticated
change permission classes to IsAuthenticated

- Optional for troubleshooting
poetry add httpie
http POST :8000/api/token username=admin password=admin

### Gunicorn

- Production level server
poetry add gunicorn

##### In docker-compose.yml change command to (changing to the project name as needed)

gunicorn tracker_proj.wsgi:application --bind 0.0.0.0:8000 --workers 4

- Install Whitenoise and add to middleware in project settings.py
poetry add whitenoise

MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'whitenoise.middleware.WhiteNoiseMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.contrib.messages.middleware.MessageMiddleware',
    'django.middleware.clickjacking.XFrameOptionsMiddleware',
]

- Also in settings.py add STATIC ROOT after STATIC_URL
STATIC_ROOT = BASE_DIR / 'staticfiles'

- In the terminal run
python manage.py collectstatic

#### AWS Production

Create Elephant SQL Instance
Connect to env file
SECRET_KEY=put-real-secret-key-here
DEBUG=True

ALLOWED_HOSTS=localhost,127.0.0.1,0.0.0.0
ALLOW_ALL_ORIGINS=True

DATABASE_ENGINE=django.db.backends.postgresql
DATABASE_NAME=ywjoyuqt
DATABASE_USER=ywjoyuqt
DATABASE_PASSWORD=8Vncv59WatsmssakqwooEq2GWiynsKco
DATABASE_HOST=kashin.db.elephantsql.com
DATABASE_PORT=5432

Migrate in order to move your tables from docker to elephant SQL

poetry add django-cors-headers

Add corsheaders to the top of MIDDLEWARE
"corsheaders.middleware.CorsMiddleware",

Change port to 8000

Create a key-pair
Download .pem file
Go to EC2 dashboard
Click on Instance ID
Click on Security
Click on security group
Edit inbound access rules - Allows port 8000 to be seen

Edit Inbound Rules
Custom TCP Rule
Port 8000
0.0.0.0/0
Save Rules

Click on Instance
Click on Connect
SSH Client
Follow instructions to log into AWS on your terminal/local computer
ssh -i "cookie-stand.pem" ec2-user@ec2-54-173-235-188.compute-1.amazonaws.com
ec2-user 54.173.235.188
sudo yum update
sudo yum install git
git clone repo from github'

Create custom folder
touch things_api_project/.env
nano things_api_project/.env

Copy and paste in everything from your .env
to close, shift-control-X
save to .env

Install Docker
sudo yum install -y docker

<https://stackabuse.com/deploying-django-applications-to-aws-ec2-with-docker/>
<https://testdriven.io/blog/django-docker-https-aws/>
<https://gist.github.com/npearce/6f3c7826c7499587f00957fee62f8ee9>
<https://docs.aws.amazon.com/AmazonECS/latest/developerguide/docker-basics.html>

Give user permission to run docker - check all the commands from video
sudo usermod -a -G docker ec2-user

(Get rid of the <> characters on the next line)
sudo curl -L "<https://github.com/docker/compose/releases/download/1.25.5/docker-compose>-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo service docker start
sudo chkconfig docker on
sudo chkconfig docker on
sudo rm /etc/localtime
sudo docker swarm init
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
sudo reboot

ssh back into ec2 instance then start the django app with
docker-compose up --build
add ec2 instance ip address to allowed hosts

to access django app use the ip address on the aws console for this instance + port 8000 and use http instead of https

<!-- For Safe Keeping -->
DATABASE_ENGINE=django.db.backends.postgresql
    # ENVIRONMENT=(str, "PRODUCTION"),
    # ALLOW_ALL_ORIGINS=(bool, False),
    # ALLOWED_HOSTS=(list, []),
    # ALLOWED_ORIGINS=(list, []),
    # DATABASE_ENGINE=(str, "django.db.backends.sqlite3"),
    # DATABASE_NAME=(str, BASE_DIR / "db.sqlite3"),
    # DATABASE_USER=(str, ""),
    # DATABASE_PASSWORD=(str, ""),
    # DATABASE_HOST=(str, ""),
    # DATABASE_PORT=(int, 5432),
