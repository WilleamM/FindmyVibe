# API Specifications for FindmyVibe

## 1. User Management (Juan)

## 2. Playlists Management (Zoila)

### 2.1. Create Playlist - `/playlists` (POST)

Create a playlist with given information, returns playlistId.

**Request:**
```json
{
    "userId": "integer",
    "name": "string",
    "description": "string",
}
```

**Response:**
```json
{
    "playlistId": "integer",
    "message": "string"
}
```

### 2.2. Add Song to Playlist - `/playlist/{playlistId}/songs` (POST)

Add a song to the playlist.

**Request:**
```json
{
    "playlistId": "integer",
    "songId": "integer"
}
```

**Response:**
```json
[
  {
      "message": "string"
  }
]
```

### 2.3. View Playlist - `/playlist/{playlistId}/songs` (GET)

Add a song to the playlist.

**Request:**
```json
{
    "playlistId": "integer",
}
```

**Response:**
```json
[
  {
     "playlistId": "integer",
      "name": "string",
      "description": "string",
      "songs": [
                  {
                    "songId": "string",
                    "title": "string",
                    "artist": "string",
                    "genre": "string",
                    "mood": "string",
                    "releaseDate": [d,m,y] /* Day, month, year*/
                    "rating": "number"
                  }
                ] /* List of songs in the playlist*/
  }
]
```

## 3. Trending Page (Zoila)

### 3.1. Get Trending List - `/trending` (GET)

Fetches a list of a specified amount of songs in the trending page.

**Response:**
```json
{
    "num_songs": "integer"
    "trending_songs": [
                          {
                            "songId": "string",
                            "title": "string",
                            "artist": "string",
                            "genre": "string",
                            "mood": "string",
                            "releaseDate": [d,m,y] /* Day, month, year*/
                            "rating": "number"
                          }
                      ] /* List of songs in the trending page*/
}
```

## 4. Song Recommendations(Will)

### 4.1. Get Song Recommendations - `/songs/recommendations` (GET)

Get the song recommendations based on user preferences or the genre and mood of the given playlist.

**Response:**

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

Get the details of a specific album including songs, artist, and genres within the album.

**Response:**

```json
{
  "albumId": "string",
  "title": "string",
  "artist": "string",
  "songs": [ ... ],
  "genre": "string",
  "releaseDate": [d,m,y] /* Day, month, year*/
}
```

## 6. Songs (Will)

### 6.1. Get Song - `/songs/{songId}` (GET)

Fetch detailed information about a specific song.

**Response:**

```json
{
  "songId": "string",
  "title": "string",
  "artist": "string",
  "genre": "string",
  "mood": "string",
  "releaseDate": [d,m,y] /* Day, month, year*/
  "rating": "number"
}
```

### 6.1 Rate Song - `/songs/{songId]/rate` (POST)

Rate a specific song given the Song Id.

**Request:**

```json
{
  "rating":"integer"
}
```

**Response:**

```json
{
  "message': "string"
}
```

## 7. Catalog (Juan)
## 8. Admin Functions

