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
<div id="player"></div>

<script>
{% raw %}
  var playlistId = 'PL9bCSP6AmQJUUI8NgSC9cg201o3AkeD_V';
  var totalSongs = 75; // Update this to your current song count
  var randomStartPos = Math.floor(Math.random() * totalSongs);
  document.getElementById('player').innerHTML = '<iframe width="100%" height="450" src="https://www.youtube.com/embed/videoseries?list=' + playlistId + '&index=' + randomStartPos + '" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share; local-network-access" allowfullscreen></iframe>';
{% endraw %}
</script>
