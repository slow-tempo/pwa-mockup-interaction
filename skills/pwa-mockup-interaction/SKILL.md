---
name: pwa-mockup-interaction
description: >
  Keep single-file PWA mockup interactions fast and side-effect free by redrawing only the changed region, binding each listener once, and verifying each click produces exactly one effect.
license: MIT
---

# PWA Mockup Interaction Performance

## Redraw only the changed region

- Redraw only the panel or list that changed when a mockup interaction changes state.

- Keep the clicked button node alive across the update instead of rebuilding it with a full page regeneration.

- Apply the visible label change immediately and defer the save until after paint.

- Check the script diff after a surgery and allow only the intended hunks to change.

## Bind each listener once

- Attach each list or panel listener once when the mockup loads.

- Rerender data inside the existing container instead of reattaching listeners on every render.

- Treat a doubled save or download count as a binding bug and fix it at the binding site.

- Keep the sort control and the per-item download control distinct so a fix to one cannot be mistaken for a fix to the other.

## Verify each interaction by count

- Check the mockup script syntax before delivery.

- Drive the interaction in a headless browser and record how many saves and downloads each click produces.

- Require exactly one save per interaction and exactly one download per download click before delivery.

- Treat headless timing as reference only and request a real viewer check when the viewer still feels slow after a headless pass.


## Alternatives for better results

- Flip rows or cards in place for a sort change instead of rebuilding the whole application view.

- Defer persistence until after paint when a click feels slow even though the state change itself is instant.
