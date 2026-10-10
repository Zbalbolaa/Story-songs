# Story Songs

Upload a photo and get song ideas for your Instagram Story.

**Live site:** 

## How it works

1. You choose a photo.
2. A free AI model (CLIP, running in your browser through Transformers.js) scores the photo against a list of moods: sunset, party, gym, beach, rainy, food, friends, city night.
3. The page shows songs for the top 3 moods from `songs.json`, with a **Copy name** button and YouTube and Spotify search links.
4. In Instagram, open the Story sticker menu, choose **Music**, and paste the song name.

Instagram has no public API to add music to Stories automatically, so the song is added manually.

## Privacy

Everything runs on your device. The photo is never uploaded, and there is no server, no API key and no cost.

## Notes

- The first visit downloads the model (about 100 to 150 MB). After that it is cached by the browser.
- Song availability in Instagram's music library depends on the country, so some songs may not appear.

## Run locally

```bash
git clone https://github.com/Zbalbolaa/story-songs.git
cd story-songs
python -m http.server 8000
```

Then open http://localhost:8000. The model will not load if you open `index.html` by double-clicking it.

## Add or edit songs

Edit `songs.json`. Each mood is a list of songs:

```json
{"title": "Song name", "artist": "Artist", "t": "ma"}
```

Use `"t": "ma"` for Moroccan songs and `"t": "ar"` for other Arabic songs. Leave `t` out for international songs.

## Built with

Plain HTML and JavaScript, [Transformers.js](https://github.com/xenova/transformers.js) and the CLIP model `Xenova/clip-vit-base-patch32`. Hosted on GitHub Pages.
