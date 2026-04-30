# COWBOY / AR — v2 ANIMATED

Animated AR cowboy experience for KLINEKRAFT.

## What's new in v2

- **5 animations** baked into the GLB: Idle, Wave, Excited, Walk, Dance
- **Animation switcher panel** below the 3D viewer
- **Voice lines panel** scaffolded (audio files to be added)
- Playing state shown live in top-right of the stage

## Files

- `index.html` — the page
- `cowboy.glb` — 2.5 MB. Animated mesh, all 5 animations included.
- `cowboy.usdz` — 9.6 MB. iPhone AR (still). USDZ animation support is too inconsistent across iOS versions to bake animations in here; AR shows a static pose.
- `vercel.json` — MIME types
- `README.md` — this file

## To add audio (next step)

1. Generate 5 mp3 files via ElevenLabs (Sam Elliott-style voice — try "Adam" with low pitch)
2. Create a folder `audio/` in the repo root
3. Save the files as:
   - `audio/howdy.mp3`
   - `audio/pixels.mp3`
   - `audio/screen.mp3`
   - `audio/stories.mp3`
   - `audio/farewell.mp3`
4. Open `index.html`, find the `<!-- ... -->` block in the Voice Lines panel, **uncomment it**
5. Optionally remove the placeholder text above it
6. Commit and push — voice lines are live

## Deploy

Same as before. Push to GitHub, Vercel auto-deploys.

## Animation source

Mixamo, free, 5 animations selected:
- Breathing Idle (default)
- Waving
- Excited
- Walking
- Gangnam Style

All retargeted to the Meshy "Gentleman Cowboy" character mesh and merged into
a single GLB via custom Python (pygltflib + glTF buffer merging) then optimized
with @gltf-transform/cli (textures → WebP @ 2K).

## Known limitations

- Cowboy is bust-only (no legs). Walk animation will look weird. Consider this
  the "talking-head/torso version" for now.
- USDZ in AR remains static (Apple limitation, not ours).
- Animations may compete with auto-rotate on the stage; auto-rotate kicks in
  after 3s of no interaction.
