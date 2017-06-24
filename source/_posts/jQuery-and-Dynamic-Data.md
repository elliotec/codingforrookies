---
title: jQuery and Dynamic Data
date: 2017-01-01 17:29:29
---

#### Spotify Playlist Creator!

###### index.html

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Coding for Rookies Playlist Creator</title>
  </head>
  <body>
    <h1>Playlist Creator!</h1>
    <form>
      <input type="text" id="search">
      <button id="create">Create Playlist!</button>
    </form>
    <div id="results"></div>
    <script src="https://code.jquery.com/jquery-3.1.1.min.js"></script>
    <script src="app.js"></script>
  </body>
</html>
```

###### app.js
```javascript
$("#create").click(function(event){
  event.preventDefault();
  createPlaylist();
});
function createPlaylist() {
  var artistName = $("#search").val();
  getArtists(artistName);
  function getArtists(artist) {
    $.ajax({
      url: 'https://api.spotify.com/v1/search',
      data: {
        q: artist,
        type: 'artist'
      },
      success: function(response){
        var artistId = response.artists.items[0].id;
        getRelatedArtists(artistId);
      }
    });
  }
  function getRelatedArtists(id) {
    $.ajax({
      url: 'https://api.spotify.com/v1/artists/' + id + '/related-artists',
      success: function(response){
        var artists = response.artists;
        getTopTracks(artists);
      }
    });
  }
  function getTopTracks(artistsArray){
    $.each(artistsArray, function(index, artist){
      $.ajax({
        url: 'https://api.spotify.com/v1/artists/' + artist.id + '/top-tracks?country=US',
        success: function(response){
          var trackObj = response.tracks[0];
          console.log(trackObj);
          displayTrack(trackObj)
        }
      });
    });
  }
  function displayTrack(track){
    $("#results").append("<p><a href='" + track.href + "'>" + track.artists[0].name + " - " + track.name + "</a></p>");
  }
}
```
