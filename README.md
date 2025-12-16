# Texture Painter

A free, browser-based 3D texture painting tool. Paint directly on 3D models, add stickers/decals, and export the results. No installation, no account, no subscription required.

**[Try it live on GitHub Pages](https://aphene.github.io/texture-painter/)**

![Texture Painter Screenshot](screenshot.png)

## Features

- **Spray Paint** - Randomized spray pattern for weathering and grunge effects
- **Brush** - Standard brush with adjustable opacity and hardness
- **Sticker/Decals** - Place any image as a sticker with rotation control
- **Eraser** - Restore original texture
- **Eyedropper** - Pick colors from the texture
- **Turntable** - Auto-rotate for easy viewing

### Additional Features

- Drag & drop support for models and textures
- 32-color palette + custom color picker
- Undo support (Ctrl+Z, up to 20 states)
- Export painted texture as PNG
- Export complete model as GLB
- Keyboard shortcuts for fast workflow

## Supported Formats

### Import
| Format | Extension | Notes |
|--------|-----------|-------|
| OBJ | `.obj` | Wavefront OBJ |
| glTF | `.gltf`, `.glb` | GL Transmission Format |
| FBX | `.fbx` | Autodesk FBX |

### Export
| Format | Extension | Notes |
|--------|-----------|-------|
| PNG | `.png` | Texture only |
| GLB | `.glb` | Full model with texture |

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `B` | Brush tool |
| `S` | Spray paint tool |
| `E` | Eraser tool |
| `R` | Rotate view |
| `I` | Eyedropper |
| `Ctrl+Z` | Undo |

## Usage

1. **Load a model** - Click "Load 3D Model" or drag & drop an OBJ/GLB/FBX file
2. **Paint** - Select a tool and paint directly on the 3D model
3. **Add stickers** - Click the Sticker tool, load an image, and click on the model
4. **Export** - Save your painted texture or the complete model

### Demo Model

A sample textured model is included in the `demo/` folder:
- `mesh.obj` - Suzanne monkey model
- `albedo.png` - AI-generated texture

## Local Development

Just open `index.html` in your browser. No build step required.

For development with live reload:
```bash
npx serve .
```

## Hosting on GitHub Pages

1. Fork this repository
2. Go to Settings → Pages
3. Set source to "Deploy from a branch" → `main` → `/ (root)`
4. Your site will be live at `https://yourusername.github.io/texture-painter/`

## Browser Compatibility

| Browser | Status |
|---------|--------|
| Chrome | ✅ Recommended |
| Edge | ✅ Works well |
| Firefox | ✅ Works |
| Safari | ⚠️ May have WebGL issues |

Requires WebGL 2.0 support.

## How It Works

1. **Raycasting** - Mouse position is converted to a 3D ray
2. **UV Mapping** - Ray intersection with the model gives UV coordinates
3. **Canvas Drawing** - UV coords map to pixel positions on the 2D texture
4. **Live Update** - Canvas changes are synced to the 3D texture in real-time

## Credits

Built with [Three.js](https://threejs.org/)

## License

MIT License - feel free to use, modify, and distribute.
