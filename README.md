# Database-1

**Create a database called movies.**

```
test> use movies
switched to db movies
```

**2) Create a collection called moviedetails.**

```
movies> db.createCollection("moviedetails")
{ ok: 1 }

```

**3) Create above 5 movie documents into a moviedetails collection.**

```
 db.MovieDetails.insertMany([
...     {"Movie-Title": "Jurassic Park", "Genre": "Adventure", "Director": "Steven Spielberg", "Release Year": "1993"},
...     {"Movie-Title": "Forrest Gump", "Genre": "Drama", "Director": "Robert Zemeckis", "Release Year": "1994"},
...     {"Movie-Title": "Titanic", "Genre": "Romance", "Director": "James Cameron", "Release Year": "1997"},
...     {"Movie-Title": "The Dark Knight", "Genre": "Action", "Director": "Christopher Nolan", "Release Year": "2008"},
...     {"Movie-Title": "Avatar", "Genre": "Science Fiction", "Director": "James Cameron", "Release Year": "2009"}
... ])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("654d190df70a169d5b091ef5"),
    '1': ObjectId("654d190df70a169d5b091ef6"),
    '2': ObjectId("654d190df70a169d5b091ef7"),
    '3': ObjectId("654d190df70a169d5b091ef8"),
    '4': ObjectId("654d190df70a169d5b091ef9")
  }
}

```

**4) List all documents created.**

```

db.MovieDetails.find()
[
  {
    _id: ObjectId("654d190df70a169d5b091ef5"),
    'Movie-Title': 'Jurassic Park',
    Genre: 'Adventure',
    Director: 'Steven Spielberg',
    'Release Year': '1993'
  },
  {
    _id: ObjectId("654d190df70a169d5b091ef6"),
    'Movie-Title': 'Forrest Gump',
    Genre: 'Drama',
    Director: 'Robert Zemeckis',
    'Release Year': '1994'
  },
  {
    _id: ObjectId("654d190df70a169d5b091ef7"),
    'Movie-Title': 'Titanic',
    Genre: 'Romance',
    Director: 'James Cameron',
    'Release Year': '1997'
  },
  {
    _id: ObjectId("654d190df70a169d5b091ef8"),
    'Movie-Title': 'The Dark Knight',
    Genre: 'Action',
    Director: 'Christopher Nolan',
    'Release Year': '2008'
  },
  {
    _id: ObjectId("654d190df70a169d5b091ef9"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]


```

**5)List James Cameron’s movies.**


```

db.MovieDetails.find({ "Director":"James Cameron" })
[
  {
    _id: ObjectId("654d190df70a169d5b091ef7"),
    'Movie-Title': 'Titanic',
    Genre: 'Romance',
    Director: 'James Cameron',
    'Release Year': '1997'
  },
  {
    _id: ObjectId("654d190df70a169d5b091ef9"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]

```

**6)List  James Cameron’s movies released in 2009.**


```

db.MovieDetails.find({ "Release Year":"2009" })
[
  {
    _id: ObjectId("654d190df70a169d5b091ef9"),
    'Movie-Title': 'Avatar',
    Genre: 'Science Fiction',
    Director: 'James Cameron',
    'Release Year': '2009'
  }
]

```

**7)Delete the movie which you don’t like.**

```

MovieDetails.remove({ "Movie-Title": "Forrest Gump" })
{ acknowledged: true, deletedCount: 1 }


```

**8)Add the movie which is your favourite.**

```

db.MovieDetails.insertOne({ "Movie-Title": "Sita-Ramam" })
{
  acknowledged: true,
  insertedId: ObjectId("654d1f34f70a169d5b091efa")
}

```

**9)List movie Directed  by Christopher Nolan in 1994.**

```

db.MovieDetails.find({ "Release Year":"1994","Director": "Christopher Nolan" })

```

**10)  List out the Director’s Name in your document.**

```
db.MovieDetails.distinct("Director")
[ 'Christopher Nolan', 'James Cameron', 'Steven Spielberg' ]

```
 






