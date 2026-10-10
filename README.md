
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#fff0f5">
  <title>Will You Be My Valentine? 💗</title>

  <style>
    :root {
      --pink: #ff4f87;
      --dark-pink: #e82e70;
      --text: #66334b;
      --card: rgba(255, 255, 255, 0.92);
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background: #fff0f5;
      background-size: cover;
      background-position: center;
      background-attachment: fixed;
      transition: background-color 0.3s;
    }

    button, input, textarea {
      font: inherit;
    }

    button {
      cursor: pointer;
      border: none;
      border-radius: 12px;
      padding: 12px 20px;
      transition: transform 0.2s, background 0.2s;
    }

    button:focus-visible, input:focus-visible,
    textarea:focus-visible {
      outline: 3px solid #d63384;
      outline-offset: 3px;
    }

    button:hover {
      filter: brightness(0.97);
    }

    .screen {
      min-height: 100vh;
      padding: 24px 16px 40px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .hidden {
      display: none !important;
    }

    .card {
      width: 100%;
      max-width: 680px;
      padding: 28px 22px;
      background: var(--card);
      border: 1px solid rgba(255, 160, 190, 0.55);
      border-radius: 24px;
      box-shadow: 0 12px 45px rgba(160, 60, 100, 0.13);
      text-align: center;
      backdrop-filter: blur(8px);
    }

    .heart {
      font-size: 58px;
      margin: 5px;
      animation: heartbeat 1.3s infinite;
    }

    @keyframes heartbeat {
      0%, 100% { transform: scale(1); }
      50% { transform: scale(1.12); }
    }

    h1 {
      color: var(--dark-pink);
      line-height: 1.25;
    }

    p {
      line-height: 1.7;
      white-space: pre-wrap;
      overflow-wrap: anywhere;
    }

    .buttons {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-wrap: wrap;
      gap: 14px;
      margin: 25px 0 10px;
    }

    #yesBtn {
      background: var(--pink);
      color: white;
      font-weight: bold;
      font-size: 19px;
      position: relative;
      z-index: 2;
    }

    #noBtn {
      background: #fff;
      color: var(--dark-pink);
      border: 2px solid #ffc1d5;
    }

    .hint {
      font-size: 13px;
      opacity: 0.75;
    }

    .primary {
      background: var(--pink);
      color: white;
      font-weight: bold;
    }

    .secondary {
      background: #ffe0eb;
      color: #8b3156;
    }

    .editor {
      width: 100%;
      max-width: 760px;
      margin-top: 22px;
      padding: 22px;
      background: var(--card);
      border-radius: 20px;
      box-shadow: 0 8px 30px rgba(100, 30, 70, 0.12);
    }

    .editor h2 {
      margin-top: 0;
      color: var(--dark-pink);
    }

    .field {
      display: flex;
      flex-direction: column;
      gap: 7px;
      text-align: left;
      margin: 16px 0;
    }

    .field label {
      font-weight: bold;
      font-size: 14px;
    }

    input[type="text"], textarea {
      width: 100%;
      padding: 12px;
      border: 1px solid #edb8cb;
      border-radius: 10px;
      background: white;
      color: #49273a;
    }

    textarea {
      min-height: 115px;
      resize: vertical;
    }

    input[type="color"] {
      width: 100%;
      height: 45px;
      border: none;
      background: transparent;
      cursor: pointer;
    }

    input[type="file"] {
      width: 100%;
      max-width: 100%;
      font-size: 14px;
    }

    .gallery {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 12px;
      margin: 22px 0;
    }

    .gallery img {
      display: block;
      width: 100%;
      height: 210px;
      object-fit: cover;
      border-radius: 14px;
      background: #ffe4ed;
    }

    .gallery:empty {
      display: none;
    }

    .editor-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      margin-top: 20px;
    }

    .editor-buttons button {
      flex: 1 1 140px;
    }

    #saveStatus {
      font-size: 13px;
      overflow-wrap: anywhere;
    }

    footer {
      text-align: center;
      padding: 20px 10px;
      font-size: 12px;
    }

    @media (max-width: 420px) {
      .card {
        padding: 24px 16px;
      }

      .gallery img {
        height: 155px;
      }

      .editor {
        padding: 17px;
      }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
      }
    }
  </style>
</head>

