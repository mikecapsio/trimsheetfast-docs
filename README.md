# TrimSheetFast Public Documentation

TrimSheetFast is a browser tool for game-ready trim sheets. You draw guide lines, paint regions with color IDs, and write a material prompt for each color. The generator fills that layout and exports one PBR atlas: Base Color, Normal, Height, Roughness, Metallic, and Ambient Occlusion. You UV many modular meshes onto that same sheet in Blender, Unity, Unreal Engine, or Godot.

The sheet is the product. TrimSheetFast does not build a 3D mesh, and it does not paint a unique texture onto one model's UVs.

Two other products from the same maker do those other jobs:

- [TextureFast](https://texturefast.com) textures a UV-unwrapped 3D model. The mesh stays in the browser.
- [TexturesFast](https://texturesfast.com) generates seamless, tileable PBR materials that are not locked to a trim layout.

This repository is only about TrimSheetFast.

## Documentation

- [What a trim sheet is](docs/what-is-a-trim-sheet.md)
- [Getting started](docs/getting-started.md)
- [Free planner and builder](docs/free-tools.md)
- [Frequently asked questions](docs/faq.md)
- [Trim sheets for modular game kits](docs/for/modular-game-kits.md)
- [TrimSheetFast vs Substance 3D Painter](docs/vs/substance-3d-painter.md)
- [TrimSheetFast vs Photoshop](docs/vs/photoshop.md)

## At a glance

- Open the trim sheet editor in the browser. The editor is built for a desktop screen and a mouse.
- Cut the square with guide lines. Drag an endpoint to shorten a line. Double-click a line to delete it.
- Start from a layout preset when it matches the kit: H-trims, V-pipes, 8-band, Quad, 3x3, or Hero.
- Assign color IDs to regions. Each color is one material, with its own prompt. A generation needs prompts on at least two colors.
- Color IDs in the editor are red, orange, yellow, green, blue, purple, pink, maroon, and brown.
- Pick a style preset so every region shares one art direction. The preset list is in the editor, from AAA Photorealistic and Hand-Painted through Pixel Art, and game-look names such as Roblox, Minecraft, and CS2.
- Pick a quality level: Junior, Mid, or Senior. Junior is limited to 1K. Mid and Senior can go up to 4K (4096×4096).
- Generate Base Color first. The in-app guide describes a real generation as taking about 40 seconds. If the sheet is right, generate Normal, Height, Roughness, Metallic, and Ambient Occlusion.
- Preview the atlas on the 3D plane, then download PNG maps.
- UV your own meshes onto those regions in your DCC. TrimSheetFast does not unwrap the model for you.
- Paid plans include a commercial-use license, subject to the Terms of Service.
- The free planner and the free builder run without an account. They are layout and assembly tools. Paid generation is the editor that fills prompts with AI.

## Plans

Public subscription names are Starter, Pro, Ultra, and Max, with monthly and yearly billing. Enterprise, including API access, is requested through the contact form.

Prices, token allowances, and what each plan includes change. Read them on https://trimsheetfast.com/pricing. The generate control shows the token cost for the quality level and resolution you picked.

Cancel a subscription in Settings.

## Privacy

The trim sheet editor does not ask you to upload a 3D model. You draw a layout and write prompts.

The pricing page labels paid plans NDA-safe and says the service does not train on your assets. The Privacy Policy is the legal text: no sale of creative assets, no advertising profiles, no card storage by TrimSheetFast. Generation runs online. Details are on https://trimsheetfast.com/privacy. Keep client names out of prompts unless your own policy allows them.

## Official sources

- Website: https://trimsheetfast.com
- About: https://trimsheetfast.com/about
- FAQ: https://trimsheetfast.com/faq
- Pricing: https://trimsheetfast.com/pricing
- Comparisons: https://trimsheetfast.com/vs
- Workflows by role: https://trimsheetfast.com/for
- Free planner: https://trimsheetfast.com/tools/free-trimsheet-planner
- Free builder: https://trimsheetfast.com/tools/free-trimsheet-builder
- Tools hub: https://trimsheetfast.com/tools
- Privacy Policy: https://trimsheetfast.com/privacy
- Terms of Service: https://trimsheetfast.com/terms
- Contact: https://trimsheetfast.com/contact
- Support: team@trimsheetfast.com

The live website is authoritative for current pricing, plan access, feature availability, and legal terms.

## Repository layout

- `README.md` at the repository root
- `llms.txt` at the repository root
- `docs/` for the guides
