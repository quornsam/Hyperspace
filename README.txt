PRISMATIC TRANSIT v24 — TESLA INSTANCED GPU BUILD

IMPORTANT
---------

v22 and v23 should not be used.

v24 is rebuilt from v21 and replaces the Tesla starfield with a new renderer
rather than modifying the unsuccessful v23 renderer.


WHAT WAS ACTUALLY EXPENSIVE
---------------------------

The original Canvas renderer performed, every frame:

- one quadratic Canvas path for every star
- two additional paths per star when Prism was active
- a live Canvas blur filter across the star layer
- six large blurred veil gradients
- four large blurred Aurora curves
- up to three full-screen canvas copies for Phase Echo
- full-screen trail fading and compositing

This creates a high number of JavaScript-to-renderer calls, large temporary
surfaces and repeated full-screen pixel operations.

The number of stars alone was not the main problem.


TESLA GPU ARCHITECTURE
----------------------

On Tesla, v24 uses WebGL with ANGLE instancing.

- One six-vertex quad is reused for every star.
- Only seven numbers per star are uploaded each frame.
- Projection, rotation, gravity warping and streak geometry run in the vertex
  shader.
- Colour, Prism and soft blur halos run in the fragment shader.
- All stars are rendered in one draw call per visual pass.
- Aurora, veils, background glow, reverse wash and gravity are procedural GPU
  effects. There are no Canvas blur filters for them.
- Glitch Memory and Phase Echo use two GPU textures which alternate each frame.
- The final scene is composited once.
- The GPU surface uses the Tesla screen's CSS-pixel resolution. It is not
  intentionally reduced.
- No frame-rate cap is imposed.

Canvas 2D remains only for effects which are usually inactive:

- the portrait
- the MEOW cat
- meteor and shattered glass
- the interface

If WebGL instancing is unavailable, v21's normal Canvas renderer remains as the
automatic fallback.


MEMORY
------

At 1920 × 1200, the two RGBA feedback textures use about 17.6 MiB in total.
There are no permanent extra full-screen cached Aurora, veil or Phase Echo
canvases.

The star upload buffer is about 44 KiB at the maximum 1,600 stars.


BUILT-IN DIAGNOSTICS
--------------------

The page exposes:

window.__prismaticDiagnostics

It reports:

- active renderer
- star count
- GPU surface dimensions
- average CPU submission time
- average star-buffer upload time
- rendered frame count
- WebGL error, if any


UPLOAD
------

Replace index.html. Keep all existing assets and the music folder unchanged.
