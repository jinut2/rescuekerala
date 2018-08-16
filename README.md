# rescuekerala
Website for coordinating rehabilitation of people affected in the 2018 Kerala Floods

We're so glad to see the PRs, will merge after releasing critical features
=======
# Kerala Rescue

Website for coordinating rehabilitation of people affected in the 2018 Kerala Floods

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

You will need to have following softwares in your system

- Python 3
- Postgres
- git

### Installing

Setting up development environment

create database and user in postgres for kerala rescue and give privileges

```
psql user=postgres
Password: 
psql (10.4 (Ubuntu 10.4-0ubuntu0.18.04))
Type "help" for help.

postgres=# CREATE DATABASE rescuekerala;
CREATE DATABASE
postgres=# CREATE USER rescueuser WITH PASSWORD 'password';
CREATE ROLE
postgres=# GRANT ALL PRIVILEGES ON DATABASE rescuekerala TO rescueuser;
GRANT
postgres=# \q

```
Clone the repo
```
git clone https://github.com/IEEEKeralaSection/rescuekerala.git
cd rescuekerala
```

Copy sample environment file and configure it as per your local settings

```
cp .env.example .env
```

If you cant copy the environment or is facing difficulty in starting the server , Copy the settings file from
https://github.com/vigneshhari/keralarescue_test_settings for local testing

Install dependencies [help on pipenv](https://docs.pipenv.org/basics/#example-pipenv-workflow)

```
pipenv install
```

Activate virtualenv

```
pipenv shell
```

Run Database migrations

```
python3 manage.py migrate
```

Setup staticfiles
```
python3 manage.py collectstatic
```

Run the server

```
python3 manage.py runserver
```
Now open localhost:8000 in the browser
