# DWEEB RECORDS (DWEEB//OS)

A tiny purple operating system for the web: a music player with a beat reactive background, a chat bot with 20 emotions, six games, 39 trophies (a lot of them secret), seasons, a settings page and a visitor eyes counter. Static site for GitHub Pages. No build step, no backend, no tracking beyond an optional GoatCounter. Upload the files and you're live.

Live at https://rdweeb.xyz

## Using this as a template
You are welcome to use this site as the structure for your own. The code is MIT licensed (see `LICENSE`). To make it yours:

1. Fork or download the repo and upload it to your own GitHub Pages repo.
2. Open `js/config.js` and change the menu, the playlist, the chat bot lines and the GoatCounter code (the sections below explain each one).
3. Replace everything in `icons/`, `covers/`, `audio/`, `video/` and `seasons/` with your own files.
4. Change the name, description and links in `index.html`, `CNAME`, `robots.txt` and `sitemap.xml`, and delete the `CNAME` file if you do not have a custom domain.
5. Rewrite `js/changelog.js` and the secrets and trophy lists to your own taste.

Please do not copy the name, the artwork or the music, and please do not leave my name or domain in your copy. A credit link back is appreciated but not required.

## Copyright and credits
- Code (`index.html`, `404.html`, `sw.js`, `css/`, `js/`): Copyright (c) 2026 RDweeb, released under the MIT license in `LICENSE`. Keep that notice if you reuse the code.
- Artwork, icons, covers, intro videos, season pictures, sounds and the names DWEEB RECORDS, DWEEB//OS and RDweeb are not part of the license. They are not included in the repo template and may not be reused without permission.
- Songs in the playlist belong to their artists. They are shown here as a personal playlist, with their names and credits. If you are an artist and want a song removed, contact me and it goes.
- Lyrics shown by the chat bot: only use lyrics you wrote or have the rights to.
- Nothing on the site collects personal information. Trophies, scores and settings are stored only in the visitor's own browser. The only outside service is the optional GoatCounter view counter.

## Features
**Music player**
- Plays your own mp3 files with cover art, a song list, shuffle, loop, volume, mute and a seek bar
- The whole site reacts to the beat of the song: icons bounce, text ripples, waves move, the background glows and dots float
- Timed lyrics from the chat bot, written by you per song
- Remembers the last song and the volume on the visitor's device
- Media keys and lock screen controls on phones

**The menu**
- A PlayStation style menu: categories across the top, items underneath, every item is a link you choose
- Works with arrow keys, mouse, swipe and tap, and the address bar remembers where you are (`#media/games`)
- Missing icons simply show nothing

**Boot screen and intro**
- A download counter while the files load, then an intro video, then the site
- A very rare second intro video (one in a billion, with its own rare trophy)
- Skip button, and a visitor setting to skip it automatically

**Chat bot (the line of text under the top bar)**
- Talks on its own, says hello and welcome back, comments on the time of day, the month, the song and the idle visitor
- Reacts to typed words and sings along with the playing song
- Gets told off for swearing, and gives up on visitors who ignore it
- 20 emotions with their own look and typing speed, see the table below
- Type `emotions` on the site to watch it do all of them

**Games**
- Rhythm (charts your own songs by listening to them, wrong taps cost accuracy so mashing fails)
- Snake (classic, wrap, speed, rocks), Pong (easy, normal, hard, 2 player), Tetris (marathon, sprint, ultra), Breakout (classic, hard, zen), 2048 (4x4, 5x5, 3x3)
- A game takes over the screen and the background effects pause, then come back
- High scores are saved on the visitor's device

**Trophies and save data**
- 39 trophies (40 with the birthday one) in five tiers: bronze, silver, gold, platinum and rare
- Pop up with a sound, a progress bar for the ones that need counting, and a tier summary
- A save data tab: time on site, visits, most played song, scores, and a delete button

