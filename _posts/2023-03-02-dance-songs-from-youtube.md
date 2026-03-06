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

<script src="https://www.youtube.com/iframe_api"></script>
<script>
{% raw %}
  var player;
  function onYouTubeIframeAPIReady() {
    player = new YT.Player('player', {
      height: '450',
      width: '100%',
      playerVars: {
        listType: 'playlist',
        list: 'PL9bCSP6AmQJUUI8NgSC9cg201o3AkeD_V',
        loop: 1
      },
      events: {
        'onReady': onPlayerReady
      }
    });
  }

  function onPlayerReady(event) {
    // This is the magic line that scrambles the list
    event.target.setShuffle(true);
    
    // Optional: If you want it to start playing immediately, uncomment the line below
    // event.target.playVideo();
  }
{% endraw %}
</script>
