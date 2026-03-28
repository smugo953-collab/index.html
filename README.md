<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAMU TV KENYA</title>
<style>
/* Basic Styles */
body { font-family: Arial, sans-serif; margin:0; background:#f2f2f2; color:#333; }
header { background:#002147; color:#fff; text-align:center; padding:20px; font-size:24px; font-weight:bold; }
nav { background:#004080; text-align:center; padding:10px; }
nav a { color:#fff; margin:0 15px; text-decoration:none; font-weight:bold; }
.ticker { background:#000; color:#0ff; padding:8px; text-align:center; }
.live-container { position:relative; padding-top:56.25%; margin:20px 0; }
.live-container iframe { position:absolute; width:100%; height:100%; border:0; }
.controls { text-align:center; margin:10px; }
button { padding:10px 15px; margin:5px; background:red; color:#fff; border:none; border-radius:5px; cursor:pointer; }
.grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:10px; padding:10px; }
.grid iframe { width:100%; height:150px; border:0; }
footer { background:#002147; color:#fff; text-align:center; padding:15px; margin-top:20px; }

/* Floating WhatsApp & PayPal Buttons */
.floating-buttons { position: fixed; bottom: 20px; right: 20px; display:flex; flex-direction:column; gap:10px; z-index:999; }
.floating-buttons a { display:flex; align-items:center; justify-content:center; width:60px; height:60px; border-radius:50%; color:#fff; font-size:28px; text-decoration:none; box-shadow:0 4px 8px rgba(0,0,0,0.3); overflow:hidden; transition:0.3s; position:relative; }
.floating-buttons a span.label { position:absolute; right:100%; white-space:nowrap; background:#222; color:#fff; padding:8px 12px; border-radius:8px; opacity:0; pointer-events:none; transition:0.3s; font-size:14px; }
.floating-buttons a.whatsapp { background:#25D366; }
.floating-buttons a.paypal { background:#003087; }
.floating-buttons a:hover { width:auto; padding:0 20px 0 10px; }
.floating-buttons a:hover span.label { opacity:1; right:70px; }
</style>
</head>
<body>

<header>SAMU TV KENYA</header>

<nav>
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Privacy</a>
<a href="#">Terms</a>
</nav>

<div class="ticker">🔴 SAMU TV KENYA LIVE 24/7 | News • Music • Entertainment</div>

<div class="live-container">
  <iframe id="player" src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU&autoplay=1&mute=1" allowfullscreen></iframe>
</div>

<div class="controls">
  <button onclick="goFull()">Fullscreen</button>
  <button onclick="unmute()">Sound</button>
</div>

<h2 style="text-align:center;">🔥 Featured Videos</h2>
<div class="grid">
  <iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU" allowfullscreen></iframe>
  <iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU" allowfullscreen></iframe>
</div>

<footer>
© 2026 SAMU TV KENYA | Email: info@samutvkenya.co.ke
</footer>

<!-- Floating Buttons -->
<div class="floating-buttons">
  <a href="https://wa.me/254759821389" target="_blank" class="whatsapp" title="Chat on WhatsApp">
    💬 <span class="label">Chat on WhatsApp</span>
  </a>
  <a href="https://www.paypal.com/paypalme/smugo953" target="_blank" class="paypal" title="Pay with PayPal">
    💳 <span class="label">Pay with PayPal</span>
  </a>
</div>

<script>
function goFull(){
  let iframe=document.getElementById("player");
  if(iframe.requestFullscreen){ iframe.requestFullscreen(); }
}

function unmute(){
  let iframe=document.getElementById("player");
  iframe.src = iframe.src.replace("mute=1","mute=0");
}
</script>

</body><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAMU TV KENYA</title>

<!-- AdSense Script (replace with your real ID later) -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXXXXX"
crossorigin="anonymous"></script>

<style>
body{font-family:Arial,sans-serif;margin:0;background:#f2f2f2;color:#333}
header{background:#002147;color:#fff;text-align:center;padding:20px}
nav{background:#004080;text-align:center;padding:10px}
nav a{color:#fff;margin:0 15px;text-decoration:none;font-weight:bold}
.ticker{background:#000;color:#0ff;padding:8px;text-align:center}
.live-container{position:relative;padding-top:56.25%;margin:20px}
.live-container iframe{position:absolute;width:100%;height:100%;border:0}
.controls{text-align:center;margin:10px}
button{padding:10px;margin:5px;background:red;color:#fff;border:none;border-radius:5px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px;padding:10px}
.grid iframe{width:100%;height:150px;border:0}
footer{background:#002147;color:#fff;text-align:center;padding:15px;margin-top:20px}

/* Floating Buttons */
.floating-buttons{position:fixed;bottom:20px;right:20px;display:flex;flex-direction:column;gap:10px;z-index:999}
.floating-buttons a{display:flex;align-items:center;justify-content:center;width:60px;height:60px;border-radius:50%;color:#fff;font-size:28px;text-decoration:none;box-shadow:0 4px 8px rgba(0,0,0,0.3);overflow:hidden;transition:0.3s;position:relative}
.floating-buttons a span{position:absolute;right:100%;white-space:nowrap;background:#222;color:#fff;padding:8px 12px;border-radius:8px;opacity:0;transition:0.3s;font-size:14px}
.floating-buttons a:hover{width:auto;padding:0 20px 0 10px}
.floating-buttons a:hover span{opacity:1;right:70px}
.whatsapp{background:#25D366}
.paypal{background:#003087}
</style>
</head>

<body>

<header>SAMU TV KENYA</header>

<nav>
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Privacy</a>
<a href="#">Terms</a>
</nav>

<div class="ticker">🔴 SAMU TV KENYA LIVE 24/7 | News • Music • Entertainment</div>

<!-- 🔹 AdSense Top -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="1111111111"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<!-- Live Player -->
<div class="live-container">
<iframe id="player"
src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU&autoplay=1&mute=1"
allowfullscreen></iframe>
</div>

<div class="controls">
<button onclick="goFull()">Fullscreen</button>
<button onclick="unmute()">Sound</button>
</div>

<!-- 🔹 AdSense Middle -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="2222222222"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<h2 style="text-align:center">🔥 Featured Videos</h2>

<div class="grid">
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
</div>

<!-- 🔹 AdSense Bottom -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="3333333333"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<footer>
© 2026 SAMU TV KENYA | Email: info@samutvkenya.co.ke
</footer>

<!-- Floating Buttons -->
<div class="floating-buttons">
<a href="https://wa.me/254759821389" target="_blank" class="whatsapp">💬<span>Chat WhatsApp</span></a>
<a href="https://www.paypal.com/paypalme/smugo953" target="_blank" class="paypal">💳<span>Pay with PayPal</span></a>
</div>

<script>
function goFull(){
let iframe=document.getElementById("player");
if(iframe.requestFullscreen){iframe.requestFullscreen();}
}

function unmute(){
let iframe=document.getElementById("player");
iframe.src=iframe.src.replace("mute=1","mute=0");
}
</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAMU TV KENYA</title>

<!-- AdSense Script (replace with your real ID later) -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXXXXX"
crossorigin="anonymous"></script>

<style>
body{font-family:Arial,sans-serif;margin:0;background:#f2f2f2;color:#333}
header{background:#002147;color:#fff;text-align:center;padding:20px}
nav{background:#004080;text-align:center;padding:10px}
nav a{color:#fff;margin:0 15px;text-decoration:none;font-weight:bold}
.ticker{background:#000;color:#0ff;padding:8px;text-align:center}
.live-container{position:relative;padding-top:56.25%;margin:20px}
.live-container iframe{position:absolute;width:100%;height:100%;border:0}
.controls{text-align:center;margin:10px}
button{padding:10px;margin:5px;background:red;color:#fff;border:none;border-radius:5px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px;padding:10px}
.grid iframe{width:100%;height:150px;border:0}
footer{background:#002147;color:#fff;text-align:center;padding:15px;margin-top:20px}

/* Floating Buttons */
.floating-buttons{position:fixed;bottom:20px;right:20px;display:flex;flex-direction:column;gap:10px;z-index:999}
.floating-buttons a{display:flex;align-items:center;justify-content:center;width:60px;height:60px;border-radius:50%;color:#fff;font-size:28px;text-decoration:none;box-shadow:0 4px 8px rgba(0,0,0,0.3);overflow:hidden;transition:0.3s;position:relative}
.floating-buttons a span{position:absolute;right:100%;white-space:nowrap;background:#222;color:#fff;padding:8px 12px;border-radius:8px;opacity:0;transition:0.3s;font-size:14px}
.floating-buttons a:hover{width:auto;padding:0 20px 0 10px}
.floating-buttons a:hover span{opacity:1;right:70px}
.whatsapp{background:#25D366}
.paypal{background:#003087}
</style>
</head>

<body>

<header>SAMU TV KENYA</header>

<nav>
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Privacy</a>
<a href="#">Terms</a>
</nav>

<div class="ticker">🔴 SAMU TV KENYA LIVE 24/7 | News • Music • Entertainment</div>

<!-- 🔹 AdSense Top -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="1111111111"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<!-- Live Player -->
<div class="live-container">
<iframe id="player"
src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU&autoplay=1&mute=1"
allowfullscreen></iframe>
</div>

<div class="controls">
<button onclick="goFull()">Fullscreen</button>
<button onclick="unmute()">Sound</button>
</div>

<!-- 🔹 AdSense Middle -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="2222222222"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<h2 style="text-align:center">🔥 Featured Videos</h2>

<div class="grid">
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
</div>

<!-- 🔹 AdSense Bottom -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="3333333333"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<footer>
© 2026 SAMU TV KENYA | Email: info@samutvkenya.co.ke
</footer>

<!-- Floating Buttons -->
<div class="floating-buttons">
<a href="https://wa.me/254759821389" target="_blank" class="whatsapp">💬<span>Chat WhatsApp</span></a>
<a href="https://www.paypal.com/paypalme/smugo953" target="_blank" class="paypal">💳<span>Pay with PayPal</span></a>
</div>

<script>
function goFull(){
let iframe=document.getElementById("player");
if(iframe.requestFullscreen){iframe.requestFullscreen();}
}

function unmute(){
let iframe=document.getElementById("player");
iframe.src=iframe.src.replace("mute=1","mute=0");
}
</script>

</body>
</html><!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAMU TV KENYA</title>

<!-- AdSense Script (replace with your real ID later) -->
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-XXXXXXXXXXXXXXXX"
crossorigin="anonymous"></script>

<style>
body{font-family:Arial,sans-serif;margin:0;background:#f2f2f2;color:#333}
header{background:#002147;color:#fff;text-align:center;padding:20px}
nav{background:#004080;text-align:center;padding:10px}
nav a{color:#fff;margin:0 15px;text-decoration:none;font-weight:bold}
.ticker{background:#000;color:#0ff;padding:8px;text-align:center}
.live-container{position:relative;padding-top:56.25%;margin:20px}
.live-container iframe{position:absolute;width:100%;height:100%;border:0}
.controls{text-align:center;margin:10px}
button{padding:10px;margin:5px;background:red;color:#fff;border:none;border-radius:5px}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px;padding:10px}
.grid iframe{width:100%;height:150px;border:0}
footer{background:#002147;color:#fff;text-align:center;padding:15px;margin-top:20px}

/* Floating Buttons */
.floating-buttons{position:fixed;bottom:20px;right:20px;display:flex;flex-direction:column;gap:10px;z-index:999}
.floating-buttons a{display:flex;align-items:center;justify-content:center;width:60px;height:60px;border-radius:50%;color:#fff;font-size:28px;text-decoration:none;box-shadow:0 4px 8px rgba(0,0,0,0.3);overflow:hidden;transition:0.3s;position:relative}
.floating-buttons a span{position:absolute;right:100%;white-space:nowrap;background:#222;color:#fff;padding:8px 12px;border-radius:8px;opacity:0;transition:0.3s;font-size:14px}
.floating-buttons a:hover{width:auto;padding:0 20px 0 10px}
.floating-buttons a:hover span{opacity:1;right:70px}
.whatsapp{background:#25D366}
.paypal{background:#003087}
</style>
</head>

<body>

<header>SAMU TV KENYA</header>

<nav>
<a href="#">Home</a>
<a href="#">About</a>
<a href="#">Privacy</a>
<a href="#">Terms</a>
</nav>

<div class="ticker">🔴 SAMU TV KENYA LIVE 24/7 | News • Music • Entertainment</div>

<!-- 🔹 AdSense Top -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="1111111111"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<!-- Live Player -->
<div class="live-container">
<iframe id="player"
src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU&autoplay=1&mute=1"
allowfullscreen></iframe>
</div>

<div class="controls">
<button onclick="goFull()">Fullscreen</button>
<button onclick="unmute()">Sound</button>
</div>

<!-- 🔹 AdSense Middle -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="2222222222"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<h2 style="text-align:center">🔥 Featured Videos</h2>

<div class="grid">
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
<iframe src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU"></iframe>
</div>

<!-- 🔹 AdSense Bottom -->
<div style="text-align:center;margin:20px">
<ins class="adsbygoogle"
style="display:block"
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="3333333333"
data-ad-format="auto"
data-full-width-responsive="true"></ins>
<script>(adsbygoogle=window.adsbygoogle||[]).push({});</script>
</div>

<footer>
© 2026 SAMU TV KENYA | Email: info@samutvkenya.co.ke
</footer>

<!-- Floating Buttons -->
<div class="floating-buttons">
<a href="https://wa.me/254759821389" target="_blank" class="whatsapp">💬<span>Chat WhatsApp</span></a>
<a href="https://www.paypal.com/paypalme/smugo953" target="_blank" class="paypal">💳<span>Pay with PayPal</span></a>
</div>

<script>
function goFull(){
let iframe=document.getElementById("player");
if(iframe.requestFullscreen){iframe.requestFullscreen();}
}

function unmute(){
let iframe=document.getElementById("player");
iframe.src=iframe.src.replace("mute=1","mute=0");
}
</script>

</body>
</html>