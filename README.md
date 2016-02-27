# tmdb
Python wrapper for The Movie Database (TMDb) API.

To use this wrapper you will need to obtain an API key from TMDB. Register an account here:
https://www.themoviedb.org/account/signup

Check out the API documentation here: 
https://docs.themoviedb.apiary.io

### Examples

Get a list of popular movies.

```python

from TMDb import TMDb
tmdb = TMDb(api_key="your-api-key", debug=False, lang="en")

popular = tmdb.popular()

for movie in popular:
    print movie.id()
    print movie.title()
    print movie.overview()
    print movie.poster()
            
```
Search for a movie by name.

```python
search = tmdb.search('Mad Max')

for movie in search:
    print movie.id()
    print movie.title()
    print movie.overview()
    print movie.poster()
    print movie.vote_average()
```

Get a list of similar movies for a given movie ID.

```python
similar = tmdb.similar(777)

for result in similar:
    print result.title()
    print result.overview()
```

Search for a TV show by name.

```python
show = tmdb.search_tv('Breaking Bad')

for result in show:
    print result.name()
    print result.overview()
```

Get a list of similar TV shows for a given TV Show ID.

```python
similar = tmdb.similar_shows(1396)

for show in similar:
    print show.name()
    print show.overview()
```

Get actor information for a given ID.

```python
person = tmdb.get_person(12)

print person.name()
print person.biography()
```

### Supported Methods

#### Movies
- **/movie/latest** 
- **/movie/now_playing**
- **/movie/top_rated**
- **/movie/upcoming**
- **/movie/id**
- **/movie/id/similar**

#### TV

- **/tv/id**
- **/tv/latest**
- **/tv/id/similar** 
- **/tv/top_rated**
- **/tv/popular**

#### People

- **/person/id**

#### Search

- **/search/movie**
- **/search/tv**
- **/search/person**