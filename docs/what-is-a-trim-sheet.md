# What a Trim Sheet Is

A trim sheet is one texture atlas that many meshes share. Strips of molding, pipe, panel, edge wear, and small details sit in marked regions. Each prop is UV-unwrapped so its faces land on the region it needs. One material in the engine covers a whole kit.

That is the job TrimSheetFast is built for. You draw the cuts, you name the material in each region, and the generator fills the sheet.

Website: https://trimsheetfast.com

## Why teams use one sheet

A modular kit falls apart when every piece has its own texture. Texel density drifts, wear does not match, and draw calls pile up.

A trim sheet fixes the art direction and the budget at the same time:

- Pipes, trims, bolts, and wall edges come from the same strips, so they match.
- Ten props can share one material.
- A style change means regenerating the sheet, not repainting every mesh.

The cost is planning. If the UVs do not sit on the regions, the atlas cannot save the kit.

## What you decide before you generate

1. Which surfaces repeat. Planks, pipes, panel breaks, floor tiles, hero insets.
2. How the square is cut. Horizontal strips, vertical columns, a grid, or a large panel plus trims.
3. Which regions share a material. In TrimSheetFast that choice is a color ID. One color, one prompt.
4. The art direction. A style preset applies to the whole sheet so a hand-painted pipe and a photoreal pipe do not land on the same atlas by accident.

Layout presets already in the editor:

| Preset | What it is for |
| --- | --- |
| H-trims | Horizontal strips for moldings, planks, and pipes |
| V-pipes | Vertical columns for pipes, cables, and beams |
| 8-band | Eight matching horizontal strips |
| Quad | Four large squares for wall, floor, or ceiling tiles |
| 3x3 | Nine cells for tiles, decals, and one-off details |
| Hero | A large panel with supporting trim strips |

You can also draw the cuts yourself.

## What TrimSheetFast fills in

For each color you used, you write a material prompt. The generator builds Base Color inside those regions, then the rest of the PBR set: Normal, Height, Roughness, Metallic, and Ambient Occlusion.

Export is PNG, up to 4K on Mid and Senior. Junior stays at 1K.

You then unwrap in Blender, Maya, 3ds Max, or another DCC, and assign the maps in Unity, Unreal Engine, or Godot.

## What this is not

- Not a unique texture for one hero mesh. Paint that in Substance 3D Painter, Blender, or a similar tool. A trim sheet will repeat your regions wherever the UVs land.
- Not a seamless floor or wall material with no layout. That is a tiling material. [TexturesFast](https://texturesfast.com) does that job. A trim sheet is an atlas with deliberate cuts.
- Not a texture painted onto a model you upload. [TextureFast](https://texturefast.com) does that job. TrimSheetFast never opens the mesh.
- Not a parametric graph. Substance 3D Designer can keep wear and scale as sliders. A TrimSheetFast download is a fixed image. Another look is another generation.
- Not a photograph from a scan library. Poliigon-style catalogs give you a surface that already exists. A trim sheet is a layout of several surfaces you chose to pack together.

## When the sheet fails

- Regions are too thin for the texel size, so detail turns to noise.
- Two materials share a color ID when they should not, so they come out identical.
- Only one color has a prompt. The editor expects at least two.
- UV islands cross a guide line, so a prop shows a seam that is really a cut in the atlas.
- The style preset fights the prompt, for example a pixel-art preset with a prompt written as a photo description.

Fix the layout or the prompt and generate again. Hero damage, labels, and story wear still belong in a paint tool on top of the sheet, or on a separate unique texture.

## Where to go next

- [Getting started](getting-started.md)
- [Modular game kits](for/modular-game-kits.md)
- [TrimSheetFast vs Substance 3D Painter](vs/substance-3d-painter.md)
- [TrimSheetFast vs Photoshop](vs/photoshop.md)