**Seasons** (the whole month, only in the real month)
- February: Valentine's, hearts, bunting and a beating heart
- October: Halloween, cobwebs in the corners, a spider that drops off its thread and climbs back up, a ghost, and sometimes the spider escapes
- December: Christmas, a tree with three light shows and snow
- Dec 31 to Jan 7: New Year, fireworks, confetti and streamers
- The text next to DWEEB//OS shows the season, and the chat bot has lines for every month

**Settings** (saved per device, phones too)
- Colours: eight presets plus colour, intensity and brightness sliders. The whole site recolours
- Reactivity: beat reaction, sensitivity, floating dots, glow, calm mode
- Music: start muted, autoplay on or off, skip intro
- Chat bot on or off and how chatty it is, seasonal decorations, jump scares, eyes following the cursor, trophy sound and a light power mode

**Eyes**
- The visitor counter is a pair of eyes. Poke them enough and they wake up, follow your cursor, blink, fall asleep and react to being petted

**Everything else**
- Changelog button with a dot for new updates
- Works on phone and desktop, with a lighter mode for slow phones
- Update helper (service worker) so new uploads show without a hard refresh
- SEO: title, description, social preview, sitemap and robots.txt
- Secure by design: a strict Content Security Policy, no inline scripts or styles, no cookies, and external links are checked before opening

## Trophies
Secret trophies show ??? until unlocked.

| trophy | tier | how |
|---|---|---|
| HELLO WORLD | bronze | Step inside the site |
| FULL ALBUM | gold | Listen to every song on the playlist |
| TOURIST | gold | Open every site in the menu |
| CHANNEL SURFER | silver | Visit every category |
| REGULAR | silver | Visit the site 5 times |
| DEVOTED | gold | Visit the site 20 times |
| SETTLE IN | silver | Stay for 30 minutes in one visit |
| ARCADE KID | silver | Play every game in the games tab |
| SNAKE CHARMER | bronze | Eat 15 apples in one Snake run |
| LINE COOK | bronze | Clear 10 lines in one Tetris game |
| PONG PRO | bronze | Beat the CPU in Pong |
| BRICK BREAKER | silver | Clear every brick in Breakout |
| FIVE TWELVE | silver | Make a 512 tile in 2048 |
| ON BEAT | bronze | Finish a song in the rhythm game |
| PERFECT TIMING | gold | Get an S rank in the rhythm game |
| TINKERER | bronze | Change 5 different settings |
| PLATINUM | platinum | Earn every trophy (except the one in a billion) |

### Secret trophies
| trophy | tier | how |
|---|---|---|
| NOT A SINGLE MISS | gold | Finish a rhythm song without missing a note |
| THE BIG ONE | gold | Make a 2048 tile |
| POTTY MOUTH | bronze | Swear at the chat bot |
| OLD SCHOOL | silver | The Konami code. On a keyboard: up up down down left right left right B A. On a phone: swipe up up down down left right left right. You also get +30 lives |
| LEFT ON READ | bronze | Ignore the chat bot until it gives up on you |
| EXISTENTIAL DREAD | bronze | Watch the chat bot have a crisis (it happens at random) |
| POKE | bronze | Click the visitor eyes 15 times |
| IT IS ALIVE | gold | Wake up the eyes (after enough pokes it has a small chance on every click) |
| NIGHT OWL | bronze | Visit between 2am and 5am |
| COMMITMENT ISSUES | bronze | Pause the music 10 times |
| RIGHT ROUND | bronze | Hold the album cover for about a second |
| THAT IS MY FACE | bronze | Poke the chat bot's text until it complains (9 pokes) |
| MAKE UP YOUR MIND | bronze | Mash the mute button (8 times in 6 seconds) |
| ONE MORE TIME | silver | Let one song loop three times |
| SPOOKY SEASON | silver | Visit in October |
| GHOSTED | silver | Catch the ghost in October |
| JUMPSCARED | gold | Catch the escaped spider in October (it is a 1 in 9 chance each time you click the spider) |
| MERRY VISITOR | silver | Visit in December |
| TREE HUGGER | silver | Click the Christmas tree 10 times |
| NEW YEAR NEW YOU | silver | Visit at New Year |
| LOVE IS IN THE AIR | silver | Visit in February |
| CAKE DAY | gold | Visit on your own birthday (set in `config.js`, only appears if you set one) |
| ONE IN A BILLION | rare | See the second intro. One visit in a billion. Ask for a screen recording when someone DMs you |

