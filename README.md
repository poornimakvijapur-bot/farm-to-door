# farm-to-door[index.html](https://github.com/user-attachments/files/34978867/index.html)
<!doctype html><html><head><meta charset=utf8><meta name=viewport content="width=device-width,initial-scale=1,viewport-fit=cover"><style>:root{color-scheme:light;box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}html{scroll-padding-top:env(safe-area-inset-top,0px)}body{margin:0;padding:0;font:14px -apple-system,BlinkMacSystemFont,sans-serif;background:#fff;color:#000}img{max-width:100%}[hidden]:not([hidden=until-found i]){display:none!important}</style></head><body>
<title>Farm to Door</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,700&family=Hind:wght@400;500;600&family=IBM+Plex+Mono:wght@500&display=swap">
<style>
/* Layout: a market-stall ledger. Sticky mode switch on top, produce grid left, order slip right (stacks on phones). */
:root{
  --bg:#F2F5EC; --surface:#FFFFFF; --fg:#1A2B1E; --muted:#5B6B5E; --line:#D9E0CF;
  --leaf:#1F6B3A; --leaf-ink:#FFFFFF; --leaf-soft:#DCEBD7;
  --turmeric:#D99A00; --turmeric-soft:#F7E8BD; --danger:#B3321F;
  --sea:#1D5FA8; --sea-soft:#DCE8F6;
  --f-display:"Bricolage Grotesque","Trebuchet MS",sans-serif;
  --f-body:"Hind","Segoe UI",system-ui,sans-serif;
  --f-mono:"IBM Plex Mono",ui-monospace,Menlo,monospace;
}
@media (prefers-color-scheme: dark){:root:not([data-theme="light"]){
  --bg:#121A14; --surface:#1B261E; --fg:#E6EEDF; --muted:#9DB0A0; --line:#2C3B30;
  --leaf:#5FBF7F; --leaf-ink:#0E1A11; --leaf-soft:#22392A;
  --turmeric:#F0B93A; --turmeric-soft:#3A3115; --danger:#F08A78;
  --sea:#7DB3EE; --sea-soft:#1F3047; color-scheme:dark}}
:root[data-theme="dark"]{
  --bg:#121A14; --surface:#1B261E; --fg:#E6EEDF; --muted:#9DB0A0; --line:#2C3B30;
  --leaf:#5FBF7F; --leaf-ink:#0E1A11; --leaf-soft:#22392A;
  --turmeric:#F0B93A; --turmeric-soft:#3A3115; --danger:#F08A78;
  --sea:#7DB3EE; --sea-soft:#1F3047; color-scheme:dark}

*{box-sizing:border-box}
body{background:var(--bg);color:var(--fg);font:16px/1.5 var(--f-body);margin:0;
  padding-block:0 48px;padding-left:max(16px,env(safe-area-inset-left,0px));padding-right:max(16px,env(safe-area-inset-right,0px))}
.wrap{max-width:1120px;margin:0 auto}
h1,h2,h3{font-family:var(--f-display);margin:0;text-wrap:balance;line-height:1.1}
button,input,select{font:inherit;color:inherit}
:focus-visible{outline:3px solid var(--turmeric);outline-offset:2px}

header.top{padding-block:28px 20px;display:flex;flex-wrap:wrap;gap:20px 32px;align-items:flex-end;justify-content:space-between}
.brand h1{font-size:clamp(2rem,6vw,3.2rem);font-weight:700;letter-spacing:-.02em}
.brand h1 span{color:var(--leaf)}
.brand p{margin:8px 0 0;color:var(--muted);max-width:46ch}
.switch{display:inline-flex;background:var(--surface);border:1px solid var(--line);border-radius:999px;padding:4px;gap:4px;flex-wrap:wrap}
.switch button{border:0;background:none;padding:10px 20px;border-radius:999px;cursor:pointer;font-weight:600;color:var(--muted)}
.switch button[aria-pressed="true"]{background:var(--leaf);color:var(--leaf-ink)}
.switch.market{margin-bottom:16px}
.switch.market button{padding:8px 16px}
.switch.market button.out[aria-pressed="true"]{background:var(--sea);color:var(--leaf-ink)}

.layout{display:grid;grid-template-columns:minmax(0,1fr) 340px;gap:28px;align-items:start}
@media (max-width:900px){.layout{grid-template-columns:minmax(0,1fr)}}

.tools{display:flex;flex-wrap:wrap;gap:12px;margin-bottom:16px}
.tools input[type=search]{flex:1 1 220px;min-width:0;padding:11px 14px;border:1px solid var(--line);border-radius:10px;background:var(--surface)}
.chips{display:flex;flex-wrap:wrap;gap:8px}
.chip{border:1px solid var(--line);background:var(--surface);border-radius:999px;padding:6px 14px;cursor:pointer;font-size:.9rem}
.chip[aria-pressed="true"]{background:var(--fg);color:var(--bg);border-color:var(--fg)}
.banner{background:var(--sea-soft);border-radius:10px;padding:10px 14px;font-size:.9rem;margin-bottom:16px}

.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(230px,1fr));gap:16px}
.card{background:var(--surface);border:1px solid var(--line);border-radius:14px;overflow:hidden;display:flex;flex-direction:column;min-width:0}
.tile{height:84px;background:var(--leaf-soft);display:flex;align-items:flex-end;justify-content:space-between;padding:10px 14px}
.out .tile{background:var(--sea-soft)}
.tile b{font:700 1.7rem/1 var(--f-display);color:var(--leaf)}
.out .tile b{color:var(--sea)}
.tag{font:500 .72rem var(--f-mono);letter-spacing:.04em;text-transform:uppercase;color:var(--muted)}
.card .body{padding:14px;display:flex;flex-direction:column;gap:6px;flex:1}
.card h3{font-size:1.2rem}
.farmer{color:var(--muted);font-size:.9rem}
.price{font:600 1.45rem var(--f-mono);font-variant-numeric:tabular-nums;color:var(--leaf)}
.imgwrap{position:relative}
.cardimg{display:block;width:100%;height:150px;object-fit:cover;background:var(--leaf-soft)}
.badge{position:absolute;left:8px;bottom:8px;font:500 .7rem var(--f-mono);background:rgba(0,0,0,.6);color:#fff;padding:3px 8px;border-radius:6px}
.thumb{width:40px;height:40px;object-fit:cover;border-radius:8px;vertical-align:middle;margin-right:8px}
.prev{display:block;width:100%;max-width:240px;border-radius:10px;margin-top:8px}
.price small{color:var(--muted);font-size:.78rem}
.save{font-size:.82rem;background:var(--turmeric-soft);color:var(--fg);border-radius:6px;padding:3px 8px;align-self:flex-start}
.save.sea{background:var(--sea-soft)}
.stock{font-size:.82rem;color:var(--muted)}
.buy{display:flex;gap:8px;margin-top:auto;padding-top:8px}
.buy input{width:84px;padding:8px;border:1px solid var(--line);border-radius:8px;background:var(--bg);font-family:var(--f-mono)}
.btn{border:0;border-radius:10px;padding:10px 16px;background:var(--leaf);color:var(--leaf-ink);font-weight:600;cursor:pointer}
.btn.sea{background:var(--sea)}
.btn.ghost{background:none;border:1px solid var(--line);color:var(--fg)}
.btn.small{padding:6px 10px;font-size:.85rem}
.btn:disabled{opacity:.5;cursor:not-allowed}
.buy .btn{flex:1}

.slip,.panel{background:var(--surface);border:1px solid var(--line);border-radius:14px;padding:18px}
.slip{position:sticky;top:12px}
@media (max-width:900px){.slip{position:static}}
.slip h2,.panel h2{font-size:1.35rem;margin-bottom:12px}
.line{display:grid;grid-template-columns:1fr auto;gap:2px 10px;padding:10px 0;border-bottom:1px dashed var(--line)}
.line .nm{font-weight:600}
.line .sub{color:var(--muted);font-size:.85rem}
.line .amt{font-family:var(--f-mono);text-align:right}
.line button{grid-column:1/-1;justify-self:start;background:none;border:0;color:var(--danger);cursor:pointer;padding:0;font-size:.85rem}
.total{display:flex;justify-content:space-between;font:500 1.2rem var(--f-mono);padding:14px 0}
.empty{color:var(--muted);padding:8px 0 12px}
label{display:block;font-size:.85rem;font-weight:600;margin:10px 0 4px}
.field{width:100%;padding:10px 12px;border:1px solid var(--line);border-radius:8px;background:var(--bg)}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:12px}
@media (max-width:480px){.row2{grid-template-columns:1fr}}
.opts{display:flex;gap:8px;margin-top:4px;flex-wrap:wrap}
.opts label{display:flex;gap:6px;align-items:center;font-weight:500;margin:0;border:1px solid var(--line);border-radius:8px;padding:8px 12px;cursor:pointer}
.check{display:flex;gap:10px;align-items:center;font-weight:600;font-size:1rem;margin:16px 0 0;cursor:pointer}
.msg{margin:10px 0 0;font-size:.9rem;min-height:1.3em}
.msg.err{color:var(--danger)} .msg.ok{color:var(--leaf);font-weight:600}
.hint{background:var(--turmeric-soft);border-radius:8px;padding:8px 12px;font-size:.9rem;margin-top:10px}
.hint.sea{background:var(--sea-soft)}
.exportbox{border:1px solid var(--sea);border-radius:10px;padding:4px 14px 14px;margin-top:10px}

.farmer-grid{display:grid;grid-template-columns:minmax(0,1fr) minmax(0,1fr);gap:24px;align-items:start}
@media (max-width:900px){.farmer-grid{grid-template-columns:minmax(0,1fr)}}
.stack{display:grid;gap:24px;min-width:0}
.listing{display:grid;grid-template-columns:1fr auto;gap:4px 12px;padding:12px 0;border-bottom:1px dashed var(--line)}
.listing .nm{font-weight:600}
.listing .sub{color:var(--muted);font-size:.85rem;overflow-wrap:anywhere}
.listing .acts{display:flex;gap:6px;align-items:center}
.status{font:500 .72rem var(--f-mono);text-transform:uppercase;letter-spacing:.04em;border-radius:6px;padding:3px 8px;background:var(--turmeric-soft);margin-right:6px}
.status.done{background:var(--leaf-soft);color:var(--leaf)}
.status.exp{background:var(--sea-soft);color:var(--sea)}
.linkbtn{background:none;border:0;padding:4px 0;color:var(--leaf);font-weight:600;cursor:pointer;text-align:left;align-self:flex-start}
.contact{background:var(--leaf-soft);border-radius:8px;padding:10px 12px;display:grid;gap:4px;font-size:.9rem}
.contact .ph{font:500 .95rem var(--f-mono);overflow-wrap:anywhere}
.contact .sub{color:var(--muted);font-size:.82rem}
.contact a,.listing a{color:var(--leaf);font-weight:600}
#myOrdersPanel{margin-top:24px}
.status.ret{background:var(--turmeric-soft)}
.field{font-size:1.05rem;padding:12px 14px}
.btn{min-height:46px;font-size:1.02rem}
.rolebtns{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:14px}
.rolebtn{display:flex;flex-direction:column;gap:6px;text-align:left;padding:26px 22px;background:var(--surface);border:2px solid var(--line);border-radius:16px;cursor:pointer}
.rolebtn b{font:700 1.5rem/1.1 var(--f-display)}
.rolebtn span{color:var(--muted)}
.rolebtn:hover{border-color:var(--leaf)}
.wz-q{font:700 1.2rem var(--f-display);margin:14px 0 10px}
.picks{display:flex;flex-wrap:wrap;gap:10px;margin-bottom:14px}
.pick{border:2px solid var(--line);background:var(--surface);border-radius:12px;padding:12px 18px;font-size:1.05rem;cursor:pointer}
.pick:hover{border-color:var(--leaf)}
.pick.dim{opacity:.55}
.pick small{color:var(--muted)}
#bCatBtns .rolebtn{padding:18px 16px}
#bCatBtns .rolebtn b{font-size:1.2rem}
#catBtns{grid-template-columns:1fr 1fr}
#catBtns .rolebtn{padding:18px 16px}
#catBtns .rolebtn b{font-size:1.15rem}
.auth{max-width:600px;margin:0 auto;padding-block:32px}
.userbar{display:flex;justify-content:flex-end;align-items:center;gap:14px;padding-top:12px;font-size:.9rem;color:var(--muted);flex-wrap:wrap}
.note{color:var(--muted);font-size:.85rem;margin-top:24px}
[hidden]{display:none!important}
@media (prefers-reduced-motion:no-preference){.card{transition:transform .15s}.card:hover{transform:translateY(-2px)}}
</style>

<div class="wrap">
  <section id="authView" class="auth" aria-label="Sign up or log in">
    <div class="brand">
      <h1>Farm <span>to</span> Door</h1>
      <p>Create a free account to buy fresh produce straight from farmers, or to sell your crops in India and abroad.</p>
    </div>
    <div id="roleStep">
      <h2 style="font-size:1.5rem;margin:28px 0 14px">Who are you?</h2>
      <div class="rolebtns">
        <button type="button" class="rolebtn" data-role="farmer"><b>I am a farmer</b><span>I want to sell my crops</span></button>
        <button type="button" class="rolebtn" data-role="buyer"><b>I want to buy</b><span>I want fresh produce from farmers</span></button>
      </div>
      <p style="color:var(--muted);margin-top:18px">Already have an account? <button type="button" class="linkbtn" id="haveAcc" style="display:inline">Log in</button></p>
    </div>
    <div id="authTabs" class="switch" role="group" aria-label="Create account or log in" style="margin:20px 0" hidden>
      <button id="tabUp" type="button" aria-pressed="true">Create account</button>
      <button id="tabIn" type="button" aria-pressed="false">Log in</button>
    </div>

    <form id="signupForm" class="panel" novalidate hidden>
      <p style="margin:0 0 4px"><b id="roleTxt">Creating a buyer account.</b> <button type="button" class="linkbtn" id="backRole" style="display:inline">Change</button></p>
      <div class="opts" hidden>
        <label><input type="radio" name="sRole" value="buyer" checked> Buyer</label>
        <label><input type="radio" name="sRole" value="farmer"> Farmer</label>
      </div>
      <div class="row2">
        <div><label for="sName">Full name</label><input class="field" id="sName" autocomplete="name"></div>
        <div id="sEmailBox"><label for="sEmail" id="sEmailL">Email</label><input class="field" id="sEmail" type="email" autocomplete="email"></div>
      </div>
      <div class="row2">
        <div><label for="sPhone" id="sPhoneL">Mobile number (optional)</label><input class="field" id="sPhone" inputmode="tel" autocomplete="tel" placeholder="10 digits in India"></div>
        <div><label for="sCountry">Country</label><select class="field" id="sCountry"></select></div>
      </div>
      <div class="row2">
        <div><label for="sState">State or region</label><input class="field" id="sState" autocomplete="address-level1" placeholder="e.g. Karnataka"></div>
        <div><label for="sPin">PIN or postal code (optional)</label><input class="field" id="sPin" autocomplete="postal-code"></div>
      </div>
      <label for="sAddress">Address</label>
      <input class="field" id="sAddress" autocomplete="street-address" placeholder="House or farm, street, area, city">

      <div id="farmerExtra" class="exportbox" hidden>
        <div class="row2">
          <div><label for="sVillage">Village or farm name</label><input class="field" id="sVillage" placeholder="e.g. Doddaballapur"></div>
          <div><label for="sCrops">Main crops (optional)</label><input class="field" id="sCrops" placeholder="e.g. tomato, ragi"></div>
        </div>
        <label class="check" for="sExport"><input type="checkbox" id="sExport"> I am interested in selling abroad</label>
      </div>
      <div id="buyerExtra" class="exportbox">
        <label for="sBuyerType">What kind of buyer are you?</label>
        <select class="field" id="sBuyerType">
          <option>Family or home</option><option>Shop or restaurant</option><option>Company or importer abroad</option>
        </select>
      </div>

      <label for="sLang">Preferred language</label>
      <select class="field" id="sLang"><option>English</option><option>Kannada (ಕನ್ನಡ)</option><option>Hindi (हिन्दी)</option></select>
      <label class="check" for="sAgree" style="font-weight:500;font-size:.9rem"><input type="checkbox" id="sAgree"> I agree to share my name and contact details with the farmers or buyers I trade with.</label>
      <button class="btn" type="submit" style="width:100%;margin-top:14px">Create account</button>
      <p class="msg" id="sMsg" role="status"></p>
    </form>

    <form id="loginForm" class="panel" novalidate hidden><!-- shown after the role step -->
      <label for="lEmail" id="lLabel">Email or mobile number you signed up with</label>
      <input class="field" id="lEmail" type="text" autocomplete="username">
      <button class="btn" type="submit" style="width:100%;margin-top:14px">Log in</button>
      <p class="msg" id="lMsg" role="status"></p>
      <p class="sub" style="color:var(--muted);font-size:.85rem">Demo version: this finds the account saved on this device. A password or one-time code (OTP) will be added when the site goes live.</p>
    </form>
  </section>

  <div id="appShell" hidden>
  <div class="userbar"><span id="hello"></span><button id="logout" type="button" class="linkbtn">Log out</button></div>
  <header class="top">
    <div class="brand">
      <h1>Farm <span>to</span> Door</h1>
      <p>Farmers set their own price and sell straight to families nearby, or to buyers abroad in dollars. No middlemen, fresher produce, a fairer deal.</p>
    </div>
    <div class="switch" role="group" aria-label="Choose your role">
      <button id="modeBuy" type="button" aria-pressed="true">I want to buy</button>
      <button id="modeSell" type="button" aria-pressed="false">I am a farmer</button>
    </div>
  </header>

  <main id="buyView" class="layout">
    <section aria-label="Fresh produce">
      <div class="switch market" role="group" aria-label="Choose market">
        <button id="mktIn" type="button" aria-pressed="true">Buy in India (₹)</button>
        <button id="mktOut" class="out" type="button" aria-pressed="false">Buy from abroad ($)</button>
      </div>
      <div id="banner" class="banner" hidden></div>
      <div id="bStep1">
        <p class="wz-q">1. What do you want to buy?</p>
        <div class="rolebtns" id="bCatBtns"></div>
        <p style="margin-top:14px"><button type="button" class="linkbtn" id="bAll" style="display:inline">Or show everything</button></p>
      </div>
      <div id="bStep2" hidden>
        <p class="wz-q">2. Which one? <button type="button" class="linkbtn" id="bBack" style="display:inline">Change type</button></p>
        <div class="picks" id="bNameBtns"></div>
      </div>
      <div id="bStep3" hidden>
        <p class="wz-q">Buying: <b id="bSel"></b> <button type="button" class="linkbtn" id="bChange" style="display:inline">Change</button></p>
        <div class="tools">
          <input id="search" type="search" placeholder="Search by farmer, village or crop" aria-label="Search produce">
        </div>
      </div>
      <div class="chips" id="chips" hidden></div>
      <div class="grid" id="grid" hidden></div>
    </section>
    <aside class="slip" aria-label="Your order">
      <h2 id="slipTitle">Your order</h2>
      <div id="cartLines"></div>
      <div class="total"><span>Total</span><span id="cartTotal">₹0</span></div>

      <form id="orderForm" novalidate>
        <label for="cName">Your name</label>
        <input class="field" id="cName" autocomplete="name">
        <label for="cPhone">Mobile number</label>
        <input class="field" id="cPhone" inputmode="numeric" maxlength="10" autocomplete="tel" placeholder="10 digits">
        <label>How do you want it?</label>
        <div class="opts">
          <label><input type="radio" name="mode" value="Home delivery" checked> Home delivery</label>
          <label><input type="radio" name="mode" value="Pick up from farm"> Pick up from farm</label>
        </div>
        <label for="cAddr">Address or area</label>
        <input class="field" id="cAddr" autocomplete="street-address" placeholder="e.g. Indiranagar, Bengaluru">
        <button class="btn" type="submit" style="width:100%;margin-top:14px" id="placeBtn">Place order</button>
        <p class="msg" id="orderMsg" role="status"></p>
      </form>

      <form id="exportForm" novalidate hidden>
        <label for="xCompany">Company or buyer name</label>
        <input class="field" id="xCompany" autocomplete="organization">
        <div class="row2">
          <div><label for="xCountry">Country</label><input class="field" id="xCountry" placeholder="e.g. UAE"></div>
          <div><label for="xEmail">Email</label><input class="field" id="xEmail" type="email" autocomplete="email"></div>
        </div>
        <label for="xShip">How should it be shipped?</label>
        <select class="field" id="xShip"><option>Sea freight (container)</option><option>Air freight</option></select>
        <label for="xNote">Port, packing or other needs (optional)</label>
        <input class="field" id="xNote" placeholder="e.g. Dubai port, 10 kg cartons">
        <button class="btn sea" type="submit" style="width:100%;margin-top:14px" id="xBtn">Send enquiry</button>
        <p class="msg" id="xMsg" role="status"></p>
      </form>
    </aside>
  </main>

  <section id="myOrdersPanel" class="panel" aria-label="Your orders and returns" hidden>
    <h2>Your orders and returns</h2>
    <div id="myOrders"></div>
  </section>

  <main id="sellView" hidden>
    <div class="farmer-grid">
      <section class="panel" aria-label="Add produce">
        <h2>List your produce</h2>
        <p class="msg ok" id="wzMsg" role="status"></p>
        <div id="wzCat">
          <p class="wz-q">1. What are you selling?</p>
          <div class="rolebtns" id="catBtns"></div>
        </div>
        <div id="wzName" hidden>
          <p class="wz-q">2. Which one? <button type="button" class="linkbtn" id="wzBack" style="display:inline">Change type</button></p>
          <div class="picks" id="nameBtns"></div>
          <label for="wzOther">Not in the list? Type the name</label>
          <div style="display:flex;gap:8px">
            <input class="field" id="wzOther" placeholder="e.g. Sweet corn">
            <button type="button" class="btn" id="wzUse">Use this</button>
          </div>
          <p class="msg err" id="wzErr" role="status"></p>
        </div>
        <div id="wzForm" hidden>
        <p class="wz-q">3. Price and quantity. Selling: <b id="wzSel"></b> <button type="button" class="linkbtn" id="wzChange" style="display:inline">Change</button></p>
        <form id="listForm" novalidate>
          <div class="row2">
            <div><label for="fName">Your name</label><input class="field" id="fName" autocomplete="name"></div>
            <div><label for="fVillage">Village / town</label><input class="field" id="fVillage" placeholder="e.g. Doddaballapur"></div>
          </div>
          <label for="fPhone">Your mobile number (customers use it to contact you)</label>
          <input class="field" id="fPhone" inputmode="numeric" maxlength="10" autocomplete="tel" placeholder="10 digits">
          <div id="cropBox" hidden>
          <label for="fCrop">What are you selling?</label>
          <input class="field" id="fCrop" list="crops" placeholder="e.g. Tomato">
          <datalist id="crops"></datalist>
          </div>
          <div class="row2">
            <div hidden><label for="fCat">Type</label><select class="field" id="fCat"></select></div>
            <div><label for="fUnit">Sold per</label><select class="field" id="fUnit"><option>kg</option><option>dozen</option><option>litre</option><option>piece</option></select></div>
          </div>
          <div class="row2">
            <div><label for="fPrice">Your price in India (₹)</label><input class="field" id="fPrice" type="number" min="1" step="1" inputmode="numeric"></div>
            <div><label for="fQty">Quantity available</label><input class="field" id="fQty" type="number" min="1" step="1" inputmode="numeric"></div>
          </div>
          <label for="fPhoto">Photo of your produce (buyers trust listings with a photo)</label>
          <input class="field" id="fPhoto" type="file" accept="image/*">
          <img id="fPhotoPrev" class="prev" alt="Preview of your photo" hidden>
          <p class="msg err" id="photoMsg" role="status"></p>
          <div id="priceHint" class="hint" hidden></div>

          <label class="check" for="fExport"><input type="checkbox" id="fExport"> Also sell abroad in dollars</label>
          <div id="exportFields" class="exportbox" hidden>
            <div class="row2">
              <div><label for="fUsd">Export price ($ per unit)</label><input class="field" id="fUsd" type="number" min="0.01" step="0.01" inputmode="decimal"></div>
              <div><label for="fMin">Minimum order</label><input class="field" id="fMin" type="number" min="1" step="1" inputmode="numeric" placeholder="e.g. 500"></div>
            </div>
            <div id="usdHint" class="hint sea" hidden></div>
            <div class="hint sea">Before exporting, farmers usually need an Importer-Exporter Code (IEC) from DGFT, APEDA registration for many farm products, and a plant health (phytosanitary) certificate. Check the exact rules for your crop and country with APEDA or DGFT.</div>
          </div>

          <button class="btn" type="submit" style="margin-top:14px">Add to marketplace</button>
          <p class="msg" id="listMsg" role="status"></p>
        </form>
        </div>
      </section>
      <div class="stack">
        <section class="panel" aria-label="Your listings">
          <h2>Your listings</h2>
          <div id="myListings"></div>
        </section>
        <section class="panel" aria-label="Orders and enquiries received">
          <h2>Orders and enquiries</h2>
          <div id="orders"></div>
        </section>
      </div>
    </div>
  </main>

  <p class="note">Demo version: your account, listings, orders and cart are saved in this browser only, and no money is taken. Prices marked "market" are sample reference rates. Dollar amounts use a sample rate of ₹88 = $1; use the real rate when you go live. Export orders here are enquiries: the farmer confirms price, shipping and payment with the buyer directly.</p>
  </div>
</div>

<script>
(function(){
  var FX=88; /* sample rupees per dollar */
  var CATS=["Vegetables","Fruits","Grains & pulses","Dairy & eggs","Spices"];
  var MANDI={tomato:22,onion:28,potato:26,carrot:38,spinach:30,mango:70,banana:48,ragi:36,rice:44,"toor dal":120,milk:48,ghee:560,eggs:78,turmeric:150};
  var SEED=[
    {id:"s1",name:"Tomato (country)",cat:"Vegetables",farmer:"Ramesh Gowda",village:"Doddaballapur",price:28,market:22,retail:45,stock:120,unit:"kg"},
    {id:"s2",name:"Spinach (palak)",cat:"Vegetables",farmer:"Lakshmi Devi",village:"Kanakapura",price:30,market:30,retail:50,stock:40,unit:"kg"},
    {id:"s3",name:"Carrot",cat:"Vegetables",farmer:"Mahesh Kumar",village:"Ooty road farms",price:42,market:38,retail:60,stock:80,unit:"kg"},
    {id:"s4",name:"Banganapalli mango",cat:"Fruits",farmer:"Venkatesh Reddy",village:"Srinivaspur",price:85,market:70,retail:130,stock:600,unit:"kg",export:true,usd:1.6,minQty:500},
    {id:"s5",name:"Robusta banana",cat:"Fruits",farmer:"Suresh Naik",village:"Maddur",price:52,market:48,retail:70,stock:15,unit:"dozen"},
    {id:"s6",name:"Ragi (finger millet)",cat:"Grains & pulses",farmer:"Nagamma",village:"Tumakuru",price:40,market:36,retail:58,stock:3000,unit:"kg",export:true,usd:0.9,minQty:1000},
    {id:"s7",name:"Toor dal",cat:"Grains & pulses",farmer:"Basavaraj Patil",village:"Kalaburagi",price:125,market:120,retail:165,stock:2500,unit:"kg",export:true,usd:1.55,minQty:1000},
    {id:"s8",name:"A2 cow milk",cat:"Dairy & eggs",farmer:"Shanthamma",village:"Hosakote",price:62,market:48,retail:70,stock:30,unit:"litre"},
    {id:"s9",name:"Country eggs",cat:"Dairy & eggs",farmer:"Anitha Reddy",village:"Chikkaballapur",price:92,market:78,retail:110,stock:25,unit:"dozen"},
    {id:"s10",name:"Turmeric powder",cat:"Spices",farmer:"Palani Selvam",village:"Erode",price:180,market:150,retail:240,stock:400,unit:"kg",export:true,usd:3.4,minQty:200}
  ];
  SEED.forEach(function(p,i){p.phone="90000000"+("0"+(i+1)).slice(-2);p.sample=true});
  var KEY="farm-to-door-v3";
  var st={mode:"buy",market:"in",cat:"All",q:"",products:SEED.slice(),cart:{},xcart:{},orders:[],user:null,accounts:[],bCat:null,bName:null};

  try{var raw=localStorage.getItem(KEY);if(raw){var d=JSON.parse(raw);
    if(d.products)st.products=d.products;if(d.cart)st.cart=d.cart;if(d.xcart)st.xcart=d.xcart;if(d.orders)st.orders=d.orders;if(d.user)st.user=d.user;if(d.accounts)st.accounts=d.accounts;if(st.user)st.mode=st.user.role==="farmer"?"sell":"buy";}}catch(e){}
  function save(){try{localStorage.setItem(KEY,JSON.stringify({products:st.products,cart:st.cart,xcart:st.xcart,orders:st.orders,user:st.user,accounts:st.accounts}))}catch(e){}}

  function $(id){return document.getElementById(id)}
  function esc(s){return String(s).replace(/[&<>"']/g,function(c){return{"&":"&","<":"<",">":">",'"':""","'":"'"}[c]})}
  function inr(n){return "₹"+Math.round(n).toLocaleString("en-IN")}
  function usd(n){return "$"+Number(n).toLocaleString("en-US",{minimumFractionDigits:2,maximumFractionDigits:2})}
  function find(id){return st.products.filter(function(p){return p.id===id})[0]}
  function isOut(){return st.market==="out"}
  function cartObj(){return isOut()?st.xcart:st.cart}
  function unitPrice(p){return isOut()?p.usd:p.price}
  function fmt(n){return isOut()?usd(n):inr(n)}

  function fmtPhone(p){return p?p.slice(0,5)+" "+p.slice(5):""}
  function contactHtml(p){
    var wa=p.sample?'<div class="sub">Sample number for this demo. Real farmers show their own number here.</div>'
      :'<a href="https://wa.me/91'+esc(p.phone)+'" target="_blank" rel="noopener">Message on WhatsApp</a>';
    return '<div class="ph">'+esc(p.farmer)+': '+esc(fmtPhone(p.phone))+'</div>'+wa+
      '<button type="button" class="linkbtn" data-copy="'+esc(p.phone)+'">Copy number</button>';
  }
  function contactsFor(items){
    var seen={},out=[];
    items.forEach(function(i){var p=find(i.id);if(p&&!seen[p.id]){seen[p.id]=1;out.push(p.farmer+" "+fmtPhone(p.phone))}});
    return out.join(", ");
  }
  function copyText(t,btn){
    var done=function(){btn.textContent="Copied"};
    var fail=function(){btn.textContent="Select the number above and copy it"};
    try{navigator.clipboard.writeText(t).then(done,fail)}catch(e){fail()}
  }

  /* ---------- customer view ---------- */
  function renderChips(){
    var all=["All"].concat(CATS);
    $("chips").innerHTML=all.map(function(c){
      return '<button type="button" class="chip" data-cat="'+esc(c)+'" aria-pressed="'+(st.cat===c)+'">'+esc(c)+'</button>';
    }).join("");
  }
  function renderGrid(){
    var q=st.q.trim().toLowerCase(),out=isOut();
    var list=st.products.filter(function(p){
      return (!out||p.export)&&(st.cat==="All"||p.cat===st.cat)&&nameMatch(p)&&(!q||(p.name+" "+p.farmer+" "+p.village).toLowerCase().indexOf(q)>-1);
    });
    if(!list.length){$("grid").innerHTML='<p class="empty">'+(out?'No farmer has listed this for export yet. Try another crop or category.':'Nothing matches that search. Try another crop or category.')+'</p>';return}
    $("grid").innerHTML=list.map(function(p){
      var soldOut=p.stock<=0||(out&&p.stock<p.minQty);
      var badge,priceLine;
      if(out){
        badge='<span class="save sea">Minimum order '+p.minQty.toLocaleString("en-IN")+' '+esc(p.unit)+'</span>';
        priceLine=usd(p.usd)+'<small>/'+esc(p.unit)+'</small> <small>≈ '+inr(p.usd*FX)+'</small>';
      }else{
        badge=p.retail&&p.retail>p.price?'<span class="save">'+inr(p.retail-p.price)+' cheaper than shop price</span>':'';
        priceLine=inr(p.price)+'<small>/'+esc(p.unit)+'</small> '+(p.market?'<small>market '+inr(p.market)+'/'+esc(p.unit)+'</small>':'');
      }
      var minv=out?p.minQty:1;
      return '<article class="card'+(out?' out':'')+'"><div class="imgwrap"><img class="cardimg" alt="'+esc(p.name)+'" src="'+esc(p.photo||illus(p))+'"><span class="badge">'+(p.photo?"Farmer's photo":"Sample picture")+'</span></div>'+
        '<div class="body"><h3>'+esc(p.name)+'</h3>'+
        '<div class="farmer">'+esc(p.farmer)+' · '+esc(p.village)+'</div>'+
        '<div class="price">'+priceLine+'</div>'+badge+
        '<div class="stock">'+(soldOut?'Not available now':p.stock.toLocaleString("en-IN")+' '+esc(p.unit)+' available')+'</div>'+
        '<div class="buy"><input type="number" min="'+minv+'" max="'+p.stock+'" value="'+minv+'" aria-label="Quantity for '+esc(p.name)+'" id="q-'+esc(p.id)+'"'+(soldOut?' disabled':'')+'>'+
        '<button type="button"
