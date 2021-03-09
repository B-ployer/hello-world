How to deploy mugshots.com on your PC?
--------------------------------------

First of all you need to clone this repository:
`git clone https://git.inetss.com/mugshots/mugshots.git`

Then go to mugshots/venv folder and uncomment(delite '#') string from the end of
requirements.txt file:
`# setuptools==41.2.0`

Run shell-script
`mugshots/venv/install.sh`

Wait while it finish and activate virtual environment for OSX and Linux with
`source venv/bin/activate`
or for Windows with
`venv/Scripts/activate`

Then you need to rename files in *mugshots/src/mugshots*
*settings\_local.py.sample* to *settings\_local.py*,
*settings\_live.py* to *settings\_live.py.sample*,
*settings\_api\_live.py* to *settings\_api\_live.py.sample*

Connect the django with db server. For that you need to add
```
'HOST': 'dev2',      # put here host of your db server
'NAME': 'minisites', # your db name
'USER': 'leonid',    # your username
'PASSWORD': 'lkj',   # your password
```
to *settings\_local.py* into
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql_psycopg2', 
        # put right here
    }
}
