# hawkling-api

A minimal authenticated Django API for HawkScan authentication testing.

## Running hawkling-api

### Prerequisites
This app has been tested with Python 3.9.1 To install Python module prerequisites, run:
```shell
$ cd hawkling-api
$ pip3 install -r requirements.txt
```


Create an environment file for storing your Django secret key
```shell
$ cd hawklingAPI/hawlingAPI/hawklingAPI
$ touch .env
$ echo DJANGO_KEY=$(python -c "import secrets; print(secrets.token_urlsafe())") >> .env
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
|     GET    |        kaakaww/               |     protected     |       Requires Bearer token to display greeting         |


### Request Credentials
- username: admin
- password: adminpassword