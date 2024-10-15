Playlists

    1) Create Playlist - POST /playlists
        User creates the initial start to the playlist
        
        Request: {
                    "userId": "12345",
                    "name": "Chill Vibes",
                    "description": "Songs to relax and unwind",
                }

        Response:{
                    "playlistId": "98765",
                    "message": "Playlist created successfully"
                }


    2) Add Song to Playlist - POST /playlists/{playlist_id}/songs
        User adds song to the playlist
        
        Request: {
                    "playlistId": "98765",
                    "songId": "54321"
                }

        Response: {
                    "message": "song successfully added"
                }

    3) View Playlist - GET /playlists/{playlist_id}
        Allows user to retrive an existing playlist

        Request: {
                    "playlistId": "333"
                }

        Response: {
                    "playlistId": "98765",
                    "name": "Chill Vibes",
                    "description": "Songs to relax and unwind",
                    "songs": [
                        {
                        "songId": "54321",
                        "title": "Lo-fi Beats",
                        "artist": "DJ Cool",
                        }
                    ]
                    }


Trending

    1) Get trending list - GET /trending/
        Returns a list of current top trending songs

        Response: {
                "trending_songs": [
                    {
                    "songId": "12345",
                    "title": "Hit Song 1",
                    "artist": "Famous Artist",
                    "genre": "Famous Artist",
                    "mood": "sad",
                    "rating": 4.8
                    },
                    {
                    "songId": "67890",
                    "title": "Hit Song 2",
                    "artist": "Popular Band",
                    "genre": "rock",
                    "mood": "hype",
                    "rating": 4.7
                    }
                ]
                }