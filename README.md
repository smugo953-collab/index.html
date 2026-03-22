# index.html<<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SAMU TV KENYA</title>
  <style>
    body { font-family: Arial, sans-serif; margin:0; background:#f2f2f2; color:#333; }
    header { background:#002147; color:white; text-align:center; padding:20px; }
    nav { text-align:center; margin:10px 0; }
    nav a { margin:0 10px; text-decoration:none; color:#002147; font-weight:bold; }
    h2 { text-align:center; margin-top:20px; }
    .section-title { margin-top:30px; font-size:1.2em; font-weight:bold; text-align:center; color:#002147; }
    .channel-grid { display:flex; flex-wrap:wrap; justify-content:center; gap:15px; margin-top:10px; }
    .channel { text-align:center; cursor:pointer; border:1px solid #ccc; padding:10px; border-radius:5px; background:white; transition: transform 0.2s; width:160px; }
    .channel:hover { transform: scale(1.05); border-color:#002147; }
    .channel img { border-radius:5px; width:150px; height:90px; object-fit:cover; }
    video { display:block; margin:20px auto; max-width:90%; border:2px solid #002147; border-radius:5px; }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <h1>SAMU TV KENYA</h1>
    <p>Watch Live Channels</p>
  </header>

  <!-- NAVIGATION -->
  <nav>
    <a href="#">Home</a>
    <a href="#">Live TV</a>
    <a href="#">Music</a>
    <a href="#">About</a>
  </nav>

  <!-- MUSIC-ONLY SECTION -->
  <h2 class="section-title">🎵 JAH MUGO ELIJAH MUSIC CHANNELS</h2>
  <div class="channel-grid">
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=JAH+MUGO+ELIJAH+1" alt="Music Channel 1">
      <br>Music 1
    </div>
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/sintel/hls/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=JAH+MUGO+ELIJAH+2" alt="Music Channel 2">
      <br>Music 2
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_001/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=JAH+MUGO+ELIJAH+3" alt="Music Channel 3">
      <br>Music 3
    </div>
  </div>

  <!-- LIVE TV DASHBOARD -->
  <h2 class="section-title">📺 SAMU TV LIVE CHANNELS</h2>
  <div class="channel-grid">
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/MI201109210084_1/m3u8s/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=News+1" alt="News 1">
      <br>News 1
    </div>
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/MI201109210084_1/m3u8s/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=News+2" alt="News 2">
      <br>News 2
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_002/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Originals+1" alt="Originals 1">
      <br>Originals 1
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_003/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Originals+2" alt="Originals 2">
      <br>Originals 2
    </div>
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/sintel/hls/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Culture+1" alt="Culture 1">
      <br>Culture 1
    </div>
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/sintel/hls/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Culture+2" alt="Culture 2">
      <br>Culture 2
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_004/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Documentary+1" alt="Documentary 1">
      <br>Documentary 1
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_005/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Documentary+2" alt="Documentary 2">
      <br>Documentary 2
    </div>
    <div class="channel" onclick="playChannel('https://bitdash-a.akamaihd.net/content/sintel/hls/playlist.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Extras+1" alt="Extras 1">
      <br>Extras 1
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_006/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Extras+2" alt="Extras 2">
      <br>Extras 2
    </div>
    <div class="channel" onclick="playChannel('https://test-streams.mux.dev/test_007/stream.m3u8')">
      <img src="https://via.placeholder.com/150x90.png?text=Extras+3" alt="Extras 3">
      <br>Extras 3
    </div>
  </div>

  <!-- MAIN VIDEO PLAYER -->
  <video id="video" controls autoplay></video>

  <!-- HLS SCRIPT -->
  <script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
  <script>
    function playChannel(link){
      var video = document.getElementById('video');
      if(Hls.isSupported()) {
        var hls = new Hls();
        hls.loadSource(link);
        hls.attachMedia(video);
      } else if(video.canPlayType('application/vnd.apple.mpegurl')) {
        video.src = link;
      }
      video.play();
    }
  </script>

</body>
</html>