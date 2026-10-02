# TrimSheetFast FAQ

Answers below follow the public site: the About page, the FAQ, the editor, the pricing page, the Privacy Policy, and the Terms. Where the FAQ still describes a 3D-model upload, this file follows the trim sheet editor instead. Prices are not copied here. Use https://trimsheetfast.com/pricing.

## Product

### What is TrimSheetFast?

TrimSheetFast turns a marker layout and a material prompt per color into a PBR texture atlas. You export maps for Unity, Unreal Engine, Godot, and Blender. Paid plans include a commercial-use license, subject to the Terms.

Mike Caps (@mikecaps) makes it, alongside TextureFast for UV-model texturing and TexturesFast for seamless materials. Those are different products.

### How does it work?

Draw guide lines, mark regions with color IDs, and write a prompt for each color you use. Choose a style preset, a quality level (Junior, Mid, or Senior), and a resolution. Generate Base Color, check it on the plane, then generate the other maps.

A run needs at least two prompted colors.

### What is a trim sheet?

One atlas shared by many meshes. Strips and panels live in regions. Each mesh is UV'd onto the region it should show. See [What a trim sheet is](what-is-a-trim-sheet.md).

### Does TrimSheetFast generate 3D models?

No. It generates the atlas. You model and unwrap elsewhere.

### Is TrimSheetFast the same as TextureFast?

No. TextureFast textures a UV-unwrapped model and keeps that model in the browser. TrimSheetFast never asks for the mesh. It fills a layout you draw.

### Is it the same as TexturesFast?

No. TexturesFast makes a seamless tileable material with no trim cuts. TrimSheetFast packs several materials into one sheet on purpose.

### Who is it for?

People who reuse one atlas: game developers, technical artists, hard-surface and prop artists, modular-environment teams, and asset-pack publishers. The product onboarding also lists archviz and kitbash. It is the wrong tool when a hero asset needs pixel-level painting.

### Is it usable for a first atlas?

The editor is a layout, then prompts, then generate. You still need to know how to place UVs in your own software. The in-app guide walks through cuts, color IDs, and the first Base Color.

### What are the style presets?

A menu you pick before generation so the whole sheet shares one look. The editor includes AAA Photorealistic, AAA Stylized, Hand-Painted, Cartoon, Toon / Cel-Shaded, Casual / Mobile Style, Pixel Art, Anime / Manga, Low-Poly Stylized, PS1 / Retro 3D, and game-look names such as Roblox, Minecraft, and CS2, plus Other for a custom phrase. The full list is in the editor. Those names are not partnerships.

### What resolution are the textures?

Up to 4K (4096×4096) PNG on Mid and Senior. Junior is limited to 1K.

### Which maps can I get?

Base Color first. Then Normal, Height, Roughness, Metallic, and Ambient Occlusion, depending on what you generate. The public pricing page describes full PBR generation as those maps.

### Can the textures have problems?

Yes. Messy cuts, vague prompts, or a style that does not match the sentence can leave artifacts. Clean regions and a specific prompt per color are the usual fix. Generate again. The Terms describe outputs as provided as-is.

## Using the atlas

### How do I get the maps into a game?

Download the PNGs and assign them to one material. UV every mesh onto the regions it should sample. Unity, Unreal, Godot, and Blender all accept the images. Unity's Lit shader uses Smoothness, so you may invert Roughness.

### Do I upload my model?

No. The trim sheet editor has no model upload. If you see older copy that talks about uploading a GLB and keeping the mesh local, that describes TextureFast, not this workflow.

### Can I use it with Blender?

Yes. Model and unwrap in Blender. Generate the atlas in TrimSheetFast. Connect the PNGs to a Principled BSDF. There is no TrimSheetFast Blender add-on.

### Is it a fit for game developers?

Yes, for props, modular kits, and environment support that can share a sheet. Unique hero assets still want a paint tool.

### Is it a fit for archviz?

The product includes archviz as a starting goal, for wood, stone, metal, and fabric packed into an atlas you drop into Blender, 3ds Max, or a similar DCC. A single seamless floor with no layout is a tiling-material job, not a trim sheet.

## Plans and billing

### How do tokens work?

Each generation spends tokens based on quality level and resolution. The editor shows the cost before you run it. Subscription balances follow the billing cycle. Current numbers are only on https://trimsheetfast.com/pricing.

### What are the plans?

Starter, Pro, Ultra, and Max. Monthly and yearly billing are offered. Enterprise, including API access, is requested through the contact form. Current prices are on https://trimsheetfast.com/pricing.

### Can I use the textures commercially?

Yes on paid plans, for games, films, ads, and other commercial projects, under the Terms. You still need rights to what you put in the prompts, and you still review the maps.

### How do I cancel?

Log in, open Settings, and cancel there.

### Are payments stored on TrimSheetFast?

No. The site says card details are not stored by TrimSheetFast. Checkout is a third-party processor. Public FAQ copy names Visa, Mastercard, and American Express among the methods checkout can offer.

### What about refunds?

Refund terms are on https://trimsheetfast.com/terms.

## Privacy

### Are my models and prompts private?

The trim sheet editor does not take a 3D model.

The pricing page labels paid plans NDA-safe and says the service does not train on your assets. The Privacy Policy says creative assets are not sold, not used to build advertising profiles, and not used to train models, and that TrimSheetFast does not store card details.

Generation runs online. The Terms allow TrimSheetFast to process prompts and outputs so the service can run. The legal page is https://trimsheetfast.com/privacy.

### Who owns the output?

You retain ownership of your prompts and generated textures. TrimSheetFast does not claim ownership of them.

## Comparisons

### Is TrimSheetFast better than Substance 3D Painter?

Painter is for a unique texture on one mesh. TrimSheetFast is for a shared atlas. Use both if the kit shares a sheet and one hero prop needs brushes. Full note: [TrimSheetFast vs Substance 3D Painter](vs/substance-3d-painter.md).

### How does it compare with Photoshop?

Photoshop is a common way to assemble a trim sheet by hand. TrimSheetFast generates the filled sheet from the layout and the prompts. See [TrimSheetFast vs Photoshop](vs/photoshop.md).

### How does it compare with Quixel Mixer?

Mixer blended material layers by hand and is no longer the active product it was. TrimSheetFast builds a custom atlas from a layout and prompts. Use Mixer only if an old project still depends on it.

https://trimsheetfast.com/vs/quixel-mixer

## Support

Email team@trimsheetfast.com, use https://trimsheetfast.com/contact, or message @trimsheetfast on X. Public copy says support email is typically answered within 24 hours. The support level on a plan is listed on the pricing page.

If a generation fails before it finishes, the editor says no tokens were deducted. The error panel includes a code you can send to support.
