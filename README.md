# Deploy Django to Heroku procedure

I created this repo to remind myself later what steps to take in order to deploy my django apps to heroku with the 
 debugger turned off. And with a thousand pages out there with different ways to do this.
 This way worked for me. Using the Heroku CLI. The 1001 way out there! :-)
 
 ### Create App
 
This step can be done before or after the app's created locally
 ```
 1. Log into your Heroku account
 2. Click on the 'new' button and choose 'Create App'
 3. Choose an app name and region and click on 'create'
```


### Prepare the Django app for Heroku
```
1. Create a Procfile in the root file of your app with the wsgi config like in this repo
2. Create a runtime.txt file in the root file with your Python version
3. Install gunicorn "pip install gunicorn"
4. Install Whitenoise "pip install whitenoise"
5. Add 'whitenoise.middleware.WhiteNoiseMiddleware', to the settings file MIDDLEWARE right under   
   'django.middleware.security.SecurityMiddleware', 
6. Add STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles') to the settings file Also at the top "import os"
7. Set DEBUG = False
8. Create a requirements.txt file. I use "pip freeze > requirements.txt" 
```

### Add heroku repo to project
```
1. Go to and install the CLI https://devcenter.heroku.com/articles/heroku-cli
2. After installing the CLI run "heroku login"
3. Initialize git and add repo:
    - git init
    - heroku git:remote -a projectname
4. Push project to Heroku repo:
    - git add .
    - git commit -am "make it better"
    - git push heroku master
```


And that's about it... Hopefully this works fine. 

Jurgen























