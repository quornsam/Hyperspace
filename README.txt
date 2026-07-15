PRISMATIC TRANSIT v21

UPLOAD
------

Replace index.html with the new file. Keep these beside it:

manifest.json
icon-192.png
icon-512.png
apple-touch-icon.png
cat_sprite_sheet.png

Leave the existing music folder and its tracks unchanged.


ADAPTIVE PERFORMANCE
--------------------

v21 keeps all visual effects and controls but changes the hidden rendering
workload automatically.

The renderer measures real frame time continuously. If a Tesla browser,
Android device or other slower system cannot sustain smooth animation, it
reduces the internal canvas resolution in small steps. The canvas still fills
the whole display and every feature remains available.

When performance has remained strong for several seconds, quality is restored
gradually.

Adaptive levels:
100%, 86%, 74%, 62% and 52% internal resolution.

The app begins at a suitable level based on:
- screen size
- device pixel ratio
- processor core count where available
- reported device memory where available

It then adjusts using measured performance rather than relying on the device
name or operating system.

The current internal quality is stored on the page as the
data-render-quality value for diagnostic inspection, but no extra control or
status box is shown to the user.


OTHER PERFORMANCE CHANGES
-------------------------

- Canvas requests the browser's desynchronised low-latency mode where supported.
- Trail history is preserved when internal resolution changes.
- The large meteor shatter snapshot is no longer kept permanently in memory.
- The shatter surface is allocated only when the meteor hits and released when
  the cracked-glass effect ends.
- Long pauses caused by tab changes, screen locking or browser menus are ignored
  by the performance monitor.


IPHONE AUDIO
------------

iPhone uses direct HTML audio playback so the current track can continue after
the phone is locked. Lock Screen and Control Centre receive Prismatic Transit
track names, artwork and media controls.

Automatic advancement between separate files while locked still depends on
the iOS version allowing webpage JavaScript to run.


IPHONE WEB APP
--------------

1. Open the live site in Safari.
2. Tap Share.
3. Tap Add to Home Screen.
4. Enable Open as Web App when shown.
5. Launch it from the Home Screen icon.


CONTROLS
--------

Desktop:
- Arrow keys: steer
- Space: slow down
- G: corkscrew
- H: gravity
- J: prism
- K: reverse
- N: next track
- F: fullscreen where supported
- Tab: hide or reveal controls

Mobile:
- Swipe across the starfield to steer
- Touch activity reveals the controls
- Toolbar and edge tab fade after inactivity


STAR SURF
---------

Star Surf is the gold control at the top. It plays compatible tracks from the
music folder in filename order, advances automatically and loops to the first
track after the last.


EASTER EGGS
-----------

MEOW:
While Star Surf is active, press M E O W.

Konami meteor:
Press Up Up Down Down Left Right Left Right A B Enter.
