# mysite
Django Personal

#criando ambeiente OBS: entrar nas pastinhas mysite com CD após criação
python -m venv env
pip install Django
django-admin startproject mysite
python manage.py startapp blog
>va no setting.py e em INSTALLED_APPS e insira no final 'blog',
python manage.py migrate
python manage.py runserver

#
>criar uma pasta models e um arquivo em branco com nome __ini__.py
>criar um arquivo nesta pasta, exemplo: post.py. Código no arquivo
>va no admin.py e insira o código: from .models import Post
>va no arquivo criado __init__.py e insera o código: from .post import Post
python manage.py makemigrations
python manage.py migrate

#Criar Usuario
python manage.py createsuperuser

#Comando para entrar na Shell
python manage.py shell
from blog.models.post import Post
from django.contrib.auth.models import User
user = User.objects.filter.all()
user = User.objects.filter()
user
user[0].username
user = User.objects.get(username=ferna)
type(user)
user = User.objects.get(username='ferna')
Post.objects.create(title='first post blog', author=user, content='my first blog post content')
post_from_ferna = Post.objects.get(author=user)
post_from_ferna
dir(post_from_ferna)
dir(post_from_ferna).status
dir(post_from_ferna).title
dir(post_from_ferna).content
dir(post_from_ferna).author

#criando segundo post
Post.objects.create(title='second post blog', slug='second', author=user, content='my second blog post content')
post_from_ferna = Post.objects.filter(author=user)
post_from_ferna
post_from_ferna[0].slug

#TESTES
pip install pytest-django
pip install Faker
pip install factory_boy
pip install -U pytest
>criação de pastas e arquivos como factory.py e init e demais, pasta test e etc
pytest
pip freeze > requirements.txt

#DJANGO VIEWS
>Arquivos criado nas pastas views em tests e blogs