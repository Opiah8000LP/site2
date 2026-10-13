# DWEEB//OS

Static site for GitHub Pages. No build step, no backend. Upload the files and you're live.

## What you edit
Everything is in `js/config.js`:
- `DW.menu` - the 10 categories and their items. `'name': 'https://link'`. Empty link = "no link yet" toast. Only http(s)/mailto links work. A dash shows as a space (`'reach-out'` -> REACH OUT). `label` replaces the text under a category icon. A category with `subs: {}` (LOCKED) has nothing to open.
- `DW.playlist` - `'music1.mp3': { title, artist, album, lyrics }`. Cover is `covers/music1.png`.
- `DW.splash` - the talking line (see below).
- `DW.counter.code` - your GoatCounter code for the eyes counter (`?me=1` once on your own browser to skip your visits).

Icons are `icons/<name>.png` (e.g. `icons/bio.png`, `icons/reach-out.png`, `icons/locked.png`). Missing icon = generated purple tile. Intro video is `video/intro.mp4`.

**When updating, don't overwrite:** `js/config.js`, `icons/`, `audio/`, `covers/`, `video/`.

## Updates without a hard refresh
`sw.js` (a service worker) asks the server "did this change?" for every file before using its saved copy, so uploads show up on the next visit instead of after GitHub's 10 minute cache.
- The very first time, visitors need the new `index.html`/`js/guard.js` once (hard refresh, or wait up to 10 min) before the worker installs.
- Pressing plain F5 in an already-open tab can still reuse files from memory; closing and reopening the tab (or Ctrl+F5) always gets the newest.
- Audio/video use Range requests that bypass the worker, so replacing an mp3 under the same filename can stay stale up to 10 min. Use a new filename.

## The splash line
It chats on its own, reacts to typed words (swear words get "Woah woah you'll make NickEh30 upset!" - change the name with `boss`), and sometimes sings the playing song.
- `lyrics` on a playlist entry: an array or multi-line string, one line per row. Prefix `[m:ss]` for lines that follow the song in time. Only paste lyrics you wrote or have rights to.
- `email`: leave `''` unless you want the "Want me to say somethin? Email me..." line (a mailto: link). It is public to everyone, so use a throwaway address.
- `lines`, `scolds`, `every`, `singChance`, `mailChance` are all optional.
- Typing also has easter eggs (try `hello`, `jams`, `sing`, the Konami code).

## Keys
Arrows or `< >` move, Enter opens, Space play/pause, N/P next/prev song, `[ ]` seek 10s, `- +` volume, M mute, S shuffle, L loop, F fullscreen, H or ? help. Letter hotkeys wait ~0.3s so typing a word doesn't trigger them. The address bar (`#media/games`) remembers your spot.

## Files
`index.html`, `404.html`, `sw.js`, `.nojekyll`, `css/style.css`, `js/*.js`.

## Games
The GAMES button in the top bar opens Rhythm, Snake, Pong, Tetris, Breakout and 2048. A game takes over the whole screen: the background, particles and beat reactions switch off while you play (the music player stays) and come back when you leave. Snake, Pong, Tetris, Breakout and 2048 each have modes (Snake: classic / wrap / speed / rocks, Pong: easy / normal / hard / 2 player, Tetris: marathon / sprint / ultra, Breakout: classic / hard / zen, 2048: 4x4 / 5x5 / 3x3). Scores are saved in the visitor's browser. Rhythm charts your own songs by listening to `audio/<file>` when a song is picked; wrong taps hurt your accuracy so mashing keys does not work. To add a game or mode, copy a `G.add({...})` block in `js/games-arcade.js`.

## Icons you need (all PNG)
- `icons/<id>.png` for every category and sub-category (as before), `icons/eyes.png`
- top bar button pictures are optional (`DW.icons` in `js/config.js`)
- Trophy pictures live in `icons/`: `bronze.png`, `silver.png`, `gold.png`, `plat.png` (or `platinum.png`), `rare.png` and `locked.png`. Every trophy uses the picture of its tier. The trophy ids are:
  welcome dj tourist hopper regular devoted longhaul arcade snake15 tetris10 pongwin breakout fivetwelve rhythm rhythmS fullcombo twentyfortyeight potty konami alone existential poke alive night commit spooky merry newyear valentine spin ouch mutiny onemore ghosted scare treehug rare plat (and birthday if you set one)
- Missing PNGs show nothing, there are no generated fallbacks.

## Trophies and save data
The TROPHIES button shows trophies and a SAVE DATA tab (time on site, visits, most played song, scores, a delete button). Trophies are defined at the top of `js/trophies.js` (`secret: true` shows ??? until unlocked). Everything is saved in the visitor's own browser, nothing is sent anywhere, so it can be edited by a determined visitor. For the one in a billion trophy, ask for a screen recording when someone DMs you.

Unlock sound: your own file at `audio/trophy.mp3` (path and volume are in `DW.trophyCfg`, js/config.js). No file, no sound.

## Seasons
`js/seasons.js` turns on decorations on certain days: Valentine's Day, Halloween (Oct 29-31), Christmas (Dec 24-26), New Year (Dec 31-Jan 1). The chat bot also has lines for every month. Preview one with `force` (see Seasons now last the whole month). Turn it all off with `DW.seasons = { on: false }`.

## Eyes
Click the visitor eyes enough (`DW.eyesPet.after`) and every click after that has a small chance (`DW.eyesPet.chance`) to wake them up. Awake eyes follow the cursor, blink, fall asleep, and react to clicks.


## Emotions (living text)

Any line the bot says (config `DW.splash.lines`, `scolds`, lyrics, anything) can carry emotions. Put a tag in `<angle brackets>` before the words you want to change. The emotion lasts until the next tag, or until `<n>`.

    HELLO <angry>WORLD              -> WORLD shakes and glows red
    Hello <shy>world                -> tiny, trembling, typed slower
    i am <sad>fine<n> really        -> only "fine" droops, then back to normal
    wait for it <wait> <excited>NOW -> <wait> pauses the typing (<wait2> = twice as long)

| tag | what it looks like | aliases |
|---|---|---|
| `<angry>` | red, shaking hard | mad, rage, furious |
| `<shy>` | tiny, trembling, slow typing | timid, bashful |
| `<sad>` | blue, drooping, slow typing | cry, down, blue |
| `<happy>` | yellow, bouncing | joy, glad, yay |
| `<excited>` | big, gold, jiggling, fast typing | hype, yippee |
| `<scared>` | pale, shivering fast | afraid, fear, terrified |
| `<whisper>` | tiny, faded, italic, slow | quiet, psst, secret |
| `<yell>` | huge, pulsing, fast typing | loud, shout, scream |
| `<sleepy>` | dim, swaying, very slow typing | tired, yawn, sleep |
| `<love>` | pink, heartbeat | heart, crush, blush |
| `<silly>` | wobbling, rainbow colours | goofy, wacky, derp |
| `<spooky>` | purple glow, flickering | ghost, creepy, eerie |
| `<dizzy>` | wavy | drunk, spin, wavy |
| `<glitch>` | mono font, cyan/magenta split, twitching | error, bug, broken |
| `<cold>` | icy blue, shivering | freeze, brr, chilly |
| `<rich>` | gold, shimmering | gold, fancy, shiny |
| `<sneaky>` | small, italic, sliding side to side | sly, plotting, smirk |
| `<nervous>` | jittery | anxious, worried, sweat |
| `<proud>` | gold, puffed up | smug, boast |
| `<sing>` | blue, bobbing like a melody | music, melody, la |

Reset with `<n>` (also `<normal>` or `</>`). Unknown tags are shown as plain text. Type `emotions` on the site to see the bot do every one of them. To add your own: add a row in `js/emotion.js` (name, typing speed, aliases) and a `.em-yourname` rule in `css/style.css`.


## Every file you supply (names matter)
- `audio/music1.mp3 ... music8.mp3` (the names in `DW.playlist`), `audio/trophy.mp3` (trophy unlock sound)
- `covers/music1.png ...` one cover per song, same name as the song
- `video/intro.mp4`, `video/intro2.mp4` (the rare second intro)
- `icons/eyes.png`, and `icons/bronze.png`, `silver.png`, `gold.png`, `plat.png`, `rare.png`, `locked.png` for the trophies
- `icons/<id>.png` for each category and sub-category in `DW.menu` (identity, bio, manifesto, persona, projects, portfolio, archive, stack, gallery, art, audio, clips, writing, essays, notes, media, library, games, reviews, curation, favorites, playlists, inspirations, ideas, concepts, wishlists, mindset, opinions, lore, contact, reach-out, faq, locked)

