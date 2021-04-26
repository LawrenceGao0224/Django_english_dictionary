# Django english dictionary

This project is similar to Django_urlshorter (https://github.com/LawrenceGao0224/Django_urlshorter).  
I use pydictionary package in this project.  
And deploy on the heroku.  
Demo : https://englishdictionary123.herokuapp.com/. 

## The following code is in Django_english_dictionary/dictionary/views.py  
It shows how I use the dictionary!  
```python
def word(request):
    search = request.GET.get('search')
    dictionary = PyDictionary()
    meaning = dictionary.meaning(search)
    synonyms = dictionary.synonym(search)
    antonyms = dictionary.antonym(search)
    context = {
        'meaning' : meaning,
        'synonyms' : synonyms,
        'antonyms' : antonyms
    }
    return render(request, 'word.html', context)
```

## Deploy on heroku

1. ```pip install gunicorn django-heroku```
2. Add runtime.txt file at root , type ```python-3.9.1```
3. Add Profile file at root, type ```web gunicorn englishdictionary.wsgi:application --log-file -```
4. ```pip freeze > requirements.txt```
5. Go to setting.py, type ```import django_heroku```, modify ```ALLOW_HOST = ['*']```, add at bottom ```django_heroku.setting(locals())```
6. ```heroku login```
7. ```heroku create englishdictionary123```
9.  ```git init```
10.  ```git remote -v```
11.  ```git remote add heroku 網址```
12.  ```git add .```
13.  ```git commit -m 'first'```
14.  ```git push heroku master```
15. Browse the website   
