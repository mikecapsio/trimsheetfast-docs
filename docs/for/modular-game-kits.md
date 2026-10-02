# Trim Sheets for Modular Game Kits

A modular kit is a set of wall pieces, trims, pipes, frames, and props that snap together. They only look like one place if they sample one material. TrimSheetFast is the atlas for that material: you cut the regions, prompt each color, and every mesh in the kit UVs onto the same PNG set.

Official pages:

- https://trimsheetfast.com/for/game-developers
- https://trimsheetfast.com/for/modular-environment-teams
- https://trimsheetfast.com/for/technical-artists
- https://trimsheetfast.com/for/hard-surface-artists

## Where kits go wrong

- Each artist sources a different wood and a different metal, and the corridor looks like a texture pack.
- A pipe on one mesh is 4 pixels tall and the same pipe on the next mesh is 40.
- Reworking art direction means opening every prop.
- A unique 4K texture per crate will not fit a mobile or VR budget.

One sheet makes the match, the texel size, and the material count a single decision.

## Plan the sheet before the meshes multiply

1. List the surfaces the kit actually repeats. Edge trim, panel, floor, pipe, cable, bolt strip, one hero inset.
2. Pick a layout. H-trims and 8-band fit moldings. V-pipes fit columns. Quad and 3x3 fit tiles and decals. Hero keeps one large panel and still leaves strips.
3. Give each surface its own color ID and a prompt that names grain, finish, and wear.
4. Pick one style preset for the game. Hand-Painted, Pixel Art, AAA Photorealistic, and the game-look names in the editor are there so the sheet does not mix languages.
5. Generate Base Color at Junior or 1K. Drop a test plane, or a single mesh, into the engine.
6. When the cuts are right, generate Mid or Senior up to 4K and the rest of the maps.
7. UV the kit to those regions. Keep islands off the cuts. Match texel density across pieces that share a strip.

## Engines

The handoff is one material.

- **Unity:** one Lit material, URP or HDRP. Normal map type set on import. Invert Roughness where the shader expects Smoothness. Mobile kits should stay on the resolution the device can sample, not on 4K because it is available.
- **Unreal:** one master material, instances if you need tint. Many static meshes, one texture set.
- **Godot:** StandardMaterial3D on the shared atlas.
- **Blender:** unwrap and look-dev, then export the meshes. The atlas PNG comes from TrimSheetFast.

The editor previews the sheet on a plane. The kit preview happens in the engine.

## What stays off the sheet

- Story decals, faction marks, and one-off damage.
- A first-person weapon that the camera fills.
- Anything that cannot share texel density with the wall kit.

Paint those in Substance 3D Painter or Blender. Leave the reusable metal, trim, and panel on the sheet.

## Tokens

Each generation spends tokens based on quality level and resolution. Test the layout cheaply. The pricing page is the only list of allowances: https://trimsheetfast.com/pricing

Paid plans include commercial use under the Terms. You still review the sheet in the level before you ship it.

## Related

- [What a trim sheet is](../what-is-a-trim-sheet.md)
- [Getting started](../getting-started.md)
- [TrimSheetFast vs Substance 3D Painter](../vs/substance-3d-painter.md)
