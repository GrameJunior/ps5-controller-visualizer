# PS5 DualSense Controller Visualizer

Real-time, web-based PS5 DualSense controller visualizer that shows button presses, sticks, triggers, and touchpad input on screen — perfect for adding a live controller overlay to your stream via OBS (browser source).

![Alt text](public/Images/PS5Controller.gif)

![Alt text](public/Images/Gameplay.gif)

![Alt text](public/Images/Controller_Skin.jpg)

## Features

- Real-time display of:
  - Buttons (X, O, Δ, ▢)
  - D-Pad
  - L1/R1 and analog L2/R2 triggers
  - Left/Right sticks + press
- Clean, simple on-screen layout

## How to Use

1. Connect your PS5 DualSense controller.  
2. Run the visualizer application.  
3. Press buttons and move sticks — the visualizer updates instantly.

## How to Use in OBS
1. Add a **Browser Source** in OBS.
2. Set URL to `http://localhost:5173/ps5-controller-visualizer/` (or your local file path if built). Add `?skin=<name>` to use a skin.
3. Set Width: `810`, Height: `810`.
4. Check "Shutdown source when not visible" to save resources.
5. The background will be transparent, showing only the controller.

## Skins
Pick a skin with the `skin` URL parameter, e.g. `http://localhost:5173/ps5-controller-visualizer/?skin=neon`.

| Skin | Look |
| --- | --- |
| *(none)* | Default: white main frame, black front plate |
| `neon` | Black main frame, neon green front plate |

An unknown skin name falls back to the default and logs the available skins to the browser console.

### Adding a skin
1. Create `skins/<name>.css`. It is only loaded when `?skin=<name>` is used.
2. Scope every rule to `.skin-<name>` (e.g. `.controller.ps5.skin-<name>`) and override only what differs from `style.css`.
3. Put images next to it (e.g. `skins/<name>/body.png`) and reference them with relative URLs like `url('./<name>/body.png')`.

The default look lives in `style.css`; edit it directly for colors, shadows, and positions.
