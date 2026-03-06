---
layout: post
title: "Dance Songs by Various Artists"
date: 2026-03-02 09:00:00 -0800
categories: [Music]
---

# Hello!
This is a page dedicated to songs by various artists that I like. 
I am hosting this using my custom domain **miracleostrich.ca**.

### My Curated Playlist
{% raw %}

//<iframe width="100%" height="400" src="https://www.youtube.com/embed/videoseries?list=PL9bCSP6AmQJUUI8NgSC9cg201o3AkeD_V" title="YouTube video player" //frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share; local-network-access" //allowfullscreen></iframe>

<div id="player"></div>

<script>
  // 1. Your Playlist ID
  var playlistId = 'PL9bCSP6AmQJUUI8NgSC9cg201o3AkeD_V';
  
  // 2. How many songs are in your playlist? (Change this number)
  var totalSongs = 200; 
  
  // 3. Pick a random number between 0 and the total songs
  var randomStartPos = Math.floor(Math.random() * totalSongs);

  // 4. Create the iframe dynamically
  document.getElementById('player').innerHTML = '<iframe width="100%" height="450" src="https://www.youtube.com/embed/videoseries?list=' + playlistId + '&index=' + randomStartPos + '" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>';
</script>

{% endraw %}
---
