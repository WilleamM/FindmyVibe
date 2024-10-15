# API Specifications for FindmyVibe

## 1. User Management

### 1.1 User Information - `/users/signup` (POST)

Gets information about the user.

**Response:**

```json
[
    {
        "userId": "integer",
        "userName": "string",
        "email": "string",
        "password": "string",
        "genrePreferences": "string",
        "moodPreferences": "string",
        "playlists": ["string"], /* The list of playlists made and managed by user */
    }
]
```

### 1.2 User Search - `/users/{user_id}/search` (GET)

Allows for user to search for music based upon its artist, name, genre, and mood/vibe.

**Query Parameters:**

- `title` (optional): The name of the song.
- `artist` (optional): The artist of a song.
- `rating` (optional): Filters songs by rating.
- `year` (optional): Filters songs by year
- `album` (optional): The name of an album.
- `genre` (optional): Filters songs by genre.
- `mood` (optional): Filters songs by mood.

**Response:**

```json
[
    {
        "title": "string",
        "artist": "string",
        "rating": "integer",
        "album": "string",
        "genre": "string",
        "mood": "string",
    }
]
```

### 1.3 Update User Preferences - `/users/{userId}/update_preferences` (POST)

Updates the users preferences in certain genres and moods.

**Request:**

```json
[
    {
        "genrePreferences": "string",
        "moodPreferences": "string"
    }
]
```

**Response:**

```json
{
    "success": "boolean"
}
```


## 2. Playlists Management

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
    "success": "boolean"
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

## 3. Trending Page 

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

## 4. Song Recommendations

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
  
## 5. Albums

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

## 6. Songs

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
    "success": "boolean"
}
```

## 7. Catalog

### 7.1 Get Inventory Summary - `/catalog/` (GET)

Return a summary of current songs, albums, artists, and genres.

**Response:**
```json
[
    {
        "numberOfSongs": "integer",
        "numberOfAlbums": "integer",
        "numberOfArtists": "integer",
        "numberOfGenres": "integer"
    }
]
```

## 8. Admin Functions

### 8.1. Add a song - `/admin/songs` (POST)

Admins can add a new song to the catalog. An unique songId will be created and returned.

**Request:** 

```json
{
  "title": "string",
  "artist": "string",
  "genre": "string",
  "mood": "string",
  "releaseDate": [d,m,y] /* Day, month, year*/
  "rating": "number"
}
```

**Response:**

```json
{
    "songId":"integer"
}
```

### 8.2. Delete a song - `/admin/songs/{songId}` (POST)

Admin can delete a song from the catalog.

**Request:** 

```json
{
    "songId":"integer"
}
```

**Response:**

```json
{
    "success": "boolean"
}
```

### 8.3. Add a song to the Trending Page - `/admin/trending/songs` (POST)

Admins can manually a new song to the trending page. Note: Songs will automatically be put into the trending page when they reach a specific rating.

**Request:** 

```json
{
    "songId":"integer"
}
```

**Response:**

```json
{
    "success": "boolean"
}
```

### 8.4. Delete a song from the Trending Page - `/admin/trending/songs/{songId}` (POST)

Admin can manually delete a song from the trending page. Note: Songs will automatically be removed from the trending page if their rating goes under a specific threshold.

**Request:** 

```json
{
    "songId":"integer"
}
```

**Response:**

```json
{
    "success": "boolean"
}
```

