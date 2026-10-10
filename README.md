<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<meta name="theme-color" content="#fff0f5">
<title>Be My Valentine? 💗</title>
<style>
  :root { --pink:#ff5f9e; --deep:#c92d70; --paper:rgba(255,255,255,.88); --ink:#612744; }
  * { box-sizing:border-box; }
  body { margin:0; min-height:100vh; font-family:system-ui,-apple-system,Segoe UI,Roboto,sans-serif; color:var(--ink);
    background:linear-gradient(135deg,#fff0f5,#ffe0eb 48%,#fff8fb); background-size:cover; background-position:center; transition:background .3s; }
  .wrap { min-height:100vh; display:grid; place-items:center; padding:22px; }
  .card { width:min(680px,100%); text-align:center; padding:clamp(24px,5vw,48px); background:var(--paper); border:1px solid rgba(255,95,158,.25); border-radius:28px; box-shadow:0 18px 60px rgba(153,35,87,.15); backdrop-filter:blur(8px); }
  .heart { font-size:clamp(48px,9vw,78px); line-height:1.1; animation:beat 1.3s infinite; }
  @keyframes beat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.08)} }
  h1 { font-size:clamp(2rem,7vw,3.5rem); line-height:1.1; margin:16px 0 12px; }
  p { font-size:1.08rem; line-height:1.65; }
  .buttons { display:flex; gap:14px; justify-content:center; align-items:center; flex-wrap:wrap; margin-top:28px; min-height:70px; }
  button, .file-label { border:0; border-radius:999px; padding:14px 25px; font:700 1rem inherit; font-size:1rem; cursor:pointer; transition:transform .2s,background .2s; }
  button:focus-visible, input:focus-visible, textarea:focus-visible, select:focus-visible { outline:3px solid #7b3ff2; outline-offset:3px; }
  #yesBtn { color:white; background:var(--pink); box-shadow:0 8px 22px rgba(255,95,158,.3); }
  #yesBtn:hover { background:var(--deep); }
  #noBtn { background:#f5e9ef; color:#704258; }
  .hidden { display:none !important; }
  .tiny { font-size:.88rem; opacity:.8; }
  .editor { text-align:left; margin-top:28px; padding-top:22px; border-top:1px solid #f1c9d9; }
  .editor h2 { margin:0 0 12px; }
  .fields { display:grid; grid-template-columns:1fr; gap:14px; }
  label { display:block; font-weight:650; margin-bottom:6px; }
  input[type="text"], textarea, select { width:100%; padding:12px 13px; border:1px solid #e7b7ca; border-radius:12px; background:white; color:#4e2438; font:inherit; }
  textarea { min-height:100px; resize:vertical; }
  input[type="color"] { width:56px; height:42px; border:0; background:transparent; cursor:pointer; }
  input[type="file"] { max-width:100%; }
  .field-row { display:flex; gap:14px; align-items:center; flex-wrap:wrap; }
  .secondary { background:#ffe1ec; color:#842e55; }
  .gallery { display:grid; grid-template-columns:repeat(auto-fit,minmax(130px,1fr)); gap:12px; margin:20px 0; }
  .gallery img { display:block; width:100%; aspect-ratio:1; object-fit:cover; border-radius:16px; border:3px solid white; box-shadow:0 5px 16px #9e42631c; }
  .gallery:empty { display:none; }
  .actions { display:flex; gap:10px; flex-wrap:wrap; margin-top:16px; }
  .actions button { padding:11px 17px; }
  .success { color:#a52b60; font-weight:700; }
  footer { margin-top:24px; font-size:.8rem; opacity:.65; }
  @media (min-width:600px) { .fields.two { grid-template-columns:1fr 1fr; } }
</style>
</head>
<body>
<main class="wrap">
  <section class="card" id="questionPage" aria-labelledby="questionTitle">
    <div class="heart" aria-hidden="true">💗</div>
    <h1 id="questionTitle">Will you be my Valentine?</h1>
    <p>I have a little question for you… and I’m hoping for a very special answer. 🌷</p>
    <div class="buttons">
      <button id="yesBtn" type="button">Yes! 💖</button>
      <button id="noBtn" type="button">No</button>
    </div>
    <p class="tiny" id="hint" aria-live="polite">Choose honestly — but the “Yes” button has a little crush on you.</p>
    <footer>Made with 💗</footer>
  </section>

  <section class="card hidden" id="lovePage" aria-labelledby="loveTitle">
    <div class="heart" aria-hidden="true">💞</div>
    <h1 id="loveTitle">YAY! You said yes! 💘</h1>
    <p id="loveMessage">You just made me the happiest person. I can’t wait to make sweet memories with you. 🌹</p>
    <div class="gallery" id="gallery" aria-label="Your photos"></div>
    <p class="success" id="signoff">Love, me 💌</p>

    <section class="editor" aria-labelledby="editorTitle">
      <h2 id="editorTitle">Make this page yours ✨</h2>
      <p class="tiny">Edit the message, add photos, and change the background. Changes are saved in this browser on this device.</p>
      <div class="fields">
        <div><label for="titleInput">Heading</label><input id="titleInput" type="text" value="YAY! You said yes! 💘" maxlength="100"></div>
        <div><label for="messageInput">Your message</label><textarea id="messageInput" maxlength="1200">You just made me the happiest person. I can’t wait to make sweet memories with you. 🌹</textarea></div>
        <div><label for="signoffInput">Sign-off</label><input id="signoffInput" type="text" value="Love, me 💌" maxlength="100"></div>
        <div class="fields two">
          <div>
            <label for="bgColor">Background color</label>
            <div class="field-row"><input id="bgColor" type="color" value="#fff0f5"><span class="tiny">Pick any color</span></div>
          </div>
          <div>
            <label for="bgImage">Or use a background photo</label>
            <input id="bgImage" type="file" accept="image/*">
          </div>
        </div>
        <div>
          <label for="photoInput">Add photos to your page</label>
          <input id="photoInput" type="file" accept="image/*" multiple>
          <p class="tiny">Tip: use a few favorite photos. Images are stored locally in this browser, not uploaded to a server.</p>
        </div>
      </div>
      <div class="actions">
        <button class="secondary" id="saveBtn" type="button">Save changes</button>
        <button class="secondary" id="resetBtn" type="button">Reset page</button>
        <button class="secondary" id="backBtn" type="button">Back to question</button>
      </div>
      <p class="tiny" id="saveStatus" aria-live="polite"></p>
    </section>
    <footer>Every love story is special. 💗</footer>
  </section>
</main>
<script>
(() => {
  const $ = id => document.getElementById(id);
  const questionPage = $('questionPage'), lovePage = $('lovePage');
  const yesBtn = $('yesBtn'), noBtn = $('noBtn'), hint = $('hint');
  const defaults = {
    title: 'YAY! You said yes! 💘',
    message: 'You just made me the happiest person. I can’t wait to make sweet memories with you. 🌹',
    signoff: 'Love, me 💌',
    bgColor: '#fff0f5', bgImage: '', photos: []
  };
  let data = {...defaults};
  let noClicks = 0;

  function showLovePage() {
    questionPage.classList.add('hidden');
    lovePage.classList.remove('hidden');
    window.scrollTo({top:0, behavior:'smooth'});
    render();
  }
  yesBtn.addEventListener('click', showLovePage);
  noBtn.addEventListener('click', () => {
    noClicks++;
    const scale = Math.min(1 + noClicks * 0.22, 3.1);
    yesBtn.style.transform = `scale(${scale})`;
    yesBtn.style.zIndex = '2';
    yesBtn.style.position = 'relative';
    const messages = ['Are you sure? 🥺', 'Think about the cute memories! 💕', 'The Yes button is getting braver… 💗', 'One more chance? 🌹', 'Pretty please? 💖'];
    hint.textContent = messages[Math.min(noClicks - 1, messages.length - 1)];
    noBtn.style.transform = `scale(${Math.max(1 - noClicks * 0.06, 0.65)})`;
  });
  $('backBtn').addEventListener('click', () => {
    lovePage.classList.add('hidden');
    questionPage.classList.remove('hidden');
    window.scrollTo({top:0, behavior:'smooth'});
  });

  function render() {
    $('loveTitle').textContent = data.title;
    $('loveMessage').textContent = data.message;
    $('signoff').textContent = data.signoff;
    document.body.style.backgroundColor = data.bgColor || defaults.bgColor;
    document.body.style.backgroundImage = data.bgImage
      ? `linear-gradient(rgba(255,240,247,.55),rgba(255,240,247,.55)),url("${data.bgImage}")`
      : `linear-gradient(135deg,${data.bgColor || defaults.bgColor},#ffe0eb 48%,#fff8fb)`;
    const gallery = $('gallery');
    gallery.replaceChildren();
    data.photos.forEach((src, i) => {
      const img = document.createElement('img');
      img.src = src; img.alt = `Photo ${i+1}`; gallery.appendChild(img);
    });
    $('titleInput').value = data.title;
    $('messageInput').value = data.message;
    $('signoffInput').value = data.signoff;
    $('bgColor').value = data.bgColor || defaults.bgColor;
  }

  function readImage(file) {
    return new Promise((resolve, reject) => {
      if (!file || !file.type.startsWith('image/')) return reject(new Error('Please choose an image file.'));
      const reader = new FileReader();
      reader.onload = () => resolve(reader.result);
      reader.onerror = () => reject(new Error('Could not read that image.'));
      reader.readAsDataURL(file);
    });
  }
  $('photoInput').addEventListener('change', async event => {
    const files = [...event.target.files].slice(0, 12);
    try {
      const newPhotos = await Promise.all(files.map(readImage));
      data.photos = [...data.photos, ...newPhotos].slice(0, 12);
      render();
      $('saveStatus').textContent = 'Photos added. Click Save changes to keep them in this browser.';
    } catch (e) { $('saveStatus').textContent = e.message; }
    event.target.value = '';
  });
  $('bgImage').addEventListener('change', async event => {
    try {
      data.bgImage = await readImage(event.target.files[0]);
      render();
      $('saveStatus').textContent = 'Background photo selected. Click Save changes to keep it in this browser.';
    } catch (e) { $('saveStatus').textContent = e.message; }
    event.target.value = '';
  });
  $('bgColor').addEventListener('input', e => {
    data.bgColor = e.target.value;
    data.bgImage = '';
    render();
  });
  $('saveBtn').addEventListener('click', () => {
    data.title = $('titleInput').value.trim() || defaults.title;
    data.message = $('messageInput').value.trim() || defaults.message;
    data.signoff = $('signoffInput').value.trim() || defaults.signoff;
    try {
      localStorage.setItem('valentine-page-customization', JSON.stringify(data));
      render();
      $('saveStatus').textContent = 'Saved on this device and browser! 💗';
    } catch (e) {
      $('saveStatus').textContent = 'The browser storage limit was reached. Try fewer or smaller photos.';
    }
  });
  $('resetBtn').addEventListener('click', () => {
    data = {...defaults, photos: []};
    try { localStorage.removeItem('valentine-page-customization'); } catch(e) {}
    render();
    $('saveStatus').textContent = 'Reset to the original page.';
  });
  try {
    const saved = localStorage.getItem('valentine-page-customization');
    if (saved) data = {...defaults, ...JSON.parse(saved)};
  } catch(e) {}
  render();
})();
</script>
</body>
</html>
