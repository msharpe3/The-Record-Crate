# The Record Crate

A vinyl collection tracker and playlist builder styled like an old indie record store, with milk crates on wooden shelves, divider cards, Edison bulbs and a lightbox sign.

**Live app:** https://msharpe3.github.io/The-Record-Crate/

It's a single `index.html` with no build step, hosted on GitHub Pages. It works best on iPhone: open it in Safari and tap **Share → Add to Home Screen**.

## Features

### Crates
- **Shelf wall:** every genre gets its own colored milk crate, and mixtapes have their own crate. Tap a crate to pull it off the shelf.
- **Flip through records** the way you would in a real crate. Swipe down to flip forward, swipe up to go back, and tap the front record to pull it out.
- A–Z divider cards, records in plastic sleeves, and a vinyl that slides out of its jacket on the detail view.
- Search across the whole collection.

### Adding records
- **Discogs import:** pull your entire Discogs collection in one tap, with covers, year, label, genre and media/sleeve condition. Running it again only adds new records.
- **Search:** Discogs (exact pressings) when a token is saved, otherwise Apple's album catalog.
- **Manual entry,** including uploading a photo of your own sleeve.
- Fields: condition (M–P grading), crate/genre, label, year and notes.

### Dig for a Vibe
- Describe a vibe ("garage workout"), name artists it should sound like ("Beastie Boys, Run-DMC") and pick mood tags. The app pulls a stack of similar tracks.
- Built on Last.fm's similar artists, top tracks and mood tags. There's no AI involved.
- Cover art, 30-second previews and Apple Music links come from Apple's iTunes Search API.
- Artists you own on vinyl are tagged **in your crate**.
- Remove tracks, reshuffle, and save the result as a mixtape.

### Mixtapes
- **Send to Apple Music** for free through TuneMyMusic: copy the track list, paste it, and pick Apple Music. You can also download a CSV for Soundiiz.
- **Cover art:** Unsplash photo search, an auto 2×2 collage of album covers, or your own uploaded image (Pinterest saves work too).

### Sync & backup
- **Sync Devices:** links your phone and computer through the same Firebase database as The Archive, using its own sync code. Records, mixtapes and API keys sync both ways.
- **Export/Import** a JSON backup.
- Without sync, everything stays on the device in `localStorage`.

## Setup (Back Room)

All of these are free. Each one has a "How to get it" guide inside the app.

| Key | Used for | Where to get it |
|---|---|---|
| Last.fm API key | Dig for a Vibe (required) | [last.fm/api/account/create](https://www.last.fm/api/account/create) |
| Discogs username + token | Collection import, vinyl search | [discogs.com/settings/developers](https://www.discogs.com/settings/developers) |
| Unsplash access key | Mixtape cover photos | [unsplash.com/oauth/applications](https://unsplash.com/oauth/applications) |
| Firebase config | Sync between devices | Copy it from The Archive → Sync Devices |

## Tech notes
- Plain HTML, CSS and JS in one file. All textures (brick, wood grain, plastic) are CSS and inline SVG, with no image assets.
- Fonts: Bowlby One, Permanent Marker, Courier Prime and Special Elite (Google Fonts).
- Synced data lives in the Firestore `households` collection as `recordcrate-<code>`. Uploaded photos are left out of sync if they'd push the document past Firestore's 1 MB limit.

---
Created by Mike Sharpe
