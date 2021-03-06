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
a django app. In our case we add the Ingredients related endpoints
- in the core app ad the test for the new model (git: d2cd614a50f30d25467988664625ff87e77557e7)
    - we test that our model is converted corectly to a string representation
- add the model
    - add the model and run the migrations (git: 21250b3dd5d9af184c7eae9008e34fbe0fa4db06)
    - `docker-compose run app sh -c "python manage.py makemigrations core"`
- register the model 
    - register the model (git: a1d2e1a9daefb648938bc444c813e7c35f44e3ef)
    - run the tests
        - `docker-compose run app sh -c "python manage.py test && flake8"`
- add tests for listing the ingredients (git: 6af380f18803915b5b736bde2a4653640ee90e07)
- implemented list ingredients (git: 954f6138de25ebe5082de63a3a9b45c67eb22e6f)
- add tests for creating ingredinets (git: 9f98a708adebaf9c2e20aa9b1a83fa46d2265650)
- implement create ingredients endpoint (git: 0939e4df3559239cb9f2eb123f8a007bd2742e3f)
