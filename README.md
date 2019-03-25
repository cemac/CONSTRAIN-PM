<div align="center">
<a href="https://www.cemac.leeds.ac.uk/">
  <img src="https://github.com/cemac/cemac_generic/blob/master/Images/cemac.png"></a>
  <br>
</div>
 <h1> <center> CONSTRAIN Project Management Database </center> </h1>

[![GitHub release](https://img.shields.io/badge/release-v.1.1-blue.svg)]()


:construction: TEST REPO for CONSTRAIN DEMO :construction:

## Requirements

Via Pip

-   pip3 >= 18.0
-   pipenv
-   autoenv
-   python3
-   python-libs
-   Flaskr
-   postgresql-10.4

or Via anaconda

- [anaconda (python3)](https://www.anaconda.com/download/)
- [heroku cli](https://devcenter.heroku.com/articles/heroku-cli)

_Individual python modules are managed in the pip lock file and installed as per installation instructions_

# Installation

-   `pipenv install --three`
- there after `pipenv shell`

**or**

-   `conda env create -f swift.yaml`
-   `conda activate swift` and thereafter to use

<hr>

## Usage

**first use**

-   `initdb -D ~/postgresql_data/`
-   `postgres -D ~/postgresql_data/ &`
-   assign:

```bash
  export  APP_SETTINGS='config.DevelopmentConfig'
  export SECRET_KEY='key'
  export ADMIN_PWD='chosen password'
  export DATABASE_URL="postgresql://localhost/DBname"
```

-   create database

```bash
createdb DBname
```

-   populate with

```bash
python populatePSQL.py
python manage.py db upgrade
```

-   run on localhost `python manage.py runserver`

**thereafter**

-   `pipenv shell` or `conda activate swift`
-   `postgres -D ~/postgresql_data/ &`
-   assign:

```bash
  export  APP_SETTINGS='config.DevelopmentConfig'
  export SECRET_KEY='key'
  export ADMIN_PWD='chosen password'
  export DATABASE_URL="postgresql://localhost/DBname"
```

-   run on localhost `python manage.py runserver`

<hr>

## Hosting

This app is currently hosted on [herokuapp](https://www.heroku.com/).

For example push changes and launch the app:

```bash
heroku login
git config heroku.remote heroku
git add -A
git commit -a -m'commit messgae'
git push heroku master
heroku run  -a swift-pm python manage.py db upgrade
```

or to populate the database:

```bash
heroku config:set DATABASE_URL="postgresql://localhost/DBNAME"
heroku run -a swift-pm python populatePSQL.py
```

<hr>

# Backups


<hr>

# Web Page

Information on the web page template.

## Flask

The web app is built using python flask and thus the html file must adhere to the flask formatting rules. Each page builds on layout.html.

## Styling

The styling for this webpage uses [BOOTSTRAP](https://getbootstrap.com/docs/3.3/)

### Custom features:

To customise the bootstrap css a text css file is loaded in after the bootstrap library static/styles/stylesheet.css

1.  Navbar

-   An additional div container is added to the nav bar in order to allow interaction with a text/css
-   stylesheet.css then contains an update to navbar-default

2.  Tables

-   For admin the tables are very long added scrolling with sticky headers

## Scripting

The following javascript libraries are loaded:

-   [jquery](https://api.jquery.com/jquery.ajax/)
-   [bootstrap javascript](https://getbootstrap.com/docs/3.3/javascript/)
-   A script is added to view.html to add in a select all check checkbox
-   A script has been added to redirect to https

## Static
