User Stories

  1.) As a user, I want to create and manage playlists, so that I can organize my favorite songs for different moods or occasions.
  
  2.) As a music enthusiast, I want to discover new songs based on my favorite genres, so that I can expand my music library.

  3.) As a user, I want to search for music by artist, song name, genre, and mood/vibe, so that I can quickly find specific tracks.

  4.) As a user, I want to see a trending page that highlights popular songs, so that I can stay updated with current music trends.

  5.) As a user, I want to add songs to my playlists directly from the recommendation or search results, so that I can curate my playlists efficiently.

  6.) As an open-minded music fan, I want to listen to random songs from anywhere so that I can expand my music knowledge.

  7.) As a user, I want to update my account settings, including my preferences for music genres and moods, so that I can personalize my experience.
  
  8.) As a fan of this certain album, I want to listen to the other songs of the album to get the full experience of the album.

  9.) As an admin, I want to cater the trending page in order to include the most highly reviewed and listened to music.

  10.) As an admin, I want to monitor user activity and engagement on the platform, so that I can identify trends and improve the user experience.
 
  11.)As an admin, I want to update music catalog information, including adding new songs and genres, so that users have access to the latest music offerings.

  12.)As an admin, I want to analyze song ratings and popularity metrics, so that I can provide insights and recommendations for the music catalog.

Exceptions

  1.) Exception: User searches for rating out of range
        Tell user to enter rating in valid range.
  
  2.) Exception: User searches for song not on recommendation list
        Tell user to enter a different song name.
        
  3.) Exception: User searches for genre that no songs have
        Tell user to enter a different genre.

  4.) Exception: User searches for artist that has no songs on the list.
        Tell user artist not found. Enter another

  5.) Exception: User searches for range of years that don't contain songs.
        Tell user to enter a different range

  6.) Exception: User searches for range of years that are invalid.
        Tell user to enter a different range

  7.) Exception: User searches for album that doesn't exist in the list.
        Tell user to enter another album.

  8.) Exception: User tries to access age restricted music while not being of age.
        Tell user that they aren't allowed to see this content and should look for something else.

  9.) Exception: User sorts for songs with a language that doesn't exist.
        Tell user to enter a valid language.

  10.) Exception: User sorts for a language but no songs exist in the list.
        Tell user that no song was found, and search another language.

  11.) Exception: User enters an invalid song length to sort by.
        Tell user to enter a valid song length.

  12.) Exception: User enters a song length, but no songs are found.
        Tell user that no songs are found, enter a different length.


