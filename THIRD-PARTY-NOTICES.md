# Third-party notices

## vgpu — Vercel, Inc.

Parts of `index.html` are ported from the prism on [vgpu.sh](https://vgpu.sh),
whose source lives in [vercel-labs/vgpu](https://github.com/vercel-labs/vgpu)
under `apps/docs/app/[lang]/(home)/components/prism-background/`.

| In this project | Ported from |
| --- | --- |
| `roundedPrismGeometry()` | `scene/prism-mesh.ts` |
| Glass fragment shader: interior trace, Fresnel, absorption, panel highlight | `pipelines/shared/glass/glass.wgsl`, `glass-common.wgsl` |
| Glass accent: inner bands and bevel rims | `pipelines/light/passes/glass-accent/glass-accent.wgsl` |
| `studio()` environment | `environment/environment.wgsl` |

The ports were translated from WGSL/WebGPU to GLSL/WebGL and changed to work
on many instanced prisms instead of one fixed prism.

```
MIT License

Copyright (c) 2025 Vercel, Inc.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## three.js

Loaded at runtime from jsDelivr. MIT License, Copyright (c) 2010-2024 three.js authors.
