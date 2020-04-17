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

### Start the stack
```
podman-compose up -d
```

### Bootstrap the Database
```
DATABASE_USERNAME=postgres DATABASE_PASSWORD=putthedbpasshere DATABASE=amari amari init
```
The password should match whats in the `docker-compose.yml`.

### Run API
```
python3 jamaica/app.py
```
