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

## 2. User Updating Genre And Mood Preference Example Flow

Gary comes to FindMyVibe because he wants to update his mood and genre preferences to ROCK and HAPPY so that he is recommended different music in hopes that he will feel better. 

Gary will do this by calling POST {userId}/update_preferences and performing the following actions:

1. Gary first gets his user id , which is 8295  
2. He then calls POST 8295/update_preferences, and puts for his genre preference ROCK and for mood preference HAPPY.
3. Finally, he calls GET /userInfo/8295 to confirm that his genre and mood preference have changed.

Gary listens to HAPPY ROCK music and now feels much better because of it. 

## 3. User Creating Playlist and Adding Songs Example Flow:

     Bob wants to create a playlist called "Road Trip" and add three songs to it. 
     
     1) He starts by calling POST /playlists to create a new playlist with ID 3001
     2) He then calls POST /playlists/3001/songs/SONG_001 and passes in a quantity of 1 and the songID to add the first song
     3) Once again calls POST /playlists/3001/songs/SONG_001 and passes in a quantity of 1 and the songID to add the second song
     4) Once again calls POST /playlists/3001/songs/SONG_001 and passes in a quantity of 1 and the songID to add the third song

     At the end of this sequence, Bob has successfully created a playlist called "Road Trip" and added three songs to it.

Trending:

    Bob wants to check the top 10 trending songs

    1) He starts by calling GET /trending to fetch the list of trending songs and passes 10 to get the top 10 trending songs

At the end of this sequence, Bob has successfully received the top 10 trending songs as a playlist
