# django-now-aws-example 
Deployment setup of ZEIT now for django with AWS (S3, RDS - postgres)
## [DEMO](https://django-now-aws.guandjoy.now.sh/)
### Django admin credentials:
login: admin <br/>
password: adminpass
### Acknowledgment
Based on @Agiliq [article](https://www.agiliq.com/blog/2019/02/django-zeit-now-serverless/) <br/>
But with @ardnt [now builder](https://github.com/ardnt/now-python-wsgi).

## Put own credentials to the `settings.py` file
### Database:
```python
# settings.py
...
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'django_now_aws_database', # dbname
        'USER': 'someuser', # master username
        'PASSWORD': 'somepass', # master password
        'HOST': 'django-now-aws.c7bqwefoebyj.eu-central-1.rds.amazonaws.com', # Endpoint
        'PORT': '5432',
    }
}
...
```
### Credentials. 
Create a new user and paste keys here. Don't forget to get proper region value [here](https://docs.aws.amazon.com/general/latest/gr/rande.html):
```python
# settings.py
...
# The AWS region to connect to.
AWS_REGION = "eu-central-1"

# The AWS access key to use.
AWS_ACCESS_KEY_ID = "AKILR1JGHBHFXA3BLO7M"

# The AWS secret access key to use.
AWS_SECRET_ACCESS_KEY = "TFZW3R2oPLRlV05K2JfEBiWE+oWS4duflTHKsm7X"
...
```
### Static `S3` service:
```python
# settings.py
...
S3_BUCKET = "name-of-your-s3-service" # Put the name of your S3 bucket here
...
```
