# API Specifications for FindmyVibe
## 1. User Management (Juan)
## 2. Playlists Management (Zoila)
## 3. Trending Page (Zoila)


## 4. Song Recommendations(Will)

### 4.1. Get Song Recommendations - `/songs/recommendations` (GET)

Get the song recommendations based on user preferences or the genre and mood of the given playlist.

**Response**

```json
[
  {
    "songId": "string",
    "title": "string",
    "artist": "string",
    "releaseDate": [d,m,y] /* Day, month, year*/
    "genre": "string",
    "mood": "string",
    "rating": "integer"
  }
]
```
  
## 5. Albums (Will)

### 5.1. Get Album - `/albums/{albumId}` (GET)

Get the details of a specific album including songs, artist, and genres within the album

**Response**

```json
[
  {
    "albumId": "string",
    "title": "string",
    "artist": "string",
    "songs": [ ... ],
    "genre": "string",
    "releaseDate": [d,m,y] /* Day, month, year*/
  }
]
```

## 6. Songs (Will)

### 6.1. Get Song - `/songs/{songId}` (GET)

Fetch detailed information about a specific song

**Response**

```json
[
  {
    "songId": "string",
    "title": "string",
    "artist": "string",
    "genre": "string",
    "mood": "string",
    "releaseDate": [d,m,y] /* Day, month, year*/
    "rating": "number"
  }

]
```

### 6.1 Rate Song - `/songs/{songId]/rate` (POST)

Rate a specific song given the Song Id.

**Request**

```json
[
  {
    "rating":"integer"
  }
]
```



## 5. Albums (Will)
## 6. Songs (Will)
## 7. Catalog (Juan)
## 8. Admin Functions

