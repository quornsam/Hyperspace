PRISMATIC TRANSIT v23 — TESLA WEBGL EDITION

IMPORTANT
---------

v22 has been abandoned. Do not use it.

v23 is rebuilt from v21, the last version before the unsuccessful cached
Canvas experiment.


UPLOAD
------

Replace index.html with this version. Keep these beside it:

manifest.json
icon-192.png
icon-512.png
apple-touch-icon.png
cat_sprite_sheet.png

Leave the music folder and all tracks unchanged.


TESLA RENDERER
--------------

Tesla's browser is Chromium-based and supports WebGL. On a Tesla browser,
v23 moves the starfield from Canvas 2D to a dedicated WebGL canvas.

This means:

- star streak geometry is submitted to the GPU in one large batch
- thousands of individual Canvas beginPath/stroke/filter operations are avoided
- prism streaks are GPU geometry
- star blur is approximated with a faint GPU halo rather than Canvas blur
- Phase Echo is added within the same GPU batch
- Glitch Memory star persistence is handled directly on the WebGL surface
- the GPU star surface renders at 72% internal resolution and fills the screen
- no extra canvas is recalculated every third frame
- no artificial 24 or 30 fps cap is imposed

The ordinary Canvas renderer remains intact as a fallback. iPhone, desktop
browsers and devices where Tesla WebGL cannot initialise continue to use the
existing v21 rendering path.


CANVAS OVERLAY
--------------

Canvas 2D remains responsible for effects which are inexpensive or unsuitable
for the star geometry batch:

- Aurora Current
- veils
- gravity overlay
- portrait easter egg
- animated MEOW cat
- meteor and shattered glass
- vignette and colour washes
- interface

The overlay is transparent on Tesla and sits above the WebGL starfield.


FUNCTIONALITY
-------------

All controls and features remain available:

- Star Surf and sequential music-folder playback
- swipe and keyboard steering
- slowdown, corkscrew, gravity, prism and reverse
- star density, trail, blur, chroma, veils and decay
- Aurora Current and Phase Echo
- Glitch Memory
- MEOW cat
- Konami meteor
- iPhone Home Screen and lock-screen media support


DIAGNOSTIC
----------

When the Tesla WebGL renderer starts successfully, the root HTML element has:

data-renderer="tesla-webgl"

If WebGL cannot initialise, it falls back automatically and reports:

data-renderer="canvas2d-fallback"


CONTROLS
--------

Arrow keys: steer
Space: slow down
G: corkscrew
H: gravity
J: prism
K: reverse
N: next track
F: fullscreen where supported
Tab: hide or reveal controls

Mobile: swipe to steer.
