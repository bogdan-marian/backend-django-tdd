# bakend-django-tdd

some commands used in the project
```bash
docker build .
docker-compose build
docker-compose run app sh -c "django-admin.py startproject app ."
docker-compose run app sh -c "python manage.py test"
docker-compose run app sh -c "python manage.py test && flake8"
docker-compose run app sh -c "python manage.py startapp core"
docker-compose run app sh -c "python manage.py makemigrations core"
docker-compose up
docker-compose run app sh -c "python manage.py createsuperuser"
docker-compose run --rm app sh -c "python manage.py startapp user"
docker-compose run --rm app sh -c "python manage.py startapp recipe"
docker-compose run app sh -c "python manage.py makemigrations"
```

## to test in browser
[admin console](http://127.0.0.1:8000/admin/)
[home url](http://127.0.0.1:8000)
[create a user](http://127.0.0.1:8000/api/user/create/)
[get a valid token](http://127.0.0.1:8000/api/user/token/)
[update me](http://127.0.0.1:8000/api/user/me/)


## mod heder tips
To simulate authorization token in brower use [HodHeader](https://chrome.google.com/webstore/detail/modheader/idgpnmonknjnojddfkpgkljpfnnfcklj?hl=en) chrome plugin

example token
```javascript
{
    "token": "2c4659ee9830006bd524136457978d902582c1f9"
}
```

In ModHeader ad to header
```md
Request Header: `Authorization`
Value: `Token 2c4659ee9830006bd524136457978d902582c1f9`
```


## general flow for addin a model
This is a short step by step tutorial about how to add a new endpoint to 
a django app
- in the core app ad the test for the new model (git: )
    - we test that our model is converted corectly to a string representation

