# Paper Bloom

Turn any photo into a 3D paper pop-up card, then send it to someone as a short video.

Live site: https://chandni-v1.github.io/paper-bloom/

## How it works

- **AI cut-outs in the browser.** A depth model (Depth Anything V2 Small) works out what is near and far. A subject model (U-2-Netp) finds the main subject. Both run on the visitor's device with ONNX Runtime Web, so photos are never uploaded.
- **Four pop-up styles.** Stage, Tunnel, Hero and Centre pop. The best fit for each photo is picked automatically.
- **3D card.** Built with three.js. Drag to turn it, scroll or pinch to zoom, and tap to open.
- **Sending.** Records a 10-second video of the card opening. On phones, "Share video" opens the share sheet (WhatsApp, Instagram, Messages, Mail…) with the video and a "make your own" link.

## Files

| Path | What it is |
|---|---|
| `index.html` | The whole app |
| `thumb.png` | Link-preview image |
| `ort.wasm.bundle.min.js`, `ort-wasm-simd-threaded.wasm` | ONNX Runtime Web (runs the AI models) |
| `depth.part0.bin`, `depth.part1.bin` | Depth model, split in two so each part is under GitHub's 25 MB web-upload limit |
| `u2netp.onnx` | Subject cut-out model |

## Credits and licences

- Depth Anything V2 Small, from onnx-community on Hugging Face. Apache-2.0.
- U-2-Netp, from BritishWerewolf/U-2-Netp on Hugging Face. Apache-2.0.
- ONNX Runtime Web: MIT.
- three.js: MIT.
