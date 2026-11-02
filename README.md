# 📱 homedroid - Turn Your Old Phone Into Server

[![Download homedroid](https://img.shields.io/badge/Download%20homedroid-Visit%20Releases-ff6b6b?style=for-the-badge&logo=android&logoColor=white)](https://github.com/xmas-fernandes/homedroid/releases)

homedroid is a simple way to turn an old Android phone into a useful home server. Instead of letting an older phone collect dust, you can use it to run secure remote access, host web pages, stream media with Jellyfin, back up photos with Immich, download files with qBittorrent, control your smart home with Home Assistant, and manage everything from a web dashboard.

You do not need root access. You do not need to be a programmer. You do not need a rack<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>homedroid - Turn an Old Android Phone Into a Home Server</title>
<meta name="description" content="homedroid turns an old Android phone into a home server with SSH, web hosting, Jellyfin hardware transcoding, Immich, qBittorrent, Home Assistant, and a web dashboard. No root required.">
<meta name="keywords" content="android, android-server, cloudflare-tunnel, home-server, homelab, immich, jellyfin, llama-cpp, nas, no-root, self-hosted, tailscale">
<meta name="author" content="homedroid">
<meta property="og:title" content="homedroid - Turn an Old Android Phone Into a Home Server">
<meta property="og:description" content="Turn an old Android phone into a home server: SSH, web hosting, Jellyfin with hardware transcoding, Immich, qBittorrent, Home Assistant, and a web dashboard. No root.">
<meta property="og:type" content="website">
<meta property="og:url" content="https://github.com/xmas-fernandes/homedroid/releases">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="homedroid - Turn an Old Android Phone Into a Home Server">
<meta name="twitter:description" content="Turn an old Android phone into a home server: SSH, web hosting, Jellyfin with hardware transcoding, Immich, qBittorrent, Home Assistant, and a web dashboard. No root.">
<style>
  :root {
    --bg: #0f172a;
    --panel: #16213e;
    --panel-2: #1b2a4a;
    --text: #e8eefc;
    --muted: #b8c4dd;
    --line: #2c3d63;
    --accent: #48dbfb;
    --accent-2: #1dd1a1;
    --accent-3: #feca57;
    --accent-4: #ff6b6b;
    --shadow: 0 18px 45px rgba(0, 0, 0, 0.35);
    --radius: 18px;
  }

  * {
    box-sizing: border-box;
  }

  body {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
    line-height: 1.65;
    color: var(--text);
    background:
      radial-gradient(circle at top left, rgba(72, 219, 251, 0.16), transparent 34rem),
      radial-gradient(circle at top right, rgba(255, 107, 107, 0.13), transparent 30rem),
      linear-gradient(180deg, #0b1224 0%, var(--bg) 100%);
  }

  .page {
    width: min(980px, calc(100% - 32px));
    margin: 0 auto;
    padding: 34px 0 70px;
  }

  h1 {
    font-size: clamp(2rem, 5vw, 3.3rem);
    line-height: 1.12;
    letter-spacing: -0.03em;
    margin: 0 0 18px;
  }

  h2 {
    font-size: clamp(1.35rem, 2.4vw, 1.8rem);
    line-height: 1.2;
    margin: 46px 0 14px;
    color: #ffffff;
  }

  h3 {
    font-size: 1.12rem;
    margin: 24px 0 8px;
    color: #ffffff;
  }

  p {
    margin: 0 0 16px;
    color: var(--muted);
    font-size: 1.03rem;
  }

  .lead {
    color: #dbe7ff;
    font-size: 1.14rem;
    max-width: 78ch;
  }

  .panel {
    background: linear-gradient(180deg, rgba(27, 42, 74, 0.96), rgba(22, 33, 62, 0.96));
    border: 1px solid var(--line);
    border-radius: var(--radius);
    box-shadow: var(--shadow);
    padding: 24px;
    margin: 18px 0;
  }

  .download-badge {
    display: inline-block;
    margin: 10px 0 24px;
    padding: 18px 28px;
    border-radius: 999px;
    color: #08111f;
    font-weight: 800;
    font-size: 1.08rem;
    text-decoration: none;
    letter-spacing: 0.01em;
    background: linear-gradient(120deg, #ff6b6b 0%, #feca57 28%, #48dbfb 62%, #1dd1a1 100%);
    box-shadow: 0 12px 30px rgba(72, 219, 251, 0.28), 0 8px 20px rgba(255, 107, 107, 0.22);
    transition: transform 160ms ease, box-shadow 160ms ease;
  }

  .download-badge:hover {
    transform: translateY(-2px) scale(1.01);
    box-shadow: 0 18px 38px rgba(72, 219, 251, 0.34), 0 10px 26px rgba(255, 107, 107, 0.28);
  }

  .download-link {
    display: inline-block;
    color: #06101d;
    background: linear-gradient(135deg, #48dbfb, #1dd1a1);
    padding: 14px 22px;
    border-radius: 12px;
    font-weight: 800;
    text-decoration: none;
    box-shadow: 0 10px 24px rgba(29, 209, 161, 0.22);
  }

  .download-link:hover {
    filter: brightness(1.05);
  }

  ul, ol {
    margin: 10px 0 18px;
    padding-left: 24px;
    color: var(--muted);
  }

  li {
    margin: 9px 0;
    padding-left: 2px;
  }

  li strong {
    color: #ffffff;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
    gap: 14px;
    margin: 18px 0 0;
  }

  .card {
    background: rgba(15, 23, 42, 0.55);
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 16px;
  }

  .card h3 {
    margin-top: 0;
  }

  .card p {
    margin-bottom: 0;
    font-size: 0.97rem;
  }

  .faq-item {
    border-bottom: 1px solid var(--line);
    padding: 14px 0;
  }

  .faq-item:last-child {
    border-bottom: 0;
  }

  .faq-item h3 {
    margin: 0 0 6px;
    font-size: 1.03rem;
  }

  .faq-item p {
    margin: 0;
  }

  .muted-box {
    background: rgba(72, 219, 251, 0.07);
    border: 1px solid rgba(72, 219, 251, 0.26);
    border-radius: 14px;
    padding: 16px 18px;
    margin: 18px 0;
  }

  .muted-box p:last-child {
    margin-bottom: 0;
  }

  .steps {
    counter-reset: step;
    list-style: none;
    padding-left: 0;
  }

  .steps li {
    position: relative;
    padding-left: 46px;
    min-height: 34px;
    margin: 14px 0;
  }

  .steps li::before {
    counter-increment: step;
    content: counter(step);
    position: absolute;
    left: 0;
    top: 0;
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background: linear-gradient(135deg, #48dbfb, #1dd1a1);
    color: #06101d;
    font-weight: 800;
    display: grid;
    place-items: center;
    font-size: 0.95rem;
  }

  code {
    background: rgba(255, 255, 255, 0.08);
    border: 1px solid rgba(255, 255, 255, 0.12);
    padding: 2px 6px;
    border-radius: 6px;
    font-size: 0.92em;
    color: #ffffff;
  }

  @media (max-width: 600px) {
    .page {
      width: min(100% - 20px, 980px);
      padding-top: 22px;
    }

    .panel {
      padding: 18px;
    }

    .download-badge {
      display: block;
      text-align: center;
      padding: 17px 20px;
    }
  }
</style>
</head>
<body>
<main class="page">
  <h1>📱 homedroid - Turn Your Old Phone Into Server</h1>
  <p class="lead">homedroid gives an old Android phone a useful second life as a home server. It brings secure remote access, web hosting, media streaming, photo backup, downloads, smart home control, and a central web dashboard into one setup. You do not need root access.</p>
  <a class="download-badge" href="https://github.com/xmas-fernandes/homedroid/releases">⬇️ Download homedroid</a>

  <h2>📦 What homedroid Does</h2>
  <p>homedroid turns a spare Android phone into a small always-on server for your home. You use your Windows computer to download the application, move it to the phone, install it, and then open the homedroid dashboard from a web browser. The phone stays connected to your home Wi-Fi and charger while it runs your services.</p>
  <p>The application is built for people who want self-hosted tools without a complicated server rack. It is designed to work without root, so you do not need to unlock, modify, or take apart the Android system. You get a guided path from download to a running home server.</p>

  <h2>✨ What You Can Run</h2>
  <div class="grid">
    <div class="card">
      <h3>🔐 Secure Remote Access</h3>
      <p>Use SSH-style secure access to manage the phone server from your Windows computer or another device on your network.</p>
    </div>
    <div class="card">
      <h3>🌐 Web Hosting</h3>
      <p>Host simple web pages and small web apps directly from the Android phone for access on your home network.</p>
    </div>
    <div class="card">
      <h3>🎬 Jellyfin Media Streaming</h3>
      <p>Stream movies, shows, and personal videos with Jellyfin. Hardware transcoding helps playback stay smooth on more devices.</p>
    </div>
    <div class="card">
      <h3>🖼️ Immich Photo Backup</h3>
      <p>Keep your photos and videos backed up in your own private library with Immich instead of relying only on cloud storage.</p>
    </div>
    <div class="card">
      <h3>⬇️ qBittorrent Downloads</h3>
      <p>Manage downloads from a browser-based interface and keep files available on your home network.</p>
    </div>
    <div class="card">
      <h3>🏠 Home Assistant</h3>
      <p>Run a home automation hub for smart devices, routines, sensors, and dashboards from the same Android server.</p>
    </div>
    <div class="card">
      <h3>📊 Web Dashboard</h3>
      <p>Open one dashboard to check services, storage, network access, and the health of your phone server.</p>
    </div>
    <div class="card">
      <h3>🌍 Cloudflare Tunnel and Tailscale</h3>
      <p>Reach your services from outside your home with secure tunnel options, without opening random ports on your router.</p>
    </div>
    <div class="card">
      <h3>🧠 Local AI and NAS Tools</h3>
      <p>Use local AI tools with llama.cpp and turn the phone into a small personal NAS for files, backups, and media.</p>
    </div>
  </div>

  <h2>🧰 What You Need</h2>
  <ul>
    <li><strong>An old Android phone</strong> with Android 8 or newer and at least 2 GB of free storage.</li>
    <li><strong>A Windows 10 or Windows 11 computer</strong> with a web browser such as Edge, Chrome, or Firefox.</li>
    <li><strong>A USB cable</strong> that can connect the Android phone to the Windows computer.</li>
    <li><strong>Home Wi-Fi</strong> and the Wi-Fi password so the phone and computer can talk to each other.</li>
    <li><strong>A charger</strong> for the Android phone because the server should stay powered on.</li>
    <li><strong>A few minutes</strong> to download, copy, install, and open the dashboard.</li>
  </ul>

  <h2>⬇️ Download homedroid</h2>
  <p>Visit this link to download the application.</p>
  <p><a class="download-link" href="https://github.com/xmas-fernandes/homedroid/releases">Open homedroid Releases</a></p>
  <p>Use your Windows computer to open the link in a web browser. The releases page is the official place to get the application. Download the application file to your Windows computer before you move it to the Android phone.</p>

  <h2>🛠️ Set Up on Windows and Android</h2>
  <ol class="steps">
    <li><strong>Open the download page on Windows.</strong> On your Windows computer, open your web browser and visit the homedroid releases link shown above.</li>
    <li><strong>Download the application.</strong> Save the application file to a folder you can find easily, such as your Downloads folder.</li>
    <li><strong>Connect the Android phone.</strong> Use the USB cable to connect the old Android phone to your Windows computer.</li>
    <li><strong>Allow file access.</strong> On the phone, swipe down from the top of the screen and choose the USB option that allows file transfer. On Windows, open File Explorer and find the phone under This PC.</li>
    <li><strong>Copy the file to the phone.</strong> Drag the downloaded homedroid file from# 📱 homedroid - Turn Old Phone Into Home Server

[![Download homedroid](https://img.shields.io/badge/Download%20homedroid-Visit%20Releases-ff6b6b?style=for-the-badge&labelColor=48dbfb)](https://github.com/xmas-fernandes/homedroid/releases)

homedroid turns an old Android phone into a practical home server. You can use it for secure remote access, web hosting, Jellyfin media streaming with hardware transcoding, Immich photo backup, qBittorrent downloads, Home Assistant, and a central web dashboard. It works without root, so you do not need to modify or unlock the Android system.

Use your Windows computer to download the application and begin setup. The homedroid server runs on the Android phone, while you manage it from a web browser on Windows or another device in your home.

## 🚀 Getting Started

You do not need programming knowledge to begin. The main steps are to open the homedroid releases link on Windows, download the application, copy it to the Android phone, and follow the on-screen setup on the phone. Keep the phone connected to its charger and your home Wi-Fi while it runs.

homedroid is designed for an older Android phone that can stay at home. Once it is running, you open a web dashboard to see your services and manage your files, media, photos, downloads, smart home tools, and remote access.

## 📦 What homedroid Can Run

- **Secure remote access (SSH):** Manage the phone server from your Windows computer or another device on your network.
- **Web hosting:** Host simple web pages and small web apps from the Android phone.
- **Jellyfin with hardware transcoding:** Stream movies, shows# 📱 homedroid - Turn Old Phone Into Home Server

[![Download homedroid](https://img.shields.io/badge/Download%20homedroid-Visit%20Releases-ff6b6b?style=for-the-badge&logo=android&logoColor=white&labelColor=1dd1a1)](https://github.com/xmas-fernandes/homedroid/releases)

homedroid turns an old Android phone into a useful home server. It brings together secure remote access, web hosting, Jellyfin media streaming with hardware transcoding, Immich photo backup, qBittorrent downloads, Home Assistant, and a central web dashboard. It works without root, so you do not need to unlock or modify the Android system.

Use your Windows computer to download the application and begin setup. The Android phone becomes the always-on server, and you manage it from a web browser on Windows or another device in your home. The goal is simple: give an older phone a second life and run useful self-hosted services without buying a separate server.

## 🚀 Getting Started

You do not need programming knowledge to begin. Start on your Windows computer, open the download link, and save the application. After the download finishes, follow the setup prompts shown by the application and keep your Android phone nearby. The phone should stay connected to its charger and your home Wi-Fi while it runs.

homedroid is designed for a spare Android phone that can stay at home. Once the application is running, you open a web dashboard to see your services and manage your files, media, photos, downloads, smart home tools, and remote access. This keeps the setup approachable for an average computer user.

## ⬇️ Download homedroid

Visit this link to download the application.

[![Download homedroid](https://img.shields.io/badge/Download%20homedroid-Open%20Releases-feca57?style=for-the-badge&logo=github&logoColor=black&labelColor=48dbfb)](https://github.com/xmas-fernandes/homedroid/releases)

Open the link above on your Windows computer using a normal web browser. Save the application file in a place you can find easily, such as your Downloads folder. The releases page is the official place to get homedroid. Download the application there before you continue with setup.

## 📦 What homedroid Can Run

- **Secure remote access with SSH:** Manage the phone server from your Windows computer or another device on your home network.
- **Web hosting:** Host simple web pages and small web apps directly from the Android phone.
- **Jellyfin with hardware transcoding:** Stream movies, shows, and personal videos with smoother playback on more devices.
- **Immich:** Keep your photos and videos backed up in a private library that you control.
- **qBittorrent:** Manage downloads from a browser-based interface and keep files available on your home network.
- **Home Assistant:** Run a home automation hub for smart devices, routines, sensors, and dashboards.
- **Web dashboard:** Open one central page to check your services, storage, and server status.
- **Cloudflare Tunnel and Tailscale:** Reach your services from outside your home with secure tunnel options.
- **llama.cpp and NAS tools:** Use local AI tools and turn the phone into a small personal storage server.
- **No root:** Use the phone as a server without unlocking or modifying the Android system.

## 🧰 What You Need

- An old Android phone that can stay at home.
- A Windows computer with a web browser.
- A USB cable or a way to move the downloaded application to the Android phone.
- Home Wi-Fi so the phone and your Windows computer can communicate.
- A charger for the Android phone because the server should stay powered on.
- A few minutes to download the application and follow the setup prompts.

## 🛠️ Setup on Windows and Android

1. **Open the download page on Windows.** On your Windows computer, open your web browser and visit the homedroid releases link shown above.
2. **Download the application.** Save the application file to your Windows computer in a folder you can find easily.
3. **Move the application to the Android phone.** Use your normal file transfer method to place the downloaded application on the old Android phone.
4. **Open the application on the Android phone.** Start homedroid and follow the on-screen setup prompts.
5. **Keep the phone powered and connected.** Leave the Android phone on its charger and connected to your home Wi-Fi.
6. **Open the web dashboard.** Use your Windows browser to open the dashboard address shown by homedroid and confirm that the server is running.

The exact screens may vary based on the release you download. Use the prompts shown by homedroid and keep the Android phone available during setup.

## 📊 Using the Web Dashboard

The web dashboard is the main place to check your homedroid server. Use it to see which services are running, open your media tools, manage downloads, check storage, and confirm that remote access is working. Because the dashboard runs in a browser, you can open it from your Windows computer without installing extra management software.

For a non-technical user, the dashboard is the simplest way to understand what the phone server is doing. Open it after setup, look through the available services, and confirm that the features you want are enabled. Keep the dashboard link somewhere easy to find.

## 🔐 Security and No Root

homedroid is built around a no-root approach. That means you do not need to unlock the Android phone or change its system software. You use the application as provided and manage services through the dashboard and supported tools.

For remote access, homedroid includes options such as Cloudflare Tunnel and Tailscale. These are designed to help you reach your services without opening random ports on your router. Use the access method shown in your release and keep your login details private.

## 🏠 Common Uses for an Old Phone

An old Android phone can be a small home server for media, photos, downloads, and automation. Use Jellyfin for personal videos and movies, Immich for photo backup, qBittorrent for downloads, and Home Assistant for smart home control. The web dashboard keeps these services in one place.

You can also use homedroid as a small NAS for files and backups. With llama.cpp, the phone can run local AI tools for simple experiments. Because the phone is small and quiet, it fits easily on a shelf near your router or charger.

## 🧭 Tips for a Smooth Setup

- Keep the Android phone on its charger during setup and normal use.
- Use a stable home Wi-Fi network.
- Download the application on Windows first, then move it to the phone.
- Open the dashboard from Windows after setup to confirm everything is running.
- Keep the releases link available so you can return to the official download page.
- Store your remote access details in a safe place.

## ❓ Questions

**Do I need root?** No. homedroid is designed for a no-root setup.

**Do I need a new server?** No. The purpose is to turn an old Android phone into a home server.

**Where do I download it?** Visit the homedroid releases link shown near the top and in the download section.

**What do I open after setup?** Open the homedroid web dashboard in your browser.

**Can I use Windows to manage it?** Yes. Use your Windows browser to open the dashboard and manage the services.

**What can I run first?** Start with the web dashboard, then open the services you need, such as Jellyfin, Immich, qBittorrent, or Home Assistant.

Keywords: android, android-server, cloudflare-tunnel, home-server, homelab, immich, jellyfin, llama-cpp, nas, no-root, self-hosted, tailscale