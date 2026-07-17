PRISMATIC TRANSIT v22 — TESLA OPTIMISED

UPLOAD
------

Replace index.html with the new version. Keep these beside it:

manifest.json
icon-192.png
icon-512.png
apple-touch-icon.png
cat_sprite_sheet.png

Leave the music folder and all existing tracks unchanged.


TESLA MODEL 3 OPTIMISATION
--------------------------

This version recognises Tesla's in-car browser and begins with a rendering
profile designed for the large 2019 Model 3 display.

No controls, effects, music features or easter eggs have been removed.

The optimisations are internal:

- Tesla uses a stable 30 fps target rather than repeatedly failing to reach
  60 fps and producing uneven motion.
- If the browser still struggles, it can step down to 24 fps.
- Internal canvas resolution adapts through:
  100%, 86%, 74%, 62%, 52%, 44% and 36%.
- Tesla begins at 52% and may recover to 62% when performance allows.
- The rendered image still fills the complete screen.
- Large blurred Aurora and veil effects are rendered on a smaller cached
  surface.
- Slow effects are recalculated every third rendered frame on Tesla, while
  remaining smoothly visible between updates.
- Star blur is applied once to the completed field instead of separately to
  hundreds or thousands of star strokes.
- Phase Echo remains available but uses one full-screen echo copy on Tesla
  instead of three simultaneous full-screen copies.
- Glitch Memory decay is corrected for the actual frame rate, so its timing
  remains visually consistent at 30 fps.
- Meteor shattered-glass memory is still allocated only when needed.
- Performance monitoring now measures actual rendering work rather than
  mistaking a deliberate 30 fps cap for poor performance.


WHY THIS SHOULD BE FASTER
-------------------------

The heaviest operations were not the star movement calculations alone. They
were repeated full-screen blur filters and repeated copies of large canvases.

v22 substantially reduces those operations while keeping the same visible
features and user controls.


IPHONE AUDIO
------------

iPhone continues to use direct HTML audio playback for lock-screen support,
with Prismatic Transit track names, artwork and media controls.


CONTROLS
--------

Desktop / Tesla:
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
- Swipe to steer
- Toolbar and edge tab fade after inactivity


STAR SURF
---------

Star Surf is the gold control at the top. It plays compatible music files in
filename order, advances automatically, and returns to the first track after
the final one.


EASTER EGGS
-----------

MEOW:
While Star Surf is active, press M E O W.

Konami meteor:
Press Up Up Down Down Left Right Left Right A B Enter.
