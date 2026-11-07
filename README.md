# GK Gks — Birthday Website

A responsive birthday microsite inspired by the supplied Netlify reference. It includes a live countdown, age calculator, approximate moon-phase display, interactive candles, memories gallery, and birthday wishes.

## 1. Personalize it
Open `script.js` and edit the `CONFIG` object at the top:

```js
const CONFIG = {
  name: "Her",
  birthday: "2006-02-02", // YYYY-MM-DD
  signature: "GK Gks",
  musicFile: "assets/birthday-song.mp3"
};
```

Change the name, date, and signature. Put an MP3 named `birthday-song.mp3` in the `assets` folder, or set `musicFile` to an empty string.

## 2. Add her throwback photos and videos to the public gallery
1. Put image files (JPG, PNG, WEBP) and video files (MP4 recommended) inside `assets/memories/`.
2. Open the `memories.json` file in the project root and add entries like these (change the filenames and captions to match your files):

```json
[
  { "type": "image", "src": "assets/memories/old-photo-1.jpg", "caption": "One of the sweetest throwbacks" },
  { "type": "image", "src": "assets/memories/old-photo-2.jpg", "caption": "A little memory" },
  { "type": "video", "src": "assets/memories/memory-clip.mp4", "caption": "A moment to replay" }
]
```

Every visitor sees these featured memories on the default webpage. Keep videos reasonably compressed (ideally under 20 MB each) so the page loads smoothly on mobile. The photo gallery opens images in a full-screen viewer; videos play inline.

**Important:** Do not add private or embarrassing photos/videos without her permission. Anyone with the public website link can view featured media.

## 3. Run it
Open `index.html` in a browser. For best results, use a local static server (for example VS Code Live Server).

## 4. Publish on Netlify
1. Extract the ZIP.
2. Open Netlify and choose **Add new site → Deploy manually**.
3. Drag the extracted project folder (the folder containing `index.html`) into the deploy area.
4. Netlify will publish it and provide a shareable URL.

## Important storage note
The featured gallery loads from `memories.json`, so all visitors see the same included photos/videos. The optional Add a memory button uses IndexedDB in the visitor’s browser; wishes use localStorage. Those personal uploads and wishes are stored only on that device/browser and are **not automatically visible to other visitors**. A shared public gallery/wall where everyone sees everyone else's uploads needs a backend such as Supabase or Firebase, including storage rules and moderation. Do not collect public uploads without appropriate safeguards.

## Included files
- `index.html` — page content and sections
- `style.css` — responsive styling and glassmorphism
- `script.js` — countdown, age, lunar estimate, candles, memories and wishes
- `memories.json` — list the photos/videos shown to every visitor
- `assets/memories/` — public photos and video clips
- `assets/` — add your music and other static assets here

The lunar values are decorative approximations, not an astronomical ephemeris.
