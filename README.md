# Django english dictionary

This project is similar to Django_urlshorter (https://github.com/LawrenceGao0224/Django_urlshorter).  
I use pydictionary package in this project.  
And deploy on the heroku.  
Demo : https://englishdictionary123.herokuapp.com/. 

The following code is in Django_english_dictionary/dictionary/views.py  
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