Season trophies only unlock in the real month and never with the preview `force` option.

## What you edit
Almost everything is in `js/config.js`:
- `DW.menu`: the 10 categories and their items. `'name': 'https://link'`. Empty link = "no link yet" toast. Only http(s) and mailto links work. A dash shows as a space (`'reach-out'` becomes REACH OUT). `label` replaces the text under a category icon. A category with `subs: {}` has nothing to open
- `DW.playlist`: `'music1.mp3': { title, artist, album, lyrics }`. The cover is `covers/music1.png`
- `DW.splash`: the chat bot (see below)
- `DW.counter.code`: your GoatCounter code for the eyes counter (`?me=1` once on your own browser to skip your visits)
- `DW.icons`: optional pictures for the top bar buttons. Leave `''` for none, then nothing is requested
- `DW.eggs`: `{ birthday: { m: 5, d: 17 } }` (month, day) turns on the birthday message and trophy
- `DW.seasons`: `{ on: false }` turns all seasons off. `{ force: 'halloween' }` previews one (`xmas`, `valentine`, `newyear`), remove it afterwards
- `DW.seasonFx`: `{ runChance: 9, jumpscare: 'audio/jumpscare.mp3', volume: 0.9, dir: 'seasons/' }`
- `DW.trophyCfg`: the trophy sound file and volume
- `DW.intro` and `DW.intro2`: the intro videos

Icons are `icons/<name>.png` (for example `icons/bio.png`, `icons/reach-out.png`). Intro video is `video/intro.mp4`.

**When updating, do not overwrite:** `js/config.js`, `icons/`, `audio/`, `covers/`, `video/`, `seasons/`.

## Updates without a hard refresh
`sw.js` (a service worker) asks the server "did this change?" for every file before using its saved copy, so uploads show up on the next visit instead of after GitHub's 10 minute cache.
- The very first time, visitors need the new `index.html` and `js/guard.js` once (hard refresh, or wait up to 10 minutes) before the worker installs
- Pressing plain F5 in an already open tab can still reuse files from memory. Closing and reopening the tab (or Ctrl+F5) always gets the newest
- Audio and video use Range requests that bypass the worker, so replacing an mp3 under the same filename can stay stale for up to 10 minutes. Use a new filename

## The chat bot
It chats on its own, reacts to typed words (swear words get "Woah woah you'll make NickEh30 upset!", change the name with `boss`), and sometimes sings the playing song.
- `lyrics` on a playlist entry: an array or multi-line string, one line per row. Prefix `[m:ss]` for lines that follow the song in time. Only paste lyrics you wrote or have rights to
- `email`: leave `''` unless you want the "Want me to say somethin? Email me..." line (a mailto: link). It is public to everyone, so use a throwaway address
- `lines`, `scolds`, `every`, `singChance`, `mailChance` are all optional
- Typing also has easter eggs (try `hello`, `jams`, `sing`, `emotions`)

## Keys
Arrows or `< >` move, Enter opens, Space play/pause, N/P next/prev song, `[ ]` seek 10s, `- +` volume, M mute, S shuffle, L loop, F fullscreen, H or ? help, Esc closes a window. Letter hotkeys wait about 0.3 seconds so typing a word does not trigger them. On a phone: swipe left/right for category, up/down for the list, tap an icon to open it and tap the cover for the song list.

## Settings (js/settings.js)
The SETTINGS button opens a window where visitors can change the site colours, the reactivity, the music behaviour, the chat bot and the extras (see Features).
- Saved in the visitor's own browser (`localStorage`, key `dw-set`), per device. Nothing is sent anywhere
- `js/settings.js` must load right after `config.js` (it already does in `index.html`)
- Everything changes live except skip intro and power mode, which need a refresh. The window shows a REFRESH button for those
- The colour change recolours the whole stylesheet by shifting every colour. Greys, whites, golds and reds stay as they are
- Optional top bar picture: `DW.icons.settings = 'icons/settings.png'`. Left empty it shows the word (SET on phones)
- The defaults live at the top of `js/settings.js` (`DEF`)

