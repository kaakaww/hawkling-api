# hawkling-api

A minimal authenticated Django API for HawkScan authentication testing.

## Running hawkling-api

### Prerequisites
This app has been tested with Python 3.9.1 To install Python module prerequisites, run:
```shell
$ cd hawkling-api
$ pip3 install -r requirements.txt
```

Generate Django Secret Key and copy value
```shell
$ cd hawklingAPI/hawklingAPI
$ python manage.py shell
>>> from django.core.management.utils import get_random_secret_key
>>> get_random_secret_key()
'randomly generated key value'
>>> exit()

Create an environment file for storing your Django secret key
```shell
$ cd hawklingAPI/
$ touch .env
$ echo DJANGO_KEY=VALUE_FROM_ABOVE >> .env
```

### Running Locally

To run the API service directly, run:
```shell
$ cd ..
$ python manage.py runserver
```

The API service will listen on 0.0.0.0 and port 8000. You can reach the app at [http://localhost:8000/](http://localhost:8000/).


### API Routes
| **Action** |            **Path**           |   **Route Type**  |                     **Details**                         |
|:----------:|:-----------------------------:|:-----------------:|:-------------------------------------------------------:|
|     GET    |             /                 |      public       |                 Hawkling API home                       |
|     POST   |          login/               |      public       |  Login accepts username/password and returns JWT token  |
|     GET    |        kaakaww/               |     protected     |       Requires JWT token to display greeting            |
