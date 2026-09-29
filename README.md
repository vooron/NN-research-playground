# NN Research Playground

An interactive, single-page playground for building intuition about how a small feed-forward neural network (MLP) works: what the weights of one layer actually do to the space, how activations bend it, and why width and depth help.

Everything runs in the browser: two classes of points, a tiny network with every weight on screen, and gradient-descent training you can pause at any step.

## What you can explore

- **One layer as a geometric transform.** For a 2 → 2 layer, `W·x + b` is an affine map: rotate, scale, shear and shift sliders build the matrix, and `det W` shows how areas change (a determinant of 0 squashes the plane onto a line).
- **Activations.** None, tanh, ReLU, Leaky ReLU and sin, applied to the same weights, so you see exactly how each one bends, folds or repeats the space.
- **Layer by layer.** Each layer tab shows the space *before* the layer, the space *after* it (with the input grid carried through), and that layer's weights.
- **Neuron fold lines.** Every neuron is a line (z = 0) where it switches; the decision boundary can only bend on these lines. Tags name each line (`h₁`, `L2·h₁`, …).
- **Per-neuron maps.** What each neuron responds to across the input plane, with its fold line and value range (and "always on / always off" for ReLU).
- **Whole network view.** The final decision boundary pulled back to the input plane, the output neuron as an angle / offset / confidence line, and its own axis: every point placed at its z on the sigmoid.
- **Height map.** The output's z as a 3-D surface over the input plane, cut by the level plane z = 0; the cut is the decision boundary.
- **Width and depth.** Up to 3 hidden layers of up to 6 neurons, and datasets from linearly separable to a spiral that needs depth.
- **Probing.** Hover anywhere on the input plane to see the values flow through every neuron.
- **Navigation.** Pan, zoom and rotate every chart; double-click to reset.

## Running it

No build step and no dependencies to install. Open `index.html` in a browser:

```bash
open index.html
```

Or serve the folder with any static server and visit it.

## Suggested path

1. Start on **Input → Output**: the data's gap is tilted, the boundary is a vertical line. Turn the output neuron's angle to fix it.
2. Open **Layer 1** and use the transform sliders to rotate, stretch and shift the space; watch the boundary follow.
3. Switch the activation to tanh or ReLU and see the same transform bend.
4. Pick **Ring**: a straight line can't separate it. Add width, then press **Train**.
5. Try **Spiral** with more depth.

## Author

Bochok Viacheslav
