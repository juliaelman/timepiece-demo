# timepiece-demo

A demo repo to display project level functionality for utilizing the [django-timepiece](https://github.com/caktus/django-timepiece) project.

## Installation

Before installing the demo, you'll need to have the following installed.

- [pyenv](https://github.com/yyuu/pyenv)
- [pyenvirtualenv](https://github.com/yyuu/pyenv-virtualenv)
- [pyenvvirtualenvwrapper](https://github.com/yyuu/pyenv-virtualenvwrapper)
- [Python 3.4.1](https://www.python.org/download/releases/3.4.1/)
- [Postgres.app](http://postgresapp.com/)

**NOTE: While some of these items are based on personal preference, it is the method I used and got working on my local dev.**

### Installing timepiece-demo

First off, let's create our local database. Make sure that you have Postgres.app turned on and configured accurately.

```sh
createdb timepiece
```

Let's grab that code! Download the `demo-timepiece` repo onto your local machine.

```sh
$ git clone [git url]
$ cd timepiece-demo
```

Create your virtual enviroment (virtualenv).

```sh
[demo] mkvirtualenv timepiece-venv
Using base prefix '../../.pyenv/versions/3.4.1'
New python executable in ../../.virtualenvs/timepice-venv/bin/python3.4
Also creating executable in /Users/juliaelman/.virtualenvs/demo-timepiece/bin/python
Installing setuptools, pip, wheel...done.
virtualenvwrapper.user_scripts creating ../../.virtualenvs/timepiece-venv/bin/predeactivate
virtualenvwrapper.user_scripts creating ../../.virtualenvs/timepiece-venv/bin/postdeactivate
virtualenvwrapper.user_scripts creating ../../.virtualenvs/timepiece-venv/bin/preactivate
virtualenvwrapper.user_scripts creating ../../.virtualenvs/timepiece-venv/bin/postactivate
virtualenvwrapper.user_scripts creating ../../.virtualenvs/timepiece-venv/bin/get_env_details
(timepiece-venv) [timepiece-demo] 
```

Your virtualenv should automatically be activated on initial creation. Now let's make sure your Python path is accurately set to read your projects folder path.

```sh
add2virtualenv .
```

With your environment all setup, let's install our the requirements.

```sh
pip install -r requirements.txt
```

Now you should have all of the pip installable applications ready for usage! Let's sync our database, add our migrations and create our super user:

```sh
cd demo
python manage.py syncdb
python manage.py migrate
```

You should now be able to run your local server, visit `http://127.0.0.1:8000/` in your favorite browser and see a login screen:

```sh
python manage.py runserver
Performing system checks...

System check identified no issues (0 silenced).
February 28, 2016 - 11:27:21
Django version 1.8.9, using settings 'demo.settings.local'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```