## Seasons
`js/seasons.js` decides the dates. February = Valentine, October = Halloween, Dec 1-30 = Christmas, Dec 31 to Jan 7 = New Year (change them at the top of the file). `js/seasonfx.js` draws the decorations. Seasons can not be switched by typing. A forced season (`force` in config) never gives the trophy.

Halloween (October), pictures in `seasons/`:
- `seasons/web.png`: a cobweb drawn in the UPPER LEFT corner. The site flips it for the other three corners, the player and the windows
- `seasons/spider.png`: the spider (hanging, falling, climbing and running: one picture, drawn facing UP)
- `seasons/jumpscare.png`: optional, falls back to spider.png. Shown full screen on the jumpscare
- `audio/jumpscare.mp3`: plays on the jumpscare

One in nine clicks the spider falls off its thread and runs around the screen for about 20 seconds. Click it and you get the jumpscare, then the bot laughs. A cobweb in the top right corner can glitch on some screens, there is a note about it on the site.

Christmas (December): `seasons/tree.png`. Each click switches to `seasons/tree1.gif`, `tree2.gif`, `tree3.gif` and then back to the png.

## Eyes
Click the visitor eyes enough (`DW.eyesPet.after`) and every click after that has a small chance (`DW.eyesPet.chance`) to wake them up. Awake eyes follow the cursor, blink, fall asleep and react to clicks.

## Trophy files
- The trophy pictures live in `icons/`: `bronze.png`, `silver.png`, `gold.png`, `plat.png` (or `platinum.png`), `rare.png` and `locked.png`. Every trophy uses the picture of its tier. Rare uses `rare.png`
- Unlock sound: `audio/trophy.mp3` must be a real mp3. If it cannot play, the browser console (F12) prints why. Browsers block all sound until the first click or key press, so the sound waits for it
- Trophies are defined at the top of `js/trophies.js` (`secret: true` shows ??? until unlocked). Everything is saved in the visitor's own browser, so it can be edited by a determined visitor

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
- `audio/music1.mp3 ... music9.mp3` (the names in `DW.playlist`), `audio/trophy.mp3`, `audio/jumpscare.mp3`
- `covers/music1.png ...` one cover per song, same name as the song
- `video/intro.mp4`, `video/intro2.mp4` (the rare second intro)
- `icons/eyes.png`, and `icons/bronze.png`, `silver.png`, `gold.png`, `plat.png`, `rare.png`, `locked.png` for the trophies
- `icons/<id>.png` for each category and sub-category in `DW.menu` (identity, bio, manifesto, persona, projects, portfolio, archive, stack, gallery, art, audio, clips, writing, essays, notes, media, library, games, reviews, curation, favorites, playlists, inspirations, ideas, concepts, wishlists, mindset, opinions, lore, contact, reach-out, faq, locked)
- `seasons/web.png`, `spider.png`, `jumpscare.png`, `tree.png`, `tree1.gif`, `tree2.gif`, `tree3.gif`
- `og.png` (1200x630): the picture shown when the link is shared

## Files
`index.html`, `404.html`, `sw.js`, `CNAME`, `robots.txt`, `sitemap.xml`, `LICENSE`, `css/style.css`, `js/*.js`.

## Going live (custom domain)
- `CNAME` holds the custom domain. `robots.txt` and `sitemap.xml` are for Google
- Site name and description for Google live in the `<title>`, the description and the JSON-LD block in `index.html`
- GoatCounter: put your site code in `DW.counter.code` in `js/config.js`

## Changelog
The CHANGELOG button in the top bar opens `js/changelog.js`. Add a new entry at the top of the `C.entries` list each time you update the site. Visitors see a blinking dot until they have opened the newest one. The small text next to DWEEB//OS is the `<small>` in `index.html`, and during a season it shows the season name instead (change those in `js/seasons.js`).
