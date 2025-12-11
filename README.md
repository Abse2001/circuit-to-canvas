# circuit-to-canvas

Draw [Circuit JSON](https://github.com/tscircuit/circuit-json) into a Canvas- works with any canvas object (Node/Vanilla)

[![NPM Version](https://img.shields.io/npm/v/circuit-to-canvas)](https://npmjs.com/package/circuit-to-canvas)

```tsx
const drawer = new CircuitToCanvasDrawer(canvasOrCanvasRenderingContext2d)

// Sets the internal transformation matrix for all operations
drawer.setCameraBounds({ minX: 0, maxX: 100, minY: 0, maxY: 100 })

drawer.configure({
  colorOverrides: {
    topCopper: "#ff0000"
  }
})

// Accepts a circuit json array, by default draws on all layers
drawer.drawElements([pcbPlatedHole], {
  layers: ["top_copper"]
})
```

## Implementation Notes

There are two "types" of layers:

- Specific drawing layers e.g. "top_copper"
- Layer groups "top" (includes "top_copper", "top_soldermask")

inner layers go by the name inner1, inner2 etc.
