# DWEEB//OS

> A tiny purple desktop-shaped universe living inside a website.

DWEEB//OS is a static, interactive website built for GitHub Pages. It has a music player, animated interface, living text, browser-saved trophies, mini-games, seasonal surprises, customization settings, and secrets for visitors to discover.

There is no build step and no backend. The site is designed to be edited, personalized, and hosted as a static website.

---

## Contents

- [Project at a glance](#project-at-a-glance)
- [Feature catalogue](#feature-catalogue)
- [Keyboard controls](#keyboard-controls)
- [Trophies and achievements](#trophies-and-achievements)
- [Secrets and easter eggs](#secrets-and-easter-eggs)
- [Seasonal events](#seasonal-events)
- [Personalizing the site](#personalizing-the-site)
- [Assets and file structure](#assets-and-file-structure)
- [Save data and privacy](#save-data-and-privacy)
- [Updates and caching](#updates-and-caching)
- [Hosting and going live](#hosting-and-going-live)
- [Credits, copyright, and reuse](#credits-copyright-and-reuse)
- [Changelog](#changelog)

---

## Project at a glance

| Detail | Information |
|---|---|
| Project | DWEEB//OS |
| Type | Static interactive website |
| Hosting | GitHub Pages-compatible |
| Build step | None |
| Backend | None required |
| Main configuration | `js/config.js` |
| Visitor data | Stored locally in the visitor's browser |
| Main technologies | HTML, CSS, and JavaScript |

DWEEB//OS is both a personal website and a little playground. Its categories can hold a portfolio, archive, writing, music, games, favorites, ideas, and whatever else the site owner wants to share.

## Feature catalogue

This is a catalogue of the features currently documented in the project. Individual options can be disabled, customized, or left unused in `js/config.js`.

### Interface and navigation

- A desktop-inspired, app-like interface.
- Ten configurable top-level categories, each with its own subcategories.
- Category and subcategory icons supplied as PNG files.
- A generated purple-tile fallback for missing category icons.
- Optional custom pictures for top-bar buttons.
- Keyboard navigation with arrow keys, Enter, and other shortcuts.
- Mobile-friendly interaction, including swipe-based navigation and touch-accessible secrets.
- URL hashes that can remember the current section, such as `#media/games`.
- A locked-category placeholder for sections that are not ready to open.
- Toast messages for menu items without links.
- Support for external HTTP(S) links and `mailto:` links.
- A custom intro video, plus a rare alternate intro.
- A custom site title, description, sharing image, and search-engine metadata.

### Intro and personality

- A splash intro that introduces the site.
- A configurable chat bot that speaks on its own.
- Responses to words typed by visitors.
- Special responses to certain words and commands.
- Optional playful scolding lines for swear words.
- A configurable name in the swear-word response.
- A chance for the bot to sing along with the currently playing song.
- Monthly chat lines.
- Optional email invitation line. Since this address is public, a throwaway address is recommended.
- Animated text emotions, allowing dialogue to look happy, angry, shy, spooky, sleepy, and much more.
- Easter eggs that can be triggered by typing certain words.

### Music player

- A configurable playlist with song title, artist, album, and optional lyrics.
- Individual cover art for songs.
- Play and pause controls.
- Next and previous track controls.
- Seeking through a track.
- Volume control and mute.
- Shuffle and loop modes.
- Fullscreen mode.
- Optional lyrics that appear line by line.
- Optional timestamped lyrics using `[m:ss]` prefixes.
- Bot singing that can follow the selected song's lyrics.
- Audio-reactive visuals throughout the site.
- A trophy-unlock sound effect, if a valid `audio/trophy.mp3` is supplied.
- Support for replacing audio by changing the filename, helping avoid stale browser-cached tracks.

Only use lyrics you wrote yourself or have permission to reproduce.

### Audio-reactive visuals

- Beat-reactive interface elements.
- Adjustable reaction strength and sensitivity.
- Floating particles and glow effects.
- A calm mode for visitors who prefer fewer visual reactions.
- Power mode in Settings.
- Visual reactions that can be adjusted to suit the visitor's device and preference.

### Living text and emotions

Any line spoken by the bot can include emotion tags. A tag affects the words after it until another tag or a reset tag appears.

Examples:

- `HELLO <angry>WORLD`
- `Hello <shy>world`
- `i am <sad>fine<n> really`
- `wait for it <wait> <excited>NOW`

Supported emotion tags and aliases:

| Tag | Effect | Aliases |
|---|---|---|
| `<angry>` | Red, hard-shaking text | `mad`, `rage`, `furious` |
| `<shy>` | Tiny, trembling text typed slowly | `timid`, `bashful` |
| `<sad>` | Blue, drooping text typed slowly | `cry`, `down`, `blue` |
| `<happy>` | Yellow, bouncing text | `joy`, `glad`, `yay` |
| `<excited>` | Large, gold, jiggling text typed quickly | `hype`, `yippee` |
| `<scared>` | Pale text that shivers quickly | `afraid`, `fear`, `terrified` |
| `<whisper>` | Tiny, faded, italic text typed slowly | `quiet`, `psst`, `secret` |
| `<yell>` | Huge, pulsing text typed quickly | `loud`, `shout`, `scream` |
| `<sleepy>` | Dim, swaying text typed very slowly | `tired`, `yawn`, `sleep` |
| `<love>` | Pink, heartbeat-style text | `heart`, `crush`, `blush` |
| `<silly>` | Wobbling text with rainbow colours | `goofy`, `wacky`, `derp` |
| `<spooky>` | Purple glow and flickering | `ghost`, `creepy`, `eerie` |
| `<dizzy>` | Wavy text | `drunk`, `spin`, `wavy` |
| `<glitch>` | Monospace text, cyan/magenta split, twitching | `error`, `bug`, `broken` |
| `<cold>` | Icy-blue, shivering text | `freeze`, `brr`, `chilly` |
| `<rich>` | Shimmering gold text | `gold`, `fancy`, `shiny` |
| `<sneaky>` | Small, italic text sliding sideways | `sly`, `plotting`, `smirk` |
| `<nervous>` | Jittery text | `anxious`, `worried`, `sweat` |
| `<proud>` | Gold, puffed-up text | `smug`, `boast` |
| `<sing>` | Blue text bobbing like a melody | `music`, `melody`, `la` |

Use `<n>`, `<normal>`, or `</>` to reset the emotion. `<wait>` pauses the typing effect, and `<wait2>` pauses for twice as long. Unknown tags are displayed as ordinary text.

Type `emotions` on the site to see the bot demonstrate the emotions. To add a new emotion, edit `js/emotion.js` and add the matching `.em-yourname` rule in `css/style.css`.

### Arcade

The **GAMES** button opens a collection of six games:

- Rhythm
- Snake
- Pong
- Tetris
- Breakout
- 2048

The arcade takes over the screen while a game is active. The background, particles, and beat reactions turn off during play, while the music player stays available. Leaving a game restores the normal site visuals.

Available game modes documented in the project:

| Game | Modes |
|---|---|
| Snake | Classic, Wrap, Speed, Rocks |
| Pong | Easy, Normal, Hard, 2 Player |
| Tetris | Marathon, Sprint, Ultra |
| Breakout | Classic, Hard, Zen |
| 2048 | 4×4, 5×5, 3×3 |
| Rhythm | Charts a selected song by listening to its audio file |

Rhythm mode uses audio from `audio/<file>` when a song is selected. Incorrect taps reduce accuracy, so repeatedly pressing keys is not a reliable way to get a perfect result.

Game scores are saved in the visitor's browser. To add a game or mode, use the existing `G.add({...})` pattern in `js/games-arcade.js`.

### Trophies and achievements

- A TROPHIES window with collectible achievements.
- Bronze, silver, gold, platinum, rare, and locked trophy artwork.
- Secret achievements that display `???` until unlocked.
- An unlock sound when a valid trophy sound file is supplied.
- Browser-local save data, including time on site, visits, most-played song, and scores.
- A save-data delete option.
- Seasonal and event-related trophies.
- A rare one-in-a-billion trophy intended to be verified by a screen recording if someone contacts the site owner.

The exact trigger for every trophy is defined in `js/trophies.js`. Achievement names are catalogued below, but secret triggers are intentionally not revealed here.

### Visitor settings

The **SETTINGS** button opens a customization window. Visitors can change:

- Colour presets.
- Hue, intensity, and brightness.
- Beat reaction and sensitivity.
- Floating dots and glow.
- Calm mode.
- Start muted.
- Autoplay.
- Skip intro.
- Chat bot on or off.
- Chat bot chattiness.
- Seasonal decorations.
- Jump scares.
- Eyes following the cursor.
- Trophy unlock sound.
- Power mode.

Settings are stored in the visitor's own browser using `localStorage` under the `dw-set` key. Some settings require a refresh, and the window provides a REFRESH button when needed. Colour changes shift the site's stylesheet while preserving greys, whites, golds, and reds.

### Living visitor counter and eyes

- A visitor-eyes counter can be configured through GoatCounter.
- The `?me=1` query can be used in your own browser to skip counting your visits.
- Visitors can click the eyes.
- After enough clicks, the eyes may wake up.
- Awake eyes follow the cursor, blink, fall asleep, and react to clicks.
- The eyes artwork is supplied in `icons/eyes.png`.

### Seasonal decorations and events

- Valentine's Day decorations.
- Halloween decorations and a spider encounter.
- Christmas tree interactions.
- New Year fireworks, confetti, and streamers.
- Season-specific bot dialogue.
- Seasonal trophies.
- Optional Halloween jumpscare image and sound.
- A force option for previewing a season during development.
- Seasonal decorations can be disabled in configuration or through visitor settings.

### Changelog and updates

- A CHANGELOG window accessible from the top bar.
- A blinking indicator when a visitor has not opened the newest changelog entry.
- A configurable version label beside `DWEEB//OS`.
- A season label that can replace the normal version label during seasonal events.

---

## Keyboard controls

| Key | Action |
|---|---|
| Arrow keys or `<` / `>` | Navigate |
| Enter | Open the selected item |
| Space | Play or pause music |
| N / P | Next / previous song |
| `[` / `]` | Seek backward / forward by 10 seconds |
| `-` / `+` | Lower / raise volume |
| M | Mute / unmute |
| S | Shuffle |
| L | Loop |
| F | Fullscreen |
| H or `?` | Show help |

Letter shortcuts wait approximately 0.3 seconds before firing, reducing the chance that typing a word accidentally activates a control.

## Trophies and achievements

Trophy definitions live near the top of `js/trophies.js`. Set `secret: true` on a trophy to hide its name as `???` until it is unlocked.

### Trophy artwork tiers

Place the following PNG files in `icons/`:

- `bronze.png`
- `silver.png`
- `gold.png`
- `plat.png` or `platinum.png`
- `rare.png`
- `locked.png`

Each trophy uses the artwork for its tier. Missing trophy images do not get generated fallbacks.

### Achievement index

The project currently documents these trophy IDs. Some IDs may be secrets, special events, or challenge-specific trophies. Their exact unlock conditions should be checked in `js/trophies.js`.

`welcome`, `dj`, `tourist`, `hopper`, `regular`, `devoted`, `longhaul`, `arcade`, `snake15`, `tetris10`, `pongwin`, `breakout`, `fivetwelve`, `rhythm`, `rhythmS`, `fullcombo`, `twentyfortyeight`, `potty`, `konami`, `alone`, `existential`, `poke`, `alive`, `night`, `commit`, `spooky`, `merry`, `newyear`, `valentine`, `spin`, `ouch`, `mutiny`, `onemore`, `ghosted`, `scare`, `treehug`, `rare`, `plat`, and `birthday` (when a birthday is configured).

### Secret achievements

Some achievements are deliberately hidden until unlocked. The catalogue above does not disclose their secret triggers, and the game itself may reveal them only after a visitor earns them.

If you want to keep a secret achievement truly secret, avoid putting its exact condition in public-facing documentation or in a public changelog. The browser code is still downloadable, so this is a playful discovery system rather than secure anti-cheat protection.

### Birthday trophy

A birthday trophy and message can be configured in `js/config.js` using a month and day:

```js
birthday: { m: 5, d: 17 }
```

Use the month number and day number for the date you want to configure. A forced seasonal preview does not award that season's trophy.

### Save data

The TROPHIES window includes a SAVE DATA tab with:

- Time spent on the site.
- Visit count.
- Most-played song.
- Game scores.
- A delete option for the saved data.

Everything is stored in the visitor's browser. It is not sent to a DWEEB//OS backend. Because the data is local and the source is available to visitors, it can be edited by a determined user.

---

## Secrets and easter eggs

DWEEB//OS includes discoverable interactions, including:

- Type `hello`.
- Type `jams`.
- Type `sing`.
- Type `emotions`.
- Try the Konami code.
- Hold the album cover.
- Poke the chat bot's text.
- Mash the mute button.
- Loop one song three times.
- Try the sequence: Up, Up, Down, Down, Left, Right, Left, Right.
- Find the seasonal ghost.
- Catch the escaped Halloween spider.
- Interact with the Christmas tree.
- Discover the eyes' wake-up behaviour.

Some of these actions are tied to achievements. The exact outcomes can change as the project develops, so treat this list as a trailhead rather than a complete spoiler guide.

## Seasonal events

Season logic lives in `js/seasons.js`, while extra seasonal effects live in `js/seasonfx.js`.

### Seasonal calendar

The current configuration supports these events:

| Event | Decorations |
|---|---|
| Valentine's Day | Heart bunting and a large beating heart that can be clicked |
| Halloween | Cobwebs, spider behaviour, and an optional jumpscare |
| Christmas | A clickable tree that cycles through image/GIF states |
| New Year | Fireworks, confetti, and streamers |

The documented full-month schedule is:

- Valentine's Day: all of February.
- Halloween: all of October.
- Christmas: December 1–30.
- New Year: December 31 through January 7.

The dates can be changed near the top of `js/seasons.js`. Seasonal trophies only unlock when the visitor actually visits during the relevant period. For testing, add `force: 'halloween'`, `force: 'xmas'`, `force: 'valentine'`, or `force: 'newyear'` to `DW.seasons` in `js/config.js`, then remove it after testing. A forced season never awards its trophy.

### Halloween assets

Put these files in the `seasons/` folder:

- `web.png`: a cobweb drawn in the upper-left corner. The site flips it for other corners, the player, and windows.
- `spider.png`: the spider, drawn facing up. The same artwork is used for hanging, falling, climbing, and running.
- `jumpscare.png`: optional full-screen jumpscare image. If absent, `spider.png` is used instead.

Also supply `audio/jumpscare.mp3` for the jumpscare sound.

The spider has a configurable chance to fall off its thread and run around the screen for roughly 20 seconds. Clicking it triggers the jumpscare, after which the bot laughs. The documented default is one chance in nine per click.

Example configuration:

```js
DW.seasonFx = {
  runChance: 9,
  jumpscare: 'audio/jumpscare.mp3',
  volume: 0.9,
  dir: 'seasons/'
};
```

### Christmas assets

- `seasons/tree.png`: the default tree image.
- `seasons/tree1.gif`, `seasons/tree2.gif`, `seasons/tree3.gif`: optional states cycled by clicking the tree.

Missing seasonal images simply do not appear.

---

## Personalizing the site

Most customization happens in `js/config.js`.

### Menu and categories

`DW.menu` defines the categories and subcategory items. Items can point to URLs, and an empty link produces a "no link yet" toast. Only HTTP(S) and `mailto:` links are supported. A dash in an item name is displayed as a space, so `reach-out` becomes `REACH OUT`.

A category with `subs: {}` is locked and has nothing to open. A category's `label` can replace the text shown under its icon.

### Playlist

`DW.playlist` maps audio filenames to their metadata. Example shape:

```js
'music1.mp3': {
  title: 'Song title',
  artist: 'Artist name',
  album: 'Album name',
  lyrics: ['First line', '[0:12] Second line']
}
```

Place the matching cover image at `covers/music1.png`. Lyrics can be an array or a multiline string, with one line per row. A `[m:ss]` prefix can time a lyric line to the song.

### Splash bot

`DW.splash` controls the bot's dialogue and behaviour. Optional settings include `lines`, `scolds`, `every`, `singChance`, and `mailChance`. Leave `email: ''` unless you want the public email invitation line. The email address will be visible to all visitors.

### Visitor counter

Set `DW.counter.code` to your GoatCounter site code. Add `?me=1` to your own site URL to skip counting your visits in that browser.

### Trophy sound

Set the trophy sound path and volume in `DW.trophyCfg` in `js/config.js`. The default expected file is `audio/trophy.mp3`. It must be a real MP3 file. If playback fails, check the browser console with F12. Browsers may block sound until the visitor first clicks or presses a key.

### Settings defaults

Default visitor settings live near the top of `js/settings.js` in `DEF`. Values from your own configuration are the starting point; visitors can override them on their own device.

### Adding a new emotion

Add a row to `js/emotion.js` with the emotion's name, typing speed, and aliases. Then add its visual style as `.em-yourname` in `css/style.css`.

### Adding a game or mode

Use an existing `G.add({...})` block in `js/games-arcade.js` as the pattern to follow.

### Changelog entries

Add new entries to the top of the `C.entries` list in `js/changelog.js`. Visitors see a blinking dot until they open the newest entry.

---

## Assets and file structure

The site is static, so filenames and paths matter.

### Core files

- `index.html`: main page and site metadata.
- `404.html`: GitHub Pages fallback page.
- `sw.js`: service worker and cache update logic.
- `.nojekyll`: GitHub Pages configuration helper.
- `CNAME`: custom domain configuration, if used.
- `robots.txt` and `sitemap.xml`: search-engine discovery files, if used.
- `css/style.css`: site styling.
- `js/*.js`: site features and configuration.
- `icons/`: category, subcategory, top-bar, and trophy artwork.
- `audio/`: music, trophy sound, and seasonal sound effects.
- `covers/`: music cover art.
- `video/`: intro videos.
- `seasons/`: seasonal artwork.

### Music and video files

- `audio/music1.mp3` through `audio/music8.mp3`, or whatever filenames your playlist uses.
- `audio/trophy.mp3`: optional trophy-unlock sound.
- `audio/jumpscare.mp3`: optional Halloween jumpscare sound.
- `covers/music1.png` and matching cover images for each playlist track.
- `video/intro.mp4`: main intro.
- `video/intro2.mp4`: rare alternate intro.

The names in `DW.playlist` must match the real files. Each cover should use the same base filename as its corresponding song.

### Icons

Use `icons/<id>.png` for category and subcategory icons. The currently documented examples include:

`identity`, `bio`, `manifesto`, `persona`, `projects`, `portfolio`, `archive`, `stack`, `gallery`, `art`, `audio`, `clips`, `writing`, `essays`, `notes`, `media`, `library`, `games`, `reviews`, `curation`, `favorites`, `playlists`, `inspirations`, `ideas`, `concepts`, `wishlists`, `mindset`, `opinions`, `lore`, `contact`, `reach-out`, `faq`, and `locked`.

Also provide `icons/eyes.png` and the trophy-tier pictures listed above. Optional top-bar button pictures can be configured through `DW.icons` in `js/config.js`.

Missing category icons can fall back to generated purple tiles. Missing trophy and seasonal PNGs do not get generated fallbacks.

---

## Save data and privacy

DWEEB//OS does not require a backend for its documented features.

- Settings are saved in the visitor's browser using `localStorage` under `dw-set`.
- Trophy and game data are saved in the visitor's browser.
- The documented save data is not sent to a DWEEB//OS server.
- Browser-local data is per device/browser and may not follow a visitor to another device.
- Visitors can delete their trophy/save data through the SAVE DATA tab.
- Since local data is stored on the visitor's device and the site code is public, a determined visitor can edit it.

If you add third-party analytics, external services, or other data collection later, update this section to explain what is collected and link to the relevant provider's privacy information.

---

## Updates and caching

The service worker in `sw.js` checks whether files have changed before using saved copies. This is intended to make updates appear on the next visit instead of waiting for the usual GitHub Pages cache delay.

- On the very first visit after adding the service worker, visitors may need to load the new `index.html` and `js/guard.js` once. A hard refresh or waiting up to around 10 minutes may be necessary.
- Pressing F5 in an already-open tab can still reuse files from memory.
- Closing and reopening the tab, or using Ctrl+F5, should load the newest version.
- Audio and video use Range requests that bypass the service worker. Replacing an MP3 while keeping the same filename can leave an old copy cached for up to around 10 minutes. Use a new filename when replacing a track.

### Important when updating

Do not overwrite your personalized versions of these files and folders when updating the project:

- `js/config.js`
- `icons/`
- `audio/`
- `covers/`
- `video/`

Back up your customizations before replacing core files.

---

## Hosting and going live

DWEEB//OS is designed for static hosting such as GitHub Pages.

1. Upload the project files to your repository.
2. Enable GitHub Pages for the repository.
3. Confirm that `index.html` and the asset folders are in the expected locations.
4. Add a `CNAME` file if using a custom domain.
5. Configure `robots.txt` and `sitemap.xml` if you want search engines to discover the site.
6. Create `og.png` in the repository root at **1200 × 630 pixels** for link previews.
7. Update the `<title>`, meta description, and JSON-LD block in `index.html`.
8. Add your GoatCounter site code to `DW.counter.code` in `js/config.js`, if using GoatCounter.
9. Visit the published site on both desktop and mobile and test the controls, links, audio, settings, and seasonal behaviour.

No build command is required.

---

## Credits, copyright, and reuse

### Copyright

Unless a file says otherwise, the original DWEEB//OS source code, visual design, written content, original artwork, and project-specific assets are © their respective creator(s). Third-party assets remain the property of their respective owners and are subject to their own licences.

**Please do not assume every file has the same licence.** If you plan to publish this repository with a specific open-source licence, add the appropriate `LICENSE` file and make sure it matches the permissions you actually want to grant.

### You can use this project as a reference

If DWEEB//OS gives you ideas for your own website, you're welcome to learn from its structure and use the project as inspiration. You can study how its files are organized, learn from its approach, and build your own site with your own identity.

A good way to make your version your own:

- Keep the general idea of a customizable, app-like personal website if it suits your project.
- Write your own text and dialogue.
- Make your own visual identity, icons, music, and artwork, or use assets with suitable licences.
- Change the categories, interactions, layout, and features to fit your needs.
- Check the licence of any code or asset you want to copy directly.
- Give credit when you reuse code, artwork, writing, or other material where the licence or creator asks for attribution.

### Please respect the original work

- Do not claim DWEEB//OS assets, writing, or original artwork as your own.
- Do not remove existing copyright or licence notices from material you reuse.
- Do not redistribute third-party music, images, fonts, or other assets unless their licences allow it.
- If you publish a direct fork or a close derivative, clearly explain what you changed and retain any required notices.
- Inspiration is encouraged; copying protected assets or presenting another person's work as your own is not the same thing.

This README is documentation, not a substitute for a software licence. If you want to allow people to copy, modify, and redistribute the source code under clear terms, choose a licence and include it in the repository. Until then, do not describe the entire project as public domain or freely licensed.

### Suggested attribution

If you reuse parts of DWEEB//OS, a simple credit is appreciated:

> Inspired by DWEEB//OS, a personal interactive website by DWEEB: [link to the original project].

Replace the placeholder with the actual public URL before publishing this attribution.

---

## Changelog

The CHANGELOG button in the top bar opens `js/changelog.js`. Add each new entry to the top of `C.entries`. Visitors see a blinking dot until they open the newest entry.

The small version text next to DWEEB//OS is configured through the `<small>` element in `index.html`. During a seasonal event, it can show the season name instead; those labels are configured in `js/seasons.js`.

When adding a release, consider documenting:

- New features.
- New games or game modes.
- New trophies and achievements, without spoiling secret conditions.
- Seasonal changes.
- Accessibility or mobile improvements.
- Bug fixes.
- Configuration changes that site owners need to know about.
- Any changed asset filenames or update instructions.

---

*DWEEB//OS is a work in progress. Features, secrets, trophy triggers, and configuration options may change as the project evolves.*
