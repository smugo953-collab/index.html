# index.html<<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SAMU TV Miracle</title>
  <style>
    body { font-family: Arial; background: #111; color: #fff; margin: 0; padding: 0;}
    header { background: #ff6600; padding: 20px; text-align: center; font-size: 24px; font-weight: bold;}
    section { padding: 30px; }
    h2 { color: #ff6600; }
    #livePlayer { display:flex; justify-content:center; margin:20px 0; }
    iframe, video { width: 80%; max-width: 900px; height: 500px; border: 3px solid #ff6600; border-radius:10px; }
    #channels, #templates { display:flex; gap:20px; flex-wrap:wrap; justify-content:center; }
    .btn { background:#222; color:#fff; padding:10px 20px; border:2px solid #ff6600; border-radius:8px; cursor:pointer; transition:0.3s; }
    .btn:hover { background:#ff6600; color:#111; }
    .item { text-align:center; }
    .item video { width: 250px; height: 140px; margin-bottom:10px; }
  </style>
</head>
<body>
  <header>SAMU TV Miracle</header>

  <!-- Live Channels Section -->
  <section>
    <h2>📡 Live Channels</h2>
    <div id="livePlayer"><iframe id="player" src="" frameborder="0" allowfullscreen></iframe></div>
    <div id="channels"></div>
  </section>

  <!-- Template Marketplace Section -->
  <section>
    <h2>🎬 Templates Marketplace</h2>
    <div id="templates"></div>
  </section>

  <script type="module">
    const API_URL = "http://localhost:5000/api"; // replace with your backend live URL
    const player = document.getElementById('player');
    const channelsDiv = document.getElementById('channels');
    const templatesDiv = document.getElementById('templates');

    // --- Load Live Channels ---
    async function loadLiveChannels() {
      try {
        const res = await fetch(`${API_URL}/live-channels`);
        const channels = await res.json();
        if (channels.length > 0) player.src = channels[0].url;
        channels.forEach(ch => {
          const btn = document.createElement('button');
          btn.className = 'btn';
          btn.textContent = ch.name;
          btn.onclick = () => player.src = ch.url;
          channelsDiv.appendChild(btn);
        });
      } catch(err) {
        console.error(err);
        channelsDiv.innerHTML = "<p style='color:red;'>Unable to load live channels</p>";
      }
    }

    // --- Template Marketplace ---
    const templates = [
      { id:1, name:"Love Template", file:"templates/love_template.mp4", price:5 },
      { id:2, name:"Reggae Template", file:"templates/reggae_template.mp4", price:3 },
      { id:3, name:"Bongo Template", file:"templates/bongo_template.mp4", price:4 }
    ];

    function loadTemplates() {
      templates.forEach(t => {
        const div = document.createElement('div');
        div.className = 'item';
        div.innerHTML = `
          <video src="${t.file}" controls muted></video>
          <div>${t.name} - $${t.price}</div>
          <button class="btn" onclick="buyTemplate(${t.id})">Buy & Download</button>
        `;
        templatesDiv.appendChild(div);
      });
    }

    // --- Payment & Download ---
    async function buyTemplate(templateId){
      const template = templates.find(t => t.id === templateId);
      // Call Stripe/PayPal/M-Pesa API
      const session = await fetch(`${API_URL}/stripe/create-checkout-session`, {
        method:'POST',
        headers:{'Content-Type':'application/json'},
        body: JSON.stringify({ templateId })
      }).then(r=>r.json());
      const stripe = Stripe("YOUR_STRIPE_PUBLIC_KEY"); // replace with your key
      stripe.redirectToCheckout({ sessionId: session.id });
    }

    // --- Auto-download after success ---
    const urlParams = new URLSearchParams(window.location.search);
    if(urlParams.get("success") && urlParams.get("template")){
      const templateId = urlParams.get("template");
      const template = templates.find(t=>t.id==templateId);
      const a = document.createElement('a');
      a.href = template.file;
      a.download = template.file.split('/').pop();
      a.click();
      alert("Template downloaded successfully!");
    }

    // --- Initialize ---
    loadLiveChannels();
    loadTemplates();
  </script>
  <!-- Stripe JS -->
  <script src="https://js.stripe.com/v3/"></script>
</body>
</html>USERS (Viewers / Customers)
                   │
                   ▼
        🌐 FRONTEND (Vercel)
   - index.html (UI)
   - Live TV Player
   - Template Marketplace
   - Video Editor (ffmpeg)
   - Payment Buttons
                   │
        API Requests (fetch)
                
↓
Auto-download template│
                   ▼
        ⚙️ BACKEND (Railway)
   - /api/live-channels
   - /api/stripe
   - /api/paypal
   - /api/mpesa
   - Auth & Database
                   │
      ┌────────────┼────────────┐
      ▼            ▼            ▼
 💳 PAYMENTS   📡 STREAMS   📦 TEMPLATES
 Stripe        YouTube      Stored Videos
 PayPal        Facebook     Download Links
 M-Pesa        Instagram    Edited Files
               Twitter/api/live-channelsFrontend → Backend → Payment GatewayUser redirected → frontend
↓
Auto-download template