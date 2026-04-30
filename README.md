# COWBOY / AR

Single-page AR experience for an AI-generated cowboy character.
Built for KLINEKRAFT.

## Stack

- `<model-viewer>` (Google web component) — handles 3D + AR
- iOS Quick Look — triggered by USDZ on iPhone Safari
- Android Scene Viewer — triggered by GLB on Android Chrome
- Static site, no build step, deploy anywhere

## Files

- `index.html` — the page
- `cowboy.glb` — 3D model for desktop preview + Android AR (53 MB)
- `cowboy.usdz` — 3D model for iOS AR via Quick Look (73 MB)
- `vercel.json` — sets correct MIME types for model files

## Deploy

### Vercel
1. Push this folder to a GitHub repo
2. Import the repo at vercel.com
3. Accept defaults — it's a static site
4. Done

### Test on iPhone
1. Open the deployed URL in Safari
2. Tap "VIEW IN AR"
3. Point phone at floor, move slowly to detect surface
4. Place cowboy, drag to position

## Known size note

~126 MB total assets is heavy. For optimization, run:

```bash
npx -y @gltf-transform/cli optimize cowboy.glb cowboy.optimized.glb
```

Can typically drop GLB from 53 MB → 10-15 MB without visible quality loss.
