# Align browser demo

[Open the live demo](https://shubin123.github.io/desert-ant-align-demo/)

Refine word timestamps against audio using the original Align models by Desert Ant Labs.

Powered by [Desert Ant Labs](https://desertant.com) 🐜. The model, weights, and SDK are by Desert Ant Labs B.V.; this independent demo is maintained by Shubin123. See [ATTRIBUTION.md](ATTRIBUTION.md) and the [SDK license](https://license.desertant.com/1.0).

## Run locally

Serve the site directory over HTTP:

```sh
python3 -m http.server 8080 --directory site
```

Open http://localhost:8080. No build step or backend is required. Original model weights and the pinned LiteRT runtime download on first inference. This independent browser pipeline does not use the native Align SDK or send usage telemetry.

## Deployment

The GitHub Actions workflow publishes the site directory to GitHub Pages on pushes to main. Choose GitHub Actions as the Pages source.

## Experimental adaptation

This app uses the original v1.1.0 coarse/fine LiteRT weights, mel filter bank, and correction calibrator. Its JavaScript pipeline adapts Desert Ant Labs' Swift frontend, lexical context, batch prediction, calibration, and structural fallback. This is not the official Align SDK. It has been checked with real speech and compared against the native SDK; timestamps can differ between runtimes, so no parity or accuracy claim is made.

## Upstream

- [SDK documentation](https://github.com/Desert-Ant-Labs/desert-ant-core/blob/main/docs/models/align.md)
- [Original model](https://huggingface.co/desert-ant-labs/align)
- [Desert Ant Labs](https://desertant.com)

Experimental browser adaptation. Supply audio and a word-timestamp JSON array. Supports nine languages.
