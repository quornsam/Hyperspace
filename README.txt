PRISMATIC TRANSIT v20

UPLOAD
------

Replace index.html with this version. Keep these alongside it:

manifest.json
icon-192.png
icon-512.png
apple-touch-icon.png
cat_sprite_sheet.png

Leave the existing music folder untouched.


IPHONE LOCKED-SCREEN AUDIO
--------------------------

v20 uses direct HTML audio playback on iPhone instead of routing the music
through Web Audio. Web Audio can be suspended when the screen locks.

The update also:

- sets the browser audio session to playback
- publishes the current track as Prismatic Transit
- supplies Prismatic Transit artwork to Lock Screen and Control Centre
- adds play, pause, previous, next and seek media controls
- updates track position and playback state
- uses a smooth foreground fallback rhythm for Star Surf visuals on iPhone

The current track should continue when the phone locks.

iOS may suspend webpage JavaScript while locked. Because each song is a
separate file, automatic advancement at the exact end of a track cannot be
guaranteed on every iOS version. The Lock Screen Next control can be used.
Guaranteed uninterrupted transitions while locked would require one continuous
audio file or a proper streaming playlist.


IPHONE WEB APP
--------------

1. Open the live site in Safari.
2. Tap Share.
3. Tap Add to Home Screen.
4. Enable Open as Web App when shown.
5. Launch it from the Home Screen icon.

Delete and reinstall the Home Screen icon after this update.


CONTROLS
--------

Desktop:
Arrow keys steer. Space slows down. G corkscrews. H enables gravity.
J enables prism. K reverses. N skips track. F requests fullscreen.
Tab hides or reveals controls.

Mobile:
Swipe to steer. Controls and the edge tab fade after inactivity.


STAR SURF
---------

Star Surf is the gold control at the top. It plays every compatible file in
the music folder in filename order and loops back to the first track.


EASTER EGGS
-----------

While Star Surf is active, press M E O W for the animated cat.

Press Up Up Down Down Left Right Left Right A B Enter for the meteor impact.