## Season decorations
`js/seasonfx.js` adds the extras for each season (it hooks into `seasons.js`). The art is yours, put these in a `seasons/` folder. Missing files just show nothing.

Halloween (October):
- `seasons/web.png` a cobweb drawn in the UPPER LEFT corner. The site flips it for the other three corners, the player and the windows.
- `seasons/spider.png` the spider (hanging on its thread, falling, climbing and running around: one picture, drawn facing UP).
- `seasons/jumpscare.png` (optional, falls back to spider.png) shown full screen on the jumpscare.
- `audio/jumpscare.mp3` plays on the jumpscare.
One in nine clicks the spider falls off its thread and runs around the screen for about 20 seconds. Click it and you get the jumpscare, then the bot laughs. Change the odds or file names in config.js if you want: `DW.seasonFx = { runChance: 9, jumpscare: 'audio/jumpscare.mp3', volume: 0.9, dir: 'seasons/' };`

Christmas (December):
- `seasons/tree.png` the tree. Each click switches to `seasons/tree1.gif`, `tree2.gif`, `tree3.gif` and then back to the png.

Valentine (February): heart bunting and a big beating heart you can click. New Year: fireworks, confetti and streamers.

## Trophy sound
`audio/trophy.mp3` must be a real mp3. If it cannot play, the browser console (F12) prints why (not found, or not a real mp3). Browsers block all sound until the first click or key press, so the sound waits for it.

## Seasons now last the whole month
Valentine = all of February, Halloween = all of October, Christmas = Dec 1-30, New Year = Dec 31 to Jan 7 (change the dates at the top of `js/seasons.js`). The trophy only unlocks if you really visit in that period.
Seasons can not be switched by typing. To preview one yourself add `force: 'halloween'` (or `xmas`, `valentine`, `newyear`) to `DW.seasons` in `js/config.js` and remove it again afterwards (a forced season never gives the trophy).

## Going live (rdweeb.xyz)
- `CNAME` holds the custom domain, `robots.txt` and `sitemap.xml` are for Google.
- Make `og.png` (1200x630) in the root: it is the picture shown when the link is shared.
- Site name / description for Google live in the `<title>`, description and the JSON-LD block in `index.html`.
- GoatCounter: put your site code in `DW.counter.code` in `js/config.js`.

## Changelog
The CHANGELOG button in the top bar opens `js/changelog.js`. Add a new entry at the top of the `C.entries` list each time you update the site; visitors see a blinking dot until they have opened the newest one. The small text next to DWEEB//OS (it used to say v0.1) is the `<small>` in `index.html`, and during a season it shows the season name instead (change those in `js/seasons.js`).


## Secrets that work on phones too (js/eggs.js)
Hold the album cover, poke the chat bot's text, mash the mute button, loop one song 3 times, swipe up up down down left right left right, and catch the ghost / escaped spider / Christmas tree in season. - For a birthday trophy and message set `birthday: { m: 5, d: 17 }` (month, day) in the same place.

## Settings (js/settings.js)

The SETTINGS button in the top bar opens a window where visitors can change: the site colours (presets plus hue / intensity / brightness sliders), how much everything reacts to the music (beat reaction, sensitivity, floating dots, glow, calm mode), start muted, autoplay, skip intro, the chat bot (on/off, chattiness), seasonal decorations, jump scares, eyes following the cursor, the trophy sound and a power mode.

- Saved in the visitor's own browser (`localStorage`, key `dw-set`), per device. Nothing is sent anywhere.
- `js/settings.js` must load right after `config.js` (it is already in that order in `index.html`).
- Some switches (skip intro, chat bot, chattiness, seasonal decorations, eyes, power mode) need a refresh; the window shows a REFRESH button when that happens.
- The colour change recolours the whole stylesheet by shifting every colour. Greys, whites, golds and reds stay as they are.
- Optional top-bar picture: `DW.icons.settings = 'icons/settings.png'` in `config.js`. Left empty it shows the word (SET on phones).
- Defaults live at the top of `js/settings.js` (`DEF`). Your own config values are the starting point; visitors only override them on their device.
