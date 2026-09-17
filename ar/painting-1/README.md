# /public/ar/painting-1

Drop this target's real MindAR files here:

- `targets.mind` - the compiled image target file for this painting.
- `overlay.mp4` - the video overlay (or an image file instead, if this
  target's `media.type` is `'image'`).

Anything in `public/` is served from the site root, so these end up at:

- `/ar/painting-1/targets.mind`
- `/ar/painting-1/overlay.mp4`

...which match `services/overlayService.js`'s `defaultOverlayTargets[0]`
(`mindSrc` and `media.src`).

## Adding another painting later

1. Make a new sibling folder, e.g. `public/ar/painting-2/`, and put its
   `targets.mind` + overlay file in it.
2. Add a matching entry to the `defaultOverlayTargets` array in
   `services/overlayService.js` (copy the `painting-1` entry, give it a
   new `id`, and point `mindSrc`/`media.src` at the new folder).
3. The editor page's target dropdown will automatically list it.
4. The AR page currently always renders `targets[0]` - once there's more
   than one target, decide how a visitor picks which one to view (e.g. a
   `/ar/[targetId]` route, or a selector on the AR page itself) and wire
   that in.
