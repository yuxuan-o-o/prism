# prism

A small light toy: white light goes through a pattern of glass prisms or
diffraction film and comes out as colour on a wall.

One prism gives you the familiar rainbow. Thirty of them arranged in rings,
slowly turning, give you something else.

## Run it

Live at [light-prism-film.vercel.app](https://light-prism-film.vercel.app/).

Or open `index.html` in a recent Chrome, Edge or Safari. There is no build step.
It needs an internet connection the first time, because three.js is loaded
from a CDN.

## Controls

| | |
| --- | --- |
| Scroll (wheel or two fingers) | Turn the light. With a point light, turn the pattern. |
| Drag the dot | Move the light source |
| Light | Beam or point, width, brightness, dispersion |
| Element | Prism or diffraction film |
| Pattern | Rings, circle, spiral, grid, hex; which way the prisms face; add or remove a ring |
| Surface | White wall, tree shade or a dark room |
| Top bar | Reset, hide the controls, slow rotation on or off, light or dark interface, fill the browser window with the wall |

## How it works

**The light is a 2D ray trace.** The beam is split into 24 wavelengths. Each
ray is followed through the prisms with Snell's law, Fresnel reflection and
total internal reflection; the refractive index depends on wavelength, which
is what separates the colours. Diffraction film splits each ray into orders
−1, 0 and +1. Rays are drawn additively, blurred, and used as a texture.

**The wall is a shader.** It takes that light texture and adds plaster grain,
prism shadows and, optionally, moving tree shade.

**The glass is a shader too.** Each prism is a rounded mesh. For every pixel
the view ray is refracted into the solid and followed until it leaves, and the
wall is sampled where it lands. Absorption grows with the distance travelled
inside the glass.

The dispersion is exaggerated on purpose. Real glass spreads colours far less;
set Dispersion to 0 for something close to it.

## Limits

- The light is traced in the plane of the wall. The 3D glass changes how the
  prisms look, not where the light goes.
- A prism seen through another prism is not rendered.

## Credits

The glass shading, the rounded prism mesh and the studio environment are
ported from the prism on [vgpu.sh](https://vgpu.sh) by Vercel
([vercel-labs/vgpu](https://github.com/vercel-labs/vgpu), MIT). See
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md) for what came from where.

## License

[MIT](LICENSE)
