# Custom Spritesheet Font Renderer for Godot 4.x

> **Prototype / Early Development** - This add-on is functional but incomplete.
> Expect Bugs, missing functionality, future itterations to break current setups.

TextToPNG lets you use hand-drawn and or pixel-art fonts in your godot 4.x project without converting them to a `.tff` or other type of font. Manually add your spritesheet in the `AlphabetFrames.tscn` (This is planned to be automated in the future.). It will then render your typed text directly in the editor.

## Requirments

- Godot 4.x
- A spritesheet PNG with characters laid out in expected order.
(Example coming soon)

## Installation
1. Download or clone this repository 
(currently not setup as a plugin just drag and drop the TextToPNG to your project)

## Spritesheet Format

Your spritesheet must have characters arranged in the following order:
```
A a B b C c D d E e F f G g H h I i J j K k L l M m
N n O o P p Q q R r S s T t U u V v W w X x Y y Z z
0 1 2 3 4 5 6 7 8 9 . , ! ? ' [space]
```
(This is planned to be adjustable so you can add, remove or adjust the order as needed in the future.)
Each cell in the sheet must be a **UNIFORM SIZE** (e.g. all characters 32x32 pixels)

## Setting up your font

### 1. Open AlphabetFrames.tscn
1. In the TextToPNG folder click and open the AlphabetFrames.tscn folder
2. In the **Inspector** find the `SpriteFrames` resource attached to the node
3. Click the resource to open the **SpriteFrames editor** at the bottom of the screen


### 2. Replace the Frames
1. Select the animation currently that exist.
2. Delete the current frames
3. Add your own frames in order matching the character layout above
4. Save the scene.

> This manual process is temporary. Automatic spritesheet import is planned.

## Planned Features

### Spritesheet Setup

- [ ] Upload your own PNG and auto-generate a SpriteFrames resource
- [ ] Configurable grid size (columns/rows) for custom sheet layouts
- [ ] Editor preview of sheet layout and character mapping

### Core

- [ ] Accurate pixel-height based `font_size` (currently a scale multiplier)
- [ ] Proportional character spacing (non-monospaced rendering)
- [ ] Descender support for characters like g, j, p, q, y
- [ ] Word wrapping with a configurable max width

### Quality of Life

- [ ] Validation warnings in the editor for missing or misconfigured sheets

## Known Issues

- `font_size` is a scale multiplier relative to source texture size, not a true
  pixel height  a value of 32 means 0.32x scale, not 32px tall
- SpriteFrames setup is entirely manual no import automation yet
- No word wrapping long lines will overflow their container
- Monospaced only all characters take up equal horizontal space
- Characters not in the supported set fall back to `!`


## Contributing

This project is in early prototype stage. Bug reports and suggestions are welcome
via [GitHub Issues](#). Pull requests are appreciated but please open an issue first
to discuss larger changes.


## License

MIT License — see `LICENSE` for details.
