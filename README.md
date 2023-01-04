# Django on Render
This is a simple project developed using Django framework and it contains the settings required for successfull deployment of Django projects on Render.
## Setup

Below are the steps to follow to setup this project locally on your machine;

* Clone the project locally on your machine using **git clone**
* Create and activate a new virtual enviroment.
* To install dependencies run
```
pip install -r requirements.txt
```
* Go to the projects setting.py file and remove the comments in the database section.

* In your terminal execute the following commands to makemigrations and migrate to database

```
python manage.py makemigrations
python manage.py migrate
```

## Using PostgreSQL Database

Comment the database section out completely and paste the follwing lines of code beneath it.

```
DATABASES = {  
    'default': {  
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'database_name',  
        'USER': 'database_user',  
        'PASSWORD': 'Database_password',  
        'HOST': 'database_host.oregon-postgres.render.com',  
        'PORT': '5432',
    }  
}
```
#build command

```
./build.sh
```

##start command

```
gunicorn project_name.wsgi:application
```

## Using Default Database

Comment the database section out completely and paste the follwing lines of code beneath it.
```

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
}
```


## Using No Database

Comment the database section out completely and paste the follwing lines of code beneath it.
```

DATABASES = {}
```
