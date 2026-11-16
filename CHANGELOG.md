# Changelog

## 1.9.0

- releases are a single Fleet.exe with its SHA-256 next to it, and the updater checks the hash before installing
- first run can add fleet to the start menu (also a switch in settings), and portable mode now always needs a password for the accounts file
- multi-instance turns on by itself when no roblox is open, and when roblox is already open fleet asks to close it and then turns multi-instance on
- lyrics no longer pick the wrong song or turn Chinese: lrclib and netease hits must match the title, the artist and the song length, covers are skipped, and chinese, japanese or korean lines are dropped (or the whole result refused) for songs with a latin name
- overlays over the roblox window in front, in the ctrl+shift+f menu: clock, how long you have played, cpu and memory of the window, the song, which account it is, how many windows are open, a note and a crosshair (dot, cross or ring). position, size and see-through are adjustable and it can stay hidden outside roblox
- a cleaner interface: the optimizer and the lyrics settings are grouped into sections that open and close (and are remembered), the colour options are one switch with the details under fine tuning, and the quick menu groups its settings the same way
- recolour every colour, not only blue: greens, reds, oranges and purples in roblox's menus and on-screen interface move to your colour too, and force colour and the menu theme now cover every interface picture (chat, voice, topbar, player list, selfview and more) instead of only the esc menu folders
- loading screen of your own: plain colour (your theme or a hex colour), the fleet logo, or your own picture, with the spinner in your accent
- icon styles for every roblox icon sheet: flat, spectrum, gradient and glow
- custom oof: pick your own ogg or mp3, and every sound (oof, ouch, falling, footsteps, jump, landing, getting up, swimming, splash, explosion, slider) can be silenced on its own
- smooth studs and calm water
- the quick menu (ctrl+shift+f) has all the texture, sound and loading screen options and can apply them as you change them
- the fleet window and tray icon are drawn from the new logo so the taskbar never shows an old cached icon
- force every change button: turns on the sky (forced onto every sky picture), effects, icons, force colour, menu theme, mono ui, health bar, hurt flash, cursor and font, then applies them
- force colour now also catches loose small icon pictures, not only the icon sheets
- more changes: no red flash when hurt, health bar in your colour, silence hurt sounds (oof, ouch, falling), silence movement sounds (footsteps, jump, landing, getting up, swimming)
- little animations on word looks: words bob, wobble, pulse, shiver, sway, shimmer through colours, ripple through their letters or flicker, each at its own pace, with a strength slider
- menus follow your fleet theme: the greys of roblox menus (panels, lines, text) in pictures and scripts are moved onto the colours of the theme you picked, with your accent for the blue
- word looks for lyrics: every word (or only the long and held ones) gets its own font, colour shift and effect (italic, outline, underline, echo, glow, capitals), the same word always looks the same. fonts, colours and effects can be switched on their own, with a colour spread slider
- dragged out words now stretch more than one letter: the held vowel and a hummable last letter, so home becomes hooooommme and feel becomes feeeelll
- sky and force field replacement now hit the real files of the current roblox player (dds pictures named .tex in PlatformContent, and the force field and sparkle dds in content\textures\particles), always keeping a backup to restore from. sun and moon are swapped too
- a bring back reflections button in performance: sets graphics to best and turns off lowering graphics after crashes
- musixmatch tries an automatic token and shows what happened under the token box
- music notes where there is only music: intros, solos, long gaps and outros (and songs with no words at all) show a swaying music note instead of nothing
- the lyrics fade out when nothing is playing (a short gap, like skipping, does not blink them) and are cleared a few seconds later, so the next song starts clean. "Looking for lyrics" is never shown
- musixmatch as a lyrics source: it needs a user token of your own (anonymous access now returns one wrong song for everything, which fleet checks for and refuses). with a token it gives exact word timing for many songs. paste it in the lyrics settings; best of all tries it first
- held words are dragged out: when the singer holds a word, its sound is stretched on screen while they hold it, growing as they do (love held for two seconds becomes looooove, so becomes soooooo). it picks the held vowel and skips a silent final e, has a limit you set, and only applies to songs with exact word times, so a guessed length never stretches words at random. works in the collage and the word animations
- auto sync: the lyrics now line themselves up with what is actually being sung. fleet listens to what the speakers play (only to measure timing), finds the moments the voice starts words, and compares them with when the lyrics say each word starts. it then moves the lyrics by the difference, continuously, so a song that is a little ahead or behind (or a spotify position that lags) corrects itself within about ten seconds. it only moves when the match is clear, shows its state in the lyrics settings, and can be switched off. the manual nudge still works on top
- roblox versions: the newest installed player is now found by the version number inside it, not by which folder was touched last. the versions page shows the number of what is installed, what roblox names as current, and warns when roblox's deploy history mentions a newer build than the one it names (which fleet cannot download by name; roblox's own updater fetches it)
- roblox versions: fleet now asks Roblox which release is the newest (the only place that knows it, since roblox's deploy history now says "version-hidden" for new releases) and uses that. starting the player directly uses the newest release and downloads it if it is not on the pc, never an older one just because that is what is installed. "get the newest" only ever downloads the release roblox names as current, and says so plainly when it cannot ask. the versions page shows the newest release and whether it is on the pc. downloads no longer fail on the installer program in the package list, and the newer extra packages go to the right folders
- the quick menu hotkey is more dependable and easier to check: every once-a-second job in fleet now runs on its own, so a failure in one (for example the lyrics window) can no longer stop the hotkey from being registered. the menu also opens over a roblox window fleet did not start, a menu that got stuck is replaced instead of eating the next press, and a failure to open is logged with the reason. tools > optimizer > windows has an in-game quick menu section to turn the hotkey on or off, change it, open the menu now, and see whether it is ready or taken by another program
- the bar that floats up when accounts are picked (launch, stop, mute, pin...) no longer lets clicks through to the list under it. before, pressing a button on the bar also pressed whatever was under it, such as another account's mute button, or started a drag selection. this was the real cause of mute and unmute hitting the wrong instance
- fixed muting and unmuting hitting the wrong window. (1) the right click menu used whatever accounts were picked, not the one you clicked, so unmute went to the other instance; it now acts on the one you clicked (or the whole pick when it is part of it). (2) when several windows start at once a process could be matched to the wrong account, so mute went to the wrong window; fleet now checks each window's process against the id its launch carried, fixes it, and says so in the log. (3) a muted account was muted again at 3, 9, 15 and 21 seconds after launch even if you had unmuted it; it now stops once you unmute. (4) every five seconds each window's sound is brought back in line with its account's mute setting
- no more "Looking for lyrics...": when the song changes, the words on screen stay (frozen, as they were) while the new lyrics are found, and the new lyrics join onto them: in a line the last line stays until the new first line, and in the collage the last words stay until the new phrase arrives (and leave on their own if nothing is found)
- right click any slider (or its label) to type an exact number. Enter sets it (held within the slider's range), Esc or a click elsewhere cancels. works in every settings page, and in the in-game quick menu, which takes the keyboard for the moment you type and hands it back to the game
- lyrics words are now on the point: (1) the NetEase search had stopped answering in the form fleet read, so every song silently fell back to line timing with guessed words. fixed, and for popular songs the exact time of every word now comes through. (2) in the collage each word starts its flight so that it lands at the exact moment it is said, with a small hit as it lands, instead of arriving roughly then. (3) spotify's position is corrected for the time the request took. (4) settings say how well the current song is timed ("exact time of every word" or "estimated") and have -50 / -10 / +10 / +50 ms nudges for a steady lag. credits at the start of lyrics are no longer shown as lines
- lyrics: words play exactly when they are sung. in the collage each word flies in just before it is said (it used to come in a fixed rhythm with the line), and "As it is sung" is now the default for word animations. beat sync stays off unless you turn it on
- lyric edit: lyrics that move with the song's tempo. fleet finds the tempo by listening to what your speakers play (a loopback of the sound card, no microphone), or guesses it from the lyric timing, or you set it. words land on the beat, the text punches on every beat, and it can shake and flash on the beat, with animations that settle within one beat. there is an Edit style that turns it all on with the collage layout
- lyrics collage layout: instead of one line, the song is cut into short phrases (at most 2 to 6 words, you choose) and one phrase at a time fills the whole lyric window like a poster. the words have different sizes (one hero word is the biggest), some stand sideways, they fly in from different sides, and the words already there slide and resize to make room as each new one arrives. at the end of a phrase the words fly off and the next phrase starts. the window height is adjustable up to 1000 px. the Kinetic style is the collage
- lyrics: words can stay turned sideways. a chosen share of the words turns a quarter turn as it arrives and stays that way, shrunk to fit if it is long
- lyrics: other words move aside. each word takes its place in the line as it arrives while the words already there slide over to make room and the whole line re-centres, instead of the line sitting still. words fly in from a different side each time
- lyrics animation is smoother everywhere: lines and words are placed at exact fractional positions (no pixel stepping), the song clock is smoothed so it never jumps when spotify refreshes its position, and the line that was just sung fades back to its resting look instead of snapping
- resize words: the word being sung can grow (up to 200%) and words can have different sizes. the line is laid out again every frame, so the other words are pushed aside smoothly, and growing words stay on the baseline
- lyrics word animation: a second way to show the line being sung. every word arrives on its own, flying in from different sides, spinning, zooming, dropping with a bounce, flipping like a card, or popping, or random for a mix. words can come with the line or as they are sung, with a strength slider, and a new Kinetic style turns it on
- quick menu rebuilt: it no longer flickers the game to black and no longer pauses it. nothing takes focus from roblox any more (no screenshot, no focus steal), so the game keeps running and keeps your keyboard while the menu is open. the game dims with a smooth fade (and can blur) behind a menu that fades and slides in, and everything fades out when you close it. esc closes it without roblox seeing the key
- force colour: roblox draws its new menu icons from picture sheets and takes its blue from script files, so recolouring the plain pictures missed them. the optimizer now recolours every icon sheet it can find, and turns roblox's blue (any shade, in pictures and in scripts) into your colour, or grey in black and white. everything is backed up and restore puts it back. on by default, with a result line after apply
- game browser fixed: roblox's game search quietly returns nothing unless the request carries a session id, so every search said "no game found". searches now send one, fall back to the older search, and errors say what roblox answered. server lists retry when roblox rate limits
- 3d avatars: roblox only answers the 3d picture service for signed in requests, so fleet now sends the account's saved login first and says clearly when it is refused. the flat picture still shows if 3d cannot load
- test connection button in the game browser and the avatar viewer: shows what each roblox service answered, so problems can be read off instead of guessed
- requests now look like a normal browser to roblox
- lyrics: the letters being sung can glow (softer, off by default, strength slider)
- fixed dropdown lists that sit inside a scrolling page (the lyrics font list, the roblox font list and others) opening off screen so they looked dead. long lists, like every installed font, now have a bar you can drag
- lyrics sources: choose LRCLIB, NetEase, or best of both. NetEase can carry the exact time of every word, so the fill and caret follow the singing precisely. without word times the line is spread over its words by syllables
- lyrics: the current word can be a smooth wipe, letters that light up and rise one by one, or whole words, with a glowing caret that moves letter by letter. the current word can lift, lines can have an outline, other lines can be smaller, and the current line can sit higher or lower in the window
- lyrics blur is a proper round blur that grows smoothly with distance (no steps), up to 25 px
- lyrics are drawn on their own thread with an exact clock at up to 120 fps, so they stay smooth even when fleet's window is busy
- lyrics on screen now only show while a Roblox window is in front (switch in the lyrics settings and the quick menu), and fade away when you switch to another program
- smoother while playing: the lyrics window draws each line once and reuses it (a frame is mostly picture copies), skips frames when nothing moved, and has a frames per second setting. fleet runs at a lower priority while roblox is open, and the roblox window you are playing gets a higher priority than the others. memory trimming and the ram cap no longer touch the window you are playing
- lyrics are far more customisable, with a live preview: six styles (apple, minimal, karaoke, subtitle, neon, cinema), any installed font, bold, capitals, left/centre/right, text size, line spacing, lines above and below, colours for the current and other lines, opacity and blur of the other lines, fill edge softness, glow, shadow, panel colour/opacity/roundness, glide speed, earlier/later timing, song name, progress bar, hide when paused
- toggle descriptions that were cut off now wrap
- launching works on installs where the roblox-player link is not registered ("Application not found"): fleet starts the player directly from the Roblox folder instead
- 30 new skies, 37 in all: nebula, galaxy, gas giant with rings, full moon, blood moon, moonrise, eclipse, midnight, mono, synthwave with a striped sun and grid, vaporwave, cyber, matrix, toxic, golden hour, twilight, desert, sakura, candy, violet haze, storm, overcast, rainy night, snow, arctic, deep sea, forest dusk with fireflies, inferno, ember night, and accent (drawn from your colour)
- auto groups: auto (follows the clock), random, calm, neon, space, dark, warm and hourly. each picks a sky from its group, and a new one every launch if that is on
- force sky: also redraws the other sky pictures roblox ships plus the sun and the moon, so games that only change part of their sky still show yours. a sky a game downloads itself cannot be replaced
- quick menu: press Ctrl+Shift+F (changeable) with a Roblox window open and the game dims and softens behind a small Fleet menu. tabs for lyrics, look (colours, cursor, sky, icons, apply), windows (title bar, border, icon, arrange) and the menu itself (dim, soften, hotkey). Esc or the hotkey closes it and gives Roblox focus back
- lyrics can be put anywhere: top, middle, bottom, left, centre, right, or drag the window and press Done. background strength slider
- lyrics on screen: a see-through window (clicks go through it) shows the lyrics of the song Spotify is playing. the line being sung is big and fills in word by word, the other lines are blurred and glide past. word times are used when the lyrics have them, otherwise each line is spread over its words by length. text size, width, lock and drag to place
- fleet icons: the small icons in roblox's menus (chat, emotes, backpack, home, players, settings, help, report, camera, leave, mute, block and more) are redrawn as thin line icons, in white or in your colour when tint is on
- optimizer: a "what fleet will change" list in plain words at the top, clearer tab names
- windows: the coloured border around roblox windows is off by default, with a switch to bring it back
- cursor pack: 17 pointer styles (mac, windows, slim, round, bold, sharp, outline, chevron, needle, flag, dot, ring, target, crosshair, plus, diamond, tiny), in black, white or your accent colour, with a size slider and smaller by default. Auto picks a different one on every launch
- spotify: connect your own spotify app (a client id, no secret, signs in once in the browser) so lyrics know the exact position of the song, even if fleet was opened mid song or you skip around
- game browser: servers > game browser. search a game by name (or paste a link or id), open it, and see its servers sorted smallest, largest, best ping or best fps, with full servers hidden if you like. click a server, random, or join top to put the selected accounts straight in
- new Fleet icon: an F made of three capsules on a dark tile. it is the app icon, the tray icon, the logo in the app, and the icon on the Roblox windows
- optimizer looks for the roblox client, in tabs: Looks (one click presets: Fleet Mono, Midnight, Mint, Sunset, Rose, Violet), Interface (cursor, font, and real colours: black and white, or tint the menus, emote wheel and hud in any colour), Sky, Windows and Clean up
- sky: draws a whole new skybox for roblox (night, aurora, sunset, dawn, space, day, mist, or auto that follows the clock), a new one each launch if you like, with words of your choice in it, or the song Spotify is playing (read from its window, no login). the sky does not move inside a game, it is a different one every session
- sky lyrics: puts the line of the song Spotify is playing, and the next three, in the sky, from LRCLIB (an open lyrics database, no login). fleet needs to be open when the song starts so it knows how far in it is
- group cards on the overview: each group of accounts has its own launch and stop, and shows how many are running
- optimizer colours have a strength slider, so the tint can be softer
- effects colour: recolours the force field, selection boxes, sparkles and loading spinner pictures. roblox animates those itself, so they keep moving in your colour
- windows: roblox windows get a dark title bar, a border in your colour, rounded corners and the Fleet icon (asked of Windows, nothing in roblox is changed)
- smoother animations everywhere: everything that moves is a spring now, so it eases in, has weight and settles softly. the selected tab and every segmented control use a liquid glass highlight that stretches as it moves and settles with a small bounce, and switches have a springy knob
- optimizer: Inter built into fleet as the font for roblox, in four weights, with a preview of both. the old windows fonts and your own font files still work
- performance > history: cpu and memory of each window (or all together) over the last 10 minutes or hour, with hover values. a window over your memory limit, or whose memory keeps climbing, is flagged and alerted
- alerts: settings > alerts chooses what goes to discord, a windows notification and a sound for each event (crash, kick, relaunch, breaker, locked, signed out, low robux, high memory, schedule ran, launch done), with test buttons, a robux limit, memory limits and quiet hours. `alerts` and `perf history` on the command line
- selecting accounts is much quicker: click one, ctrl click to add, shift click for a range, and drag a box over cards or rows like on the desktop (the list scrolls by itself near the edge). a master checkbox, invert, running, signed out and pinned quick picks, ctrl+a / ctrl+i / esc, enter to launch, delete to remove, double click to launch
- a bar floats up when accounts are picked with launch, stop, mute, pin, check and more, and right click gives the same menu
- pin accounts with a star to keep them on top, and sort the list by name, robux, status or last launched
- drag accounts (cards or rows) to put them in order, and drag several picked ones together. a line shows where they land and they slide into place
- undo and redo (ctrl+z, ctrl+y, and an undo button that shows for a few seconds) for removing, editing, tagging, pinning, muting and reordering accounts. `undo` and `redo` on the command line too
- the list / cards choice is remembered
- layout rewritten: windows tile the screen exactly with nothing overlapping. rows are balanced instead of one wide leftover, the invisible window border windows has is measured so neighbours do not overlap, and there is no minimum size forced any more (windows are asked for the exact slot and only if roblox refuses is its smallest size remembered and the layout redone, spilling extra windows to other screens)
- every page can be scrolled all the way down now, and the accounts toolbar and tools tabs no longer run into each other on small windows
- a full command line: fleetctl.exe (or Fleet.exe with a command) controls everything the window does, from launching accounts into any game or private server to settings, servers, presets, health, the optimizer, roblox versions, schedules, backups and more. fleetctl help lists it all, --json works on listings, and it returns exit codes for scripts. fleet://launch-account/name?place=id links work too
- tools > optimizer: swaps roblox's cursor for the normal windows pointer, replaces the font, turns the menu / emote wheel / top bar pictures black and white, and cleans old roblox versions, logs and cache. everything it changes is backed up and can be restored, and it can re-apply itself after roblox updates
- finds roblox when it is installed in program files, and the version list now includes the current version
- what's new window after an update, built from this changelog (also under settings > about)
- a short first launch tour that lights up each page, with a skip button. replay it from settings > about
- slimmer scrollbars that fade out, grow on hover and can be dragged
- right click menus and multiline boxes follow the theme
- fleet draws its own title bar with its own minimize, maximize and close buttons. dialogs have one too
- panels, popups and notifications are slightly see-through
- startup animation, and a nicer first setup: pick a theme and accent with a preview, steps slide in, the tour waits until you finish adding accounts
- smoother animations that run the same at any frame rate
- text boxes show the text cursor instead of the hand

## 1.8.1

- simpler layout page: windows fill the screen with no gaps and rearrange by themselves

## 1.8.0

- launching is faster. every login ticket is fetched at the same time, clients can all start at the same moment (new start all at once switch, on by default), and one shared detector finds all their windows instead of every account polling on its own. less disk writing during a launch
- windows arrange themselves: the best grid for the screen shape with no gaps, spread over all screens by size, and they rearrange when a window opens or closes
- fixed a bug where double clicking a word in a text field only selected part of it

## 1.7.0

- proper roblox version manager under settings > roblox: download any of the recent versions with progress and cancel, pick the default, delete old ones and see their sizes. accounts can have their own version too (edit account)
- scheduler under tools: launch a preset, launch everyone or stop everything at a time on chosen days
- fleet:// links and command line options. a second fleet hands its job to the first one
- gallery under tools: install shared configs and themes. the list lives in the gallery folder of the repo
- option to lower graphics when the crash breaker trips
- extra backup copies to a folder (cloud folder, usb stick), needs a password
- shortcuts: ctrl+f search, ctrl+l launch selected, ctrl+shift+s stop all, esc closes windows. there is a list in about
- open crash log button in about

## 1.6.0

- proper text fields: move the caret with the arrow keys, home, end and ctrl+arrows, select with shift or the mouse (double click picks a word), cut, copy, paste, undo, and a right-click menu
- typing in other languages works: japanese, chinese, korean and so on, including emoji, and the input window shows up next to the caret
- there are tests for the text fields now and they run in the build workflow

## 1.5.0

- animations are a lot lighter on the cpu now. the ui is cached and only redrawn when something changes, the wallpaper runs at a low frame rate, and everything pauses when fleet is minimized, in the background or on battery
- new animation setting in appearance: efficient (default), smooth or minimal
- the 3d viewer only renders when the model moves

## 1.4.0

- 3d avatar viewer. click an account's picture and fleet pulls the 3d model from roblox and shows it spinning. drag to turn it, scroll to zoom

## 1.3.0

- account tools under tools: summary, quick selection, sort, bulk rename, bulk edit, duplicate finder and export of the selected accounts

## 1.2.0

- account details window: age, premium, robux, friends and followers
- import accounts from other managers
- discord rich presence
- whole-pc memory cleaner, manual or automatic
- experimental proxy setting for the roblox process itself

## 1.1.0

- four light themes: paper, snow, sand and sky. the whole ui follows the theme

## 1.0.1

- animations: page slides, cards sliding in, counting numbers, toasts, pulsing dot on running accounts

## 1.0.0

first version.

- accounts as cards or a list with groups, tags, colours, notes, robux and mute. browser login or paste cookies
- fast overlapping launches, exact and private servers, follow a player, public server browser, game search
- saved private servers with a link check
- health page, event log, auto-relaunch and a crash breaker
- performance limits, quick and community configs, shareable configs
- window tiling, presets, macro recorder, mini window, compact mode, tray and hotkeys
- eight black themes, custom themes, ten languages, first-run setup
- proxies, discord alerts, roblox version changer, portable mode, backups, password protection and an updater