<body>

  <!-- FIRST PAGE -->
  <main id="questionScreen" class="screen">
    <section class="card">
      <div class="heart" aria-hidden="true">💗</div>

      <h1>Will You Be My Valentine?</h1>
      <p>I have a little question for you... 🌷</p>

      <div class="buttons">
        <button id="yesBtn" class="primary" type="button">
          Yes! 💖
        </button>

        <button id="noBtn" type="button">
          No 🙈
        </button>
      </div>

      <p id="hint" class="hint">
        Choose wisely! Hehe 💕
      </p>
    </section>
  </main>

  <!-- SECOND PAGE -->
  <main id="loveScreen" class="screen hidden">
    <section class="card">
      <div class="heart" aria-hidden="true">💞</div>
      <h1 id="pageTitle">Yay! You said YES! 💗</h1>

      <p id="loveMessage">You just made my day! I'm so happy you said yes. Every moment with you is special, and I can't wait to make more beautiful memories together. 🌷</p>

      <p id="loveSignoff">With all my love, always. 💌</p>

      <div id="gallery" class="gallery"></div>

      <button id="backBtn" class="secondary" type="button">
        ← Back
      </button>
    </section>

    <!-- PERSONALIZATION PANEL -->
    <section class="editor">
      <h2>Customize Your Love Page 💌</h2>
      <p class="hint">
        Edit your message, add pictures, or change the background.
      </p>

      <div class="field">
        <label for="titleInput">Page title</label>
        <input id="titleInput" type="text"
          maxlength="120"
          placeholder="Yay! You said YES! 💗">
      </div>

      <div class="field">
        <label for="messageInput">Your love message</label>
        <textarea id="messageInput" maxlength="5000"
          placeholder="Write your heartfelt message here..."></textarea>
      </div>

      <div class="field">
        <label for="signoffInput">Your sign-off</label>
        <input id="signoffInput" type="text"
          maxlength="300"
          placeholder="With all my love, always. 💌">
      </div>

      <div class="field">
        <label for="photoInput">Add photos (up to 12 total)</label>
        <input id="photoInput" type="file"
          accept="image/*" multiple>
        <p class="hint">
          For better performance, use small JPG or WebP images.
        </p>
      </div>

      <div class="field">
        <label for="bgColor">Background color</label>
        <input id="bgColor" type="color" value="#fff0f5">
      </div>

      <div class="field">
        <label for="bgImage">Or choose a background photo</label>
        <input id="bgImage" type="file" accept="image/*">
      </div>

      <div class="editor-buttons">
        <button id="saveBtn" class="primary" type="button">
          Save changes 💗
        </button>

        <button id="resetBtn" class="secondary" type="button">
          Reset
        </button>
      </div>

      <p id="saveStatus" role="status" aria-live="polite">
        Your changes are ready to customize.
      </p>
    </section>

    <footer>Made with love 💗</footer>
  </main>

  <script>
    (() => {
      "use strict";

      const $ = id => document.getElementById(id);

      const defaults = {
        title: "Yay! You said YES! 💗",
        message: "You just made my day! I'm so happy you said yes. Every moment with you is special, and I can't wait to make more beautiful memories together. 🌷",
        signoff: "With all my love, always. 💌",
        bgColor: "#fff0f5",
        bgImage: "",
        photos: []
      };

      let data = {
        ...defaults,
        photos: []
      };

      let yesSize = 19;
      const maxPhotos = 12;
      const storageKey = "valentine-page-customization";

      function render() {
        $("pageTitle").textContent = data.title;
        $("loveMessage").textContent = data.message;
        $("loveSignoff").textContent = data.signoff;

        document.body.style.backgroundColor =
          data.bgColor || defaults.bgColor;

        if (data.bgImage) {
          document.body.style.backgroundImage =
            'url("' + data.bgImage + '")';
        } else {
          document.body.style.backgroundImage = "none";
        }

        const gallery = $("gallery");
        gallery.replaceChildren();

        data.photos.forEach((src, i) => {
          const img = document.createElement("img");
          img.src = src;
          img.alt = "Photo " + (i + 1);
          img.loading = "lazy";
          gallery.appendChild(img);
        });

        $("titleInput").value = data.title;
        $("messageInput").value = data.message;
        $("signoffInput").value = data.signoff;
        $("bgColor").value = data.bgColor || defaults.bgColor;
      }

      function readImage(file) {
        return new Promise((resolve, reject) => {
          if (!file || !file.type.startsWith("image/")) {
            reject(new Error("Please choose an image file."));
            return;
          }

          const reader = new FileReader();

          reader.onload = () => {
            if (typeof reader.result === "string") {
              resolve(reader.result);
            } else {
              reject(new Error("Could not read that image."));
            }
          };

          reader.onerror = () => {
            reject(new Error("Could not read that image."));
          };

          reader.readAsDataURL(file);
        });
      }

      function showLovePage() {
        $("questionScreen").classList.add("hidden");
        $("loveScreen").classList.remove("hidden");
        window.scrollTo({ top: 0, behavior: "smooth" });
      }

      function showQuestionPage() {
        $("loveScreen").classList.add("hidden");
        $("questionScreen").classList.remove("hidden");
        window.scrollTo({ top: 0, behavior: "smooth" });
      }

      $("yesBtn").addEventListener("click", () => {
        showLovePage();
      });

      $("noBtn").addEventListener("click", () => {
        yesSize = Math.min(yesSize + 10, 100);
        $("yesBtn").style.fontSize = yesSize + "px";
        $("yesBtn").style.padding =
          (12 + yesSize / 4) + "px " +
          (20 + yesSize / 3) + "px";

        $("hint").textContent =
          "Are you sure? The YES button keeps growing! 💗";
      });

      $("backBtn").addEventListener("click", () => {
        showQuestionPage();
      });

      $("photoInput").addEventListener("change", async event => {
        const files = Array.from(event.target.files || []);
        const remaining = maxPhotos - data.photos.length;

        if (remaining <= 0) {
          $("saveStatus").textContent =
            "You already have 12 photos. Reset the page to start over.";
          event.target.value = "";
          return;
        }

        const selected = files.slice(0, remaining);

        try {
          const newPhotos = await Promise.all(
            selected.map(readImage)
          );

          data.photos = [...data.photos, ...newPhotos];
          render();

          $("saveStatus").textContent =
            "Photos added. Click Save changes to save them in this browser.";

          if (files.length > remaining) {
            $("saveStatus").textContent +=
              " Only the first " + remaining + " selected photos were added.";
          }
        } catch (error) {
          $("saveStatus").textContent = error.message;
        }

        event.target.value = "";
      });

      $("bgImage").addEventListener("change", async event => {
        const file = event.target.files &&
          event.target.files[0];

        if (!file) return;

        try {
          data.bgImage = await readImage(file);
          render();

          $("saveStatus").textContent =
            "Background photo selected. Click Save changes.";
        } catch (error) {
          $("saveStatus").textContent = error.message;
        }

        event.target.value = "";
      });

      $("bgColor").addEventListener("input", event => {
        data.bgColor = event.target.value;
        data.bgImage = "";
        render();
      });

      $("saveBtn").addEventListener("click", () => {
        data.title =
          $("titleInput").value.trim() || defaults.title;

        data.message =
          $("messageInput").value.trim() || defaults.message;

        data.signoff =
          $("signoffInput").value.trim() || defaults.signoff;

        data.bgColor =
          $("bgColor").value || defaults.bgColor;

        try {
          localStorage.setItem(
            storageKey,
            JSON.stringify(data)
          );

          render();

          $("saveStatus").textContent =
            "Saved on this device and browser! 💗";
        } catch (error) {
          $("saveStatus").textContent =
            "Could not save. Your photos may be too large. Try smaller images and save again.";
        }
      });

      $("resetBtn").addEventListener("click", () => {
        data = {
          ...defaults,
          photos: []
        };

        try {
          localStorage.removeItem(storageKey);
        } catch (error) {
          // The page can still reset if storage is unavailable.
        }

        $("yesBtn").style.fontSize = "";
        $("yesBtn").style.padding = "";
        yesSize = 19;

        render();

        $("saveStatus").textContent =
          "Reset to the original page.";
      });

      try {
        const saved = localStorage.getItem(storageKey);

        if (saved) {
          const parsed = JSON.parse(saved);

          if (parsed && typeof parsed === "object") {
            data = {
              ...defaults,
              ...parsed,
              photos: Array.isArray(parsed.photos)
                ? parsed.photos.slice(0, maxPhotos)
                : []
            };
          }
        }
      } catch (error) {
        data = {
          ...defaults,
          photos: []
        };
      }

      render();
    })();
  </script>
</body>
</html>
