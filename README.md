Havana
======

Podman/Docker app stack.

Requirements
------------
* Podman (or docker-compose)
* podman-compose (or docker-compose)
* Python 3 with pip & virtualenv (virtualenvwrapper is encouraged for easy setup)

Setup
-----

### Python Virtualenv
Ensure you have a venv based on python3.

```
mkvirtualenv amari -p python3
```

Install all requirements from this repo's `requirements.txt`.

```
pip install -r requirements.txt
```

In each repo directory of [barbados, england, jamaica]:
```
pip install -e .
```

Execution
---------

### Start the stack
From the Havana `docker-compose.yml`
```
podman-compose up -d
```

### Bootstrap the Database
```
DATABASE_USERNAME=postgres DATABASE_PASSWORD=putthedbpasshere DATABASE_NAME=amari amari init
```
The password should match whats in the `docker-compose.yml`. Edit it if you want to.

### Fill in the Tables
Ensure you're still in the virtualenv (it usually prefixes your shell).
```
amari import ingredients ../tortuga/ingredients/
amari import recipe ../tortuga/recipes/
```

### Run API
From the Jamaica repo:
```
python3 jamaica/app.py
```
