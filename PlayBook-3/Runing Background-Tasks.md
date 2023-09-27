## Running Background Tasks:
Message Brokers:
- Redis (in-memory data store)
- RabbitMQ
## Installing Redis 
Install inside a docker container
```python
#while runing Docker
docker run -d -p 6379:6379 redis
#also run bellow to add as dependencies of project
pipenv install redis
#list of running cotainer
docker ps 
```
## Celery and Windows:
Because it does not support its latest version on window so install Linux subsystem for celery
```python
pip install celery
pipenv install celery
```
create a file celery.py in the project directory and run bellow task in project dir as well:
```python
@celery.py
import os 
from celery import Celery

os.environ.setdefault('DJANGO_SETTINGS_MODULE', 'storefront.settings')

celery = Celery('storefront')
celery.config_from_object('django.conf:settings', namespace='CELERY')
celery.autodiscover_tasks()

@settings.py
CELERY_BROKER_URL = 'redis://localhost:6379'

@__init___.py
from .celery import celery
#in terminal
celery -A storefront worker --loglevel=info
```

### Every time open three terminal windows:
```python
python manage.py runserver
docker run -p 6379:6379 redis
celery -A storefront worker
```
### Creating and executing tasks:

