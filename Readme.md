#Django Basic Commands

pip install Django

create a virtualenv, activate

### Creating a Project
django-admin startproject ProjectName

ex:
    
    1) django-admin startproject mysite
    2) django-admin startproject polls

#Creating a DataBase(Migrate)

    python manage.py makemigrate polls
    python manage.py migrate

under the migrations folder it will create the histroy same as git

#Apps Settings
Go to projectfolder(Main) and in settings.py under INSTALLED_APPS add the app name

ex: 

        1) mysite->settings.py->INSTALLED_APPS->Polls

#Populating a Database
    python manage.py shell

Steps:

1) In the shell import the django 
        
        import django
2) django.setup()
3) from polls.models import Question, Choice
4) Question.objects.all()
5) from django.utils import timezone
6) q = Question(question_text = "What is your name", pub_date = timezone.now())
7) q.save()

###Creating a SuperUser

    python manage.py createsuperuser

### Run a server
    
    python manage.py runserver
Open this in a browser: http://127.0.0.1:8000/admin

###Making changes in admin
Open polls file, open admin.py file and modify the changes accordingly

### Playing around the URLS
In the mainproject folder i.e mysite urls.py add the path of the polls folder urls.py file

ex:

      path("polls/", include("polls.urls")),

And in the create a urls.py file, polls->urls.py
Add this line
   
      urlpatterns = [
      url('^$', views.index, name="index"),
      # 127.0.0.1/polls/
      ]

And in the views.py add the below code

      def index(request):
         return HttpResponse("Awesome  Job Guys")


visit the URL for viewing it in browser: http://127.0.0.1/polls/

### Setting up views
Go to views.py and add the code which is required

### Settings up templates
we can use jinja or DTL

