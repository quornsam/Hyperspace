PRISMATIC TRANSIT v26 — CONTROLS RESTORED

The previous fix addressed canvas stacking, but the actual disappearance was
caused by the 4.8-second inactivity timer. It set both the sidebar and edge tab
to opacity zero.

V26:
- Opera and desktop browsers keep the panel visible.
- The Tesla display keeps the panel visible.
- Hide UI and the edge tab still work.
- Small phones still auto-hide, but the edge tab remains visible.
- The dormant Tesla GPU canvas is not composited in non-Tesla browsers.
- The UI is after every canvas in DOM order and has the highest stacking level.
- Tesla drops only the panel backdrop blur to avoid a needless compositor pass.

Diagnostic: window.__prismaticControlDiagnostics
