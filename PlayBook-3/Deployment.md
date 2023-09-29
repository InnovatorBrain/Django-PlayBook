<a href="">
  <img align="center" src="https://img.shields.io/badge/Deployment%20|%20Django%20Appications-blue" alt="center">
</a>

## Hosting Options:
1. VPS
2. PaaS(recommended) Heroku, Google Cloud, MS Azure

## Getting Started with Heroku:
Create an account and open Heroku Cli to install, `heroku --version`, `heroku login`, 
## Creating a Heroku app:
```cmd
heroku create faizan-prod
```
copy the domain name from here
open prod.py and past it in array

## Setting Environment variables:
1. For @prod.py
For generating secret key djecrety.ir
```cmd
heroku config:set SECRET_KEY='past-here'
```
2. For setting prod
@wsgi.py
Here, we set the default value to "dev". There is no value for "production". Run the command below.
```cmd
heroku config:set DJANGO_SETTINGSMODULE = storefront.settings.prod
```
## Creating a Procfile:
Create a new file Procfile in root folder
This file instructs Heroku on how to launch the application.
```python
release: python manage.py migrate
# Start an application we need a web process
# web process by using gunicorn
web: gunicorn storefront.wsgi
worker: celery -A storefront worker
```
## Provisioning a MySQL Database:
Kindly access the cloud service provider database through Heroku/apps.base.


