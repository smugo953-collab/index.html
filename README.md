<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SAMU TV Miracle</title>
<style>
body { font-family: Arial; background: #111; color: #fff; margin: 0; padding: 0;}
header { background: #ff6600; padding: 20px; text-align: center; font-size: 24px; font-weight: bold;}
section { padding: 20px; }
h2 { color: #ff6600; }
#livePlayer { display:flex; justify-content:center; margin:20px 0; }
iframe, video { width: 80%; max-width: 900px; height: 500px; border: 3px solid #ff6600; border-radius:10px; }
#channels, #templates, #merch { display:flex; gap:20px; flex-wrap:wrap; justify-content:center; margin-bottom:30px; }
.btn { background:#222; color:#fff; padding:10px 20px; border:2px solid #ff6600; border-radius:8px; cursor:pointer; transition:0.3s; }
.btn:hover { background:#ff6600; color:#111; }
.item { text-align:center; }
.item img, .item video { width: 250px; height: 140px; margin-bottom:10px; border-radius:8px; }
footer { text-align:center; padding:15px; background:#222; margin-top:20px; color:#fff; }
</style>
</head>
<body>

<header>SAMU TV Miracle</header>

<section>
<h2>📡 Live Channels</h2>
<div id="livePlayer">
  <iframe id="player" src="https://www.youtube.com/embed/videoseries?list=PLazHNRREZJPvUAMd3K2HuSqxZJVSR5BdU&autoplay=1&mute=1" frameborder="0" allowfullscreen></iframe>
</div>
<div id="channels"></div>
</section>

<section>
<h2>🎬 Templates Marketplace</h2>
<div id="templates"></div>
</section>

<section>
<h2>🛒 Merch Products</h2>
<div id="merch">
  <div class="item">
    <img src="products/tshirt.jpg" alt="Samu TV T-Shirt">
    <div>T-Shirt - $15</div>
    <button class="btn" onclick="buyMerch('T-Shirt', 'paypal')">PayPal</button>
    <button class="btn" onclick="buyMerch('T-Shirt', 'mpesa')">M-Pesa</button>
    <button class="btn" onclick="updateWhatsApp('T-Shirt', 15)">WhatsApp Order</button>
  </div>
  <div class="item">
    <img src="products/hat.jpg" alt="Samu TV Hat">
    <div>Hat - $10</div>
    <button class="btn" onclick="buyMerch('Hat', 'paypal')">PayPal</button>
    <button class="btn" onclick="buyMerch('Hat', 'mpesa')">M-Pesa</button>
    <button class="btn" onclick="updateWhatsApp('Hat', 10)">WhatsApp Order</button>
  </div>
</div>
</section>

<a id="whatsappBtn" href="https://wa.me/254700123456?text=Hi%20Samu%20TV!" 
   style="position:fixed; bottom:20px; right:20px; background:#25D366; color:#fff; padding:15px 20px; border-radius:50px; font-weight:bold; text-decoration:none; box-shadow:0 5px 10px rgba(0,0,0,0.3); z-index:9999; display:flex; align-items:center; gap:10px; font-size:16px;" target="_blank">
  📲 Order Now
</a>

<footer>
© 2026 SAMU TV Miracle | Email: info@samutvkenya.co.ke
</footer>

<script src="https://js.stripe.com/v3/"></script>

<script>
// WhatsApp number
const whatsappNumber = "254700123456"; 
let lastProduct = null;

// Floating WhatsApp update
function updateWhatsApp(productName, price){
  lastProduct = { name: productName, price: price };
  const message = `Hi Samu TV! I want to buy: ${productName} for $${price}`;
  document.getElementById('whatsappBtn').href = `https://wa.me/${whatsappNumber}?text=${encodeURIComponent(message)}`;
}

// Merch Payments
async function buyMerch(productName, method){
  if(method==='paypal'){
    window.open(`https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&business=YOUR_PAYPAL_EMAIL&item_name=${productName}&amount=${encodeURIComponent(lastProduct?.price || 0)}&currency_code=USD`, '_blank');
  }
  if(method==='mpesa'){
    alert(`M-Pesa payment request for ${productName} initiated!`);
  }
}

// Templates
const templates = [
  { id:1, name:"Love Template", file:"templates/love_template.mp4", price:5 },
  { id:2, name:"Reggae Template", file:"templates/reggae_template.mp4", price:3 },
  { id:3, name:"Bongo Template", file:"templates/bongo_template.mp4", price:4 }
];

function loadTemplates() {
  const templatesDiv = document.getElementById('templates');
  templates.forEach(t => {
    const div = document.createElement('div');
    div.className = 'item';
    div.innerHTML = `
      ${t.name} - $${t.price} <br>
      <button class="btn" onclick="buyTemplate(${t.id}, 'stripe')">Stripe</button>
      <button class="btn" onclick="buyTemplate(${t.id}, 'paypal')">PayPal</button>
      <button class="btn" onclick="updateWhatsApp('${t.name}', ${t.price})">WhatsApp Order</button>
    `;
    templatesDiv.appendChild(div);
  });
}

// Stripe / PayPal Checkout
async function buyTemplate(templateId, method){
  const template = templates.find(t=>t.id===templateId);
  if(method==='stripe'){
    const session = await fetch(`https://YOUR_BACKEND_URL/stripe/create-checkout-session`, {
      method:'POST',
      headers:{'Content-Type':'application/json'},
      body: JSON.stringify({ templateId })
    }).then(r=>r.json());
    const stripe = Stripe("YOUR_STRIPE_PUBLIC_KEY");
    stripe.redirectToCheckout({ sessionId: session.id });
  } else if(method==='paypal'){
    window.open(`https://www.paypal.com/cgi-bin/webscr?cmd=_xclick&business=YOUR_PAYPAL_EMAIL&item_name=${template.name}&amount=${template.price}&currency_code=USD&return=${encodeURIComponent(window.location.href + "?success=1&template=" + templateId)}`, '_blank');
  }
}

// Auto-download template after successful checkout
const urlParams = new URLSearchParams(window.location.search);
if(urlParams.get("success") && urlParams.get("template")){
  const templateId = parseInt(urlParams.get("template"));
  const template = templates.find(t=>t.id===templateId);
  if(template){
    const a = document.createElement('a');
    a.href = template.file;
    a.download = template.file.split('/').pop();
    a.click();
    alert(`✅ ${template.name} downloaded successfully! Enjoy your template.`);
  }
}

// Initialize
loadTemplates();
</script>

</body>
</html>