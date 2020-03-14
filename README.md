# CondGuai-Açu
Aplicação para gerenciar condominio do Edifício Colina do Guai-Açu

![Python application](https://github.com/jlplautz/CondGuai-Acu/workflows/Python%20application/badge.svg)
[![Updates](https://pyup.io/repos/github/jlplautz/CondGuai-Acu/shield.svg)](https://pyup.io/repos/github/jlplautz/CondGuai-Acu/)
[![Python 3](https://pyup.io/repos/github/jlplautz/CondGuai-Acu/python-3-shield.svg)](https://pyup.io/repos/github/jlplautz/CondGuai-Acu/)


<h1>Procedimento executado</h1>

name: Python application

on: [pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.8
      uses: actions/setup-python@v1
      with:
        python-version: 3.8
    - name: Install dependencies
      run: |
        pip install pipenv
        pipenv sync --dev
    - name: Link with flake8
      run: |
        pipenv run flake8 .
```
CondGuai-Acu $ tree
.
├── LICENSE
└── README.md

CondGuai-Acu $ pyenv versions
  system
* 3.8.0 (set by /home/plautz/.pyenv/version)
CondGuai-Acu $ pyenv local 3.8.0
CondGuai-Acu $ pyenv local
3.8.0
CondGuai-Acu $ pyenv global
3.8.0

CondGuai-Acu $ pipenv shell
Creating a virtualenv for this project…
Pipfile: /home/plautz/PycharmProjects/CondGuai-Acu/Pipfile
Using /home/plautz/.pyenv/versions/3.8.0/bin/python3.8 (3.8.0) to create virtualenv…
⠦ Creating virtual environment...Already using interpreter /home/plautz/.pyenv/versions/3.8.0/bin/python3.8
Using base prefix '/home/plautz/.pyenv/versions/3.8.0'
New python executable in /home/plautz/PycharmProjects/CondGuai-Acu/.venv/bin/python3.8
Also creating executable in /home/plautz/PycharmProjects/CondGuai-Acu/.venv/bin/python
Installing setuptools, pip, wheel...
done.
✔ Successfully created virtual environment! 
Virtualenv location: /home/plautz/PycharmProjects/CondGuai-Acu/.venv
Creating a Pipfile for this project…
Launching subshell in virtual environment…
 . /home/plautz/PycharmProjects/CondGuai-Acu/.venv/bin/activate
CondGuai-Acu $  . /home/plautz/PycharmProjects/CondGuai-Acu/.venv/bin/activate

(CondGuai-Acu) CondGuai-Acu $ pipenv lock --clear
Locking [dev-packages] dependencies…
Locking [packages] dependencies…
Updated Pipfile.lock (db4242)!

(CondGuai-Acu) CondGuai-Acu $ pipenv install --dev flake8
+--------------------------------------------------------+
criar o arquivo .flake8 na raiz do projeto
[flake8]
max-line-length = 120
exclude = .venv
+--------------------------------------------------------+
criar o arquivo .pyup.yml
requirements:
  - Pipfile
  - Pipfile.lock
+--------------------------------------------------------+
```

<b>Inserir no github o Simple workflow Actions</b>
```
name: Python application

on: [pull_request]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.8
      uses: actions/setup-python@v1
      with:
        python-version: 3.8
    - name: Install dependencies
      run: |
        pip install pipenv
        pipenv sync --dev
    - name: Link with flake8
      run: |
        pipenv run flake8 .
```

<b>Instalar lib django</b>
```
CondGuai-Acu $ pipenv install django
```

<b>Ferramentas basicas do Django (linha de comando)</b>
```
(CondGuai-Acu) CondGuai-Acu $ django-admin

Type 'django-admin help <subcommand>' for help on a specific subcommand.

Available subcommands:

[django]
    check
    compilemessages
    createcachetable
    dbshell
    diffsettings
    dumpdata
    flush
    inspectdb
    loaddata
    makemessages
    makemigrations
    migrate
    runserver
    sendtestemail
    shell
    showmigrations
    sqlflush
    sqlmigrate
    sqlsequencereset
    squashmigrations
    startapp
    startproject
    test
    testserver
Note that only Django core commands are listed as settings are not properly configured (error: Requested setting INSTALLED_APPS, but settings are not configured. You must either define the environment variable DJANGO_SETTINGS_MODULE or call settings.configure() before accessing settings.).

(CondGuai-Acu) CondGuai-Acu $ django-admin startproject GuaiAcu .
(CondGuai-Acu) CondGuai-Acu $ cd GuaiAcu/
(CondGuai-Acu) GuaiAcu $ tree
.
├── asgi.py
├── __init__.py
├── settings.py
├── urls.py
└── wsgi.py

(CondGuai-Acu) GuaiAcu $ mng runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 17 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.

March 14, 2020 - 22:21:26
Django version 3.0.4, using settings 'GuaiAcu.settings'
Starting development server at http://127.0.0.1:8000/
Quit the server with CONTROL-C.
```

<b>Instalar as libs pytest-cov e codecov</b>
```
(CondGuai-Acu) CondGuai-Acu $ pipenv install --dev  pytest-cov codecov
```