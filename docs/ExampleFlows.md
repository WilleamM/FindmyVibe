
## 1. User Creating a Playlist and Adding Songs Example Flow

John, a music lover, has just joined FindmyVibe. He's excited to explore new music and create a playlist filled with his favorite upbeat rock songs. First, he signs up for the service and provides his preferences. Then, he searches for songs by his favorite genre and mood, creates a playlist, and adds songs to his playlist.

1. John signs up for FindmyVibe by calling `POST /users/signup` and recieves a userId of 1.
**Request**
```json
{
  "userName": "JohnDoe",
  "email": "john@example.com",
  "password": "password123",
  "genrePreferences": "rock",
  "moodPreferences": "upbeat"
}
```
**Response**
```json
{
  "userId": 123,
}
```

2. John then searches for songs by the rock category and an upbeat mood by calling `GET /users/123/search?genre=rock&mood=upbeat`.

**Response**
```json
[
  {
    "title": "Thunderstruck",
    "artist": "AC/DC",
    "rating": 5,
    "album": "The Razors Edge",
    "genre": "rock",
    "mood": "upbeat"
  },
  {
    "title": "Smells Like Teen Spirit",
    "artist": "Nirvana",
    "rating": 5,
    "album": "Nevermind",
    "genre": "rock",
    "mood": "upbeat"
  }
]
```

3. John creates a new playlist called "Rock Playlist" by calling `POST /playlists`.

**Request**
```json
{
  "userId": 123,
  "name": "Rock Playlist",
  "description": "Upbeat rock songs"
}
```

**Response**
```json
{
  "playlistId": 456,
  "message": "Playlist created successfully"
}
```
4. John then adds a new song to his playlist by calling `POST /playlist/456/songs`.

**Request**
```json
{
  "playlistId": 456,
  "songId": 1 /* Thunderstruck */
}
```

**Response**
```json
{
  "success": true
}
```
John can now enjoy his new playlist that consists of one song!




