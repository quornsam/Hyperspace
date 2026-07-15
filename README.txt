PRISMATIC TRANSIT v19

UPLOAD STRUCTURE
----------------

Upload these files to the main published directory:

index.html
manifest.json
icon-192.png
icon-512.png
apple-touch-icon.png
cat_sprite_sheet.png

Keep the existing music folder beside them:

music/
  track-one.mp3
  track-two.mp3
  track-three.mp3
  ...

Star Surf discovers compatible audio files in the music folder, plays them
in filename order, and starts again after the final track.


IPHONE: REMOVE THE BOTTOM URL BAR
---------------------------------

A normal webpage open inside Safari cannot reliably force Safari's bottom URL
bar and toolbar to disappear permanently.

Use the Home Screen web-app version instead:

1. Open the live Prismatic Transit site in Safari.
2. Tap Share.
3. Tap Add to Home Screen.
4. Enable Open as Web App when that option is shown.
5. Tap Add.
6. Close Safari.
7. Launch Prismatic Transit from its new Home Screen icon.

When launched from the Home Screen icon, it opens in standalone web-app mode.
The Safari URL bar and bottom toolbar are not shown. A small iPhone status area
may remain.

Reloading the page in Safari is not the same as launching the installed web app.

After uploading this version, delete any older Prismatic Transit Home Screen
icon and add it again so iPhone reads the new manifest and app settings.


CONTROLS
--------

Desktop:
- Arrow keys: steer
- Space: slow down
- G: corkscrew
- H: gravity
- J: prism
- K: reverse transit
- N: next track
- F: fullscreen where the browser supports it
- Tab: hide or reveal the toolbar

Mobile:
- Swipe across the starfield to steer
- Touch activity reveals the toolbar
- The toolbar and its edge tab fade after inactivity
- The old mobile keypad and arrow pad are removed


STAR SURF
---------

Star Surf is the gold control at the top of the toolbar.

It:
- plays all compatible tracks in the music folder
- advances automatically and loops the playlist
- changes visual treatment at bars, phrases, builds and drops
- changes speed smoothly rather than jolting on each beat
- varies density, blur, colour, trails, veils and effects
- occasionally uses controlled one- or two-bar slowdowns


VISUAL EFFECTS
--------------

Aurora Current:
Flowing spectral ribbons.

Phase Echo:
Displaced ghost images of the starfield.

Glitch Memory:
Trails fade naturally after being switched off. Memory tone can be Auto,
Light or Dark.

Star Blur:
Softens stars and streaks.

Centre Protection:
Prevents trails building into a solid white patch at the vanishing point.


EASTER EGGS
-----------

MEOW:
While Star Surf is on, press M E O W in order.

The sprite-animated cat climbs into view, walks, sits facing away, watches,
licks its paw, curls up, sleeps, wakes, walks away and climbs down.

Konami meteor:
Press Up Up Down Down Left Right Left Right A B Enter.

A meteor approaches, strikes the display, shakes it and leaves cracked glass
that gradually fades.


GITHUB PAGES
------------

The main page must be named index.html.

All filenames are case-sensitive.

When updating:
- replace index.html
- upload manifest.json and the three icon PNG files
- keep cat_sprite_sheet.png beside index.html
- leave the music folder untouched

Allow GitHub Pages time to deploy before testing. On iPhone, remove and re-add
the Home Screen web app after manifest or icon changes.
