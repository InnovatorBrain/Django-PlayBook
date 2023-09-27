## Running Background-Tasks:
Message Borkers:
- Redis (in memory data store)
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
Because it does not support its latest version on window so intall linux subsystem for celery
```python
pip install celery
pipenv install celery
```
create a file celery.py in project directory



