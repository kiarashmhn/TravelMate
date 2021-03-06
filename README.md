# [Travel Mate](https://github.com/project-travel-mate/Travel-Mate) Server (Project: Nomad)
[![Build Status](https://travis-ci.org/project-travel-mate/server.svg?branch=master)](https://travis-ci.org/project-travel-mate/server)
> [Django 2.0](https://docs.djangoproject.com/en/2.0/releases/2.0/) server for Travel Mate

## Contribute
+ For new feature request in the app, open a [new feature request](https://github.com/project-travel-mate/Travel-Mate/issues) on the main repository
+ For reporting bug in existing APIs, open a [new issue](https://github.com/project-travel-mate/server/issues) on this repository

## Local setup instructions
+ Clone the project from source
```shell
git clone https://github.com/project-travel-mate/server && cd server
```
+ Setup virtual environment
```shell
pip install virtualenv
virtualenv venv --python=python3.6
source venv/bin/activate
```
+ Install all dependencies
```shell
pip install -r requirements.txt
```
+ Setup Postgres database and user
*(assuming Postgres is already installed on system; See [postgres setup instructions](http://postgresguide.com/setup/install.html))*

For Linux-
```
$ sudo -u postgres createuser nomad
$ sudo -u postgres createdb nomad

$ sudo -u postgres psql
psql=# alter user nomad with encrypted password 'pass';
psql=# grant all privileges on database nomad to nomad ;
psql=# ALTER USER nomad CREATEDB ;
```
For Windows-
```
The complete path>psql -U postgres -h localhost
Password:The one given during setup of postgres.
postgres=# create database nomad;
postgres=# create user nomad;
postgres=# alter user nomad with encrypted password 'pass';
postgres=# grant all privileges on database nomad to nomad ;
postgres=# ALTER USER nomad CREATEDB ;
```

+ Database migrations
```
python manage.py makemigrations
python manage.py migrate
```

+ Run Tests
```
python manage.py test
```

+ Finally! Run server
```
python manage.py runserver
```

Open [localhost:8000](http://localhost:8000)