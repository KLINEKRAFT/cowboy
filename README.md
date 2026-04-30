# COWBOY / AR

Single-page AR experience featuring an AI-generated gentleman cowboy.
Built for KLINEKRAFT.

## Files

- `index.html` — the page
- `cowboy.glb` — 1.5 MB. Desktop preview + Android AR.
- `cowboy.usdz` — 9.6 MB. iPhone AR via Quick Look.
- `vercel.json` — sets correct MIME types
- `README.md` — this file

Total: ~11 MB. All under GitHub limits, fast loading on cellular.

## Deploy

1. Create a new GitHub repo (e.g. `cowboy-ar`)
2. Upload all 5 files via GitHub web UI
3. Go to vercel.com → Add New Project → import repo
4. Accept defaults — it's a static site
5. Done — live in ~30 seconds

## Test on iPhone

1. Open the Vercel URL in Safari
2. Cowboy loads in 3D viewer (drag to rotate, pinch to zoom)
3. Tap red "VIEW IN AR" button
4. iOS Quick Look opens
5. Point phone at floor, move slowly to lock surface
6. Drag to position, pinch to scale, take photos

## Test on Android

Same flow, AR launches via Scene Viewer using the GLB.

## Test on desktop

3D viewer works. AR button shows fallback message ("open on phone").

## Optimization details

Original Meshy exports were:
- FBX: 38 MB + 65 MB textures
- USDZ: 38 MB

Optimized to:
- GLB: 1.5 MB (FBX→GLB conversion via FBX2glTF, then gltf-transform with WebP textures @ 2K)
- USDZ: 9.6 MB (textures downsized to 2K, repackaged with Pixar's UsdUtils.CreateNewARKitUsdzPackage for iOS Quick Look compliance)

No visible quality loss at AR viewing distance.
