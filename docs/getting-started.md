# Getting Started with TrimSheetFast

TrimSheetFast fills a trim sheet you lay out yourself. You cut a square, mark regions with color IDs, describe each color, and download a PBR atlas. Your meshes stay in Blender or your engine. You UV them onto the sheet after export.

The in-app guide describes a real generation as taking about 40 seconds. Use a lower quality level while the layout is still changing.

## Before you start

- A desktop browser. The editor tells you the trim sheet tools are built for a larger screen and a mouse.
- An account when you want to generate. The free planner and builder do not require one. See [Free planner and builder](free-tools.md).
- Tokens on a paid plan when you generate. The control shows the cost first. Prices and allowances are on https://trimsheetfast.com/pricing.
- A kit in mind: which trims, panels, and pipes will share the sheet.
- A DCC where you can place UVs. TrimSheetFast does not unwrap the model.

## Step 1: Cut the layout

Open the trim sheet editor from the site.

Guide lines:

- Hover the left ruler for a vertical cut. Hover the top ruler for a horizontal cut.
- Click the canvas to place the line.
- Drag the line to move it.
- Drag an endpoint to shorten a cut that should not slice a region you want to keep whole.
- Double-click a line, or drag it to the edge, to delete it.

Or start from a preset:

- **H-trims** for horizontal moldings, planks, and pipes.
- **V-pipes** for vertical pipes, cables, and beams.
- **8-band** for eight matching strips.
- **Quad** for four large tiles.
- **3x3** for nine cells.
- **Hero** for one large panel plus smaller trims.

Lock the template when the cuts are right. Generation uses that layout.

## Step 2: Assign color IDs

Each color is one material. Every region you paint with that color gets the same prompt.

1. Select a color.
2. Click a region on the template, or click the same region on the 3D plane. The two stay in sync.
3. Repeat until each cell you care about has a color.

The colors are red, orange, yellow, green, blue, purple, pink, maroon, and brown.

You need prompts on at least two colors before a generation will run.

## Step 3: Write the prompts

The prompt box is per color, not per rectangle. If three strips are "green," one sentence covers all three.

Weak:

> metal

More useful:

> Brushed steel pipe, fine lengthwise grain, soft satin highlights, dark grease in the seams.

Keep the sentences in one art direction. A style preset will push the whole sheet. Do not ask one color for a photo and another color for pixels unless that clash is intentional.

Leave client names and unreleased titles out of the prompt unless your own rules allow them.

## Step 4: Style, quality, and resolution

**Style** is a real menu. Choices include AAA Photorealistic, AAA Stylized, Hand-Painted, Cartoon, Toon / Cel-Shaded, Casual / Mobile Style, Pixel Art, Anime / Manga, Low-Poly Stylized, PS1 / Retro 3D, and several game-look names (Roblox, Minecraft, CS2, and others). There is an Other field for a custom phrase. These names are looks inside the product, not studio partnerships.

**Quality** is Junior, Mid, or Senior.

- Junior is limited to 1K.
- Mid and Senior can go up to 4K (4096×4096).

Generate the first tries at the cheaper level. Move up after the cuts and the prompts are right. The button shows the token cost.

## Step 5: Generate Base Color

Generate Base Color and look at the plane.

Check:

- Each color stayed inside its region.
- The material you named is the material you see.
- Strips are wide enough that the detail is readable.
- The style matches across colors.

If a region is wrong, change that color's prompt or the cuts, then generate again. Do not spend the other maps on a sheet you will throw away.

## Step 6: Generate the other maps

When the color is approved, generate:

- Normal
- Height
- Roughness
- Metallic
- Ambient Occlusion

The editor can invert normal channels and adjust levels before you download. Download the adjusted file if you changed those controls. PNG is the export format the FAQ describes.

Name the files by sheet and channel, for example `kit_a_basecolor.png` and `kit_a_normal.png`.

## Step 7: UV the kit onto the sheet

In Blender, Maya, 3ds Max, or another DCC:

1. Unwrap each mesh, or reuse an unwrap that already matches this layout.
2. Place UV islands on the region that mesh should sample. A pipe island sits on the pipe strip. A wall quad sits on the panel.
3. Keep islands off the guide lines, or you will see the neighboring material on the edge.
4. Keep texel density similar across pieces that share the sheet. A tiny prop stretched across a huge region will look soft. A large wall crammed into a thin strip will look muddy.

TrimSheetFast does not check those UVs. The plane preview only shows the atlas.

## Step 8: Assign the maps

- **Blender:** Principled BSDF. Base Color to Base Color. Normal through a Normal Map node with Non-Color. Roughness, Metallic, Height, and AO into the slots you actually use.
- **Unity URP/HDRP:** Lit material. Mark the Normal map in the importer. Invert Roughness if the shader wants Smoothness.
- **Unreal:** a master material and instances. One atlas, many static meshes.
- **Godot:** StandardMaterial3D slots for albedo, normal, roughness, metallic, height, and AO.

Look at the kit under the game's lighting, not only on the plane.

## Common problems

### Generation will not start

At least two colors need prompts, and those colors need to be painted onto regions. Finish the layout before generating.

### A material bled into the next strip

The guide line is in the wrong place, or the UV island crosses it. Move the cut or the UVs. Do not expect the generator to invent padding you did not leave.

### Everything looks like the same surface

Those regions share a color ID. Give them different colors and different prompts.

### The sheet looks noisy

The prompt is too busy for the texel size, or Junior 1K is too small for the camera. Simplify the sentence, or move Mid or Senior up to a higher resolution after the direction is right.

### Not enough tokens

Lower the quality level or wait for the plan to renew. The pricing page is the source for allowances.

### I uploaded a model and nothing happened

The trim sheet editor does not take a mesh. Build the layout in the editor. Unwrap the model in your DCC and point the UVs at the downloaded atlas.

## Next steps

- [What a trim sheet is](what-is-a-trim-sheet.md)
- [Modular game kits](for/modular-game-kits.md)
- [FAQ](faq.md)
- Pricing: https://trimsheetfast.com/pricing
