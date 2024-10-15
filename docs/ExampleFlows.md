Playlists
    Bob wants to create a playlist called "Road Trip" and add three songs to it. To do this, he:

    1) Starts by calling POST /playlists to create a new playlist with ID 1234:
    2) Then Bob calls POST /playlists/3001/songs/SONG_001 and passes in a songId that passes in a quantity of 1 to add the first song
    3) He makes another call to POST /playlists/3001/songs/SONG_002 and passes in a songId that passes in a quantity of 1 to add the second song
    4) He makes another call to POST /playlists/3001/songs/SONG_002 and passes in a songId that passes in a quantity of 1 to add the third song

    At the end of this sequence, Bob has successfully created a playlist called "Road Trip" and added three songs


Trending
    Bob wants to know the top 5 trending songs

    1) Bob starts by calling GET /trending to fetch the list of top trending songs and passes the integer 5 to recive the top 5 trending songs

    This return the top number of 5 trending songs ()