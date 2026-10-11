# Reelinsta - Project Guide (English)

## Files
- index.html : home page (tabs for Video, Photo, Reels, Story, Profile; features, how-to, FAQ)
- instagram-*-downloader.html : one page per downloader type
- how-to-download-on-iphone/android/pc.html : help guides
- about, terms, privacy, contact .html : info pages
- css/style.css, js/app.js : shared styles and logic
- tool.html  : tools for your own files (compress, MP4, MP3, GIF, resize, remove your own logo)
- backend/   : Python + Flask + FFmpeg server

## Step 1: Put the backend online (Render.com free plan)
1. Upload this whole folder to GitHub.
2. On Render.com choose New > Web Service and connect the repo.
3. Root Directory: backend, Runtime: Docker. Click Deploy.
4. You get an address like https://reelsaver.onrender.com
5. Optional: set ALLOWED_ORIGIN to your website address.

## Step 2: Connect the frontend
In tool.html AND js/app.js set:  const API_BASE = "https://reelsaver.onrender.com";
In js/app.js also set CONTACT_ENDPOINT (e.g. a Formspree URL) for the contact form.

## Step 3: Put the frontend online
GitHub repo > Settings > Pages > Branch: main, Folder: / (root) > Save.

## Test locally
    cd backend
    pip install -r requirements.txt
    python app.py     # ffmpeg must be installed

## Note
The Instagram link boxes wait for a backend (API_BASE is empty). The Instagram fetch backend is not included.
