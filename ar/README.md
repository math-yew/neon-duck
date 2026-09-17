# /public/ar

Drop your real MindAR files here:

- `targets.mind` - the compiled image target file (from the MindAR image
  target compiler).
- `overlay.mp4` - the default video overlay.
- optionally `overlay-image.jpg` (or similar) if you want an image-based
  overlay instead of video for a given painting.

Anything in `public/` is served from the site root, so these end up at:

- `/ar/targets.mind`
- `/ar/overlay.mp4`

The AR page (`app/ar/page.js` -> `components/ARScene.jsx`) always points at
`/ar/targets.mind`. Which media file it overlays (video or image, and its
path) comes from `services/overlayService.js`'s `defaultOverlayConfig.media`
- update that (or edit it live from `/editor`) to point at a different file
in this folder.
