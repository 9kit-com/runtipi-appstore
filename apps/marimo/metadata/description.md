# Marimo

[Marimo](https://github.com/marimo-team/marimo) is a reactive Python notebook that stores notebooks as pure Python files and can also serve them as web apps.

## What This App Does

This package starts the official marimo container in editor mode and persists your workspace in the app data directory.

On first start it creates:

- `app.py`: a starter marimo notebook
- `requirements.txt`: a starter dependency file

Your files are stored in `/app` inside the container and survive restarts.

## Access

Open the web UI and edit `/app/app.py` in the browser.

The container exposes marimo on port `8080` and includes a health check against `/health`.

## Notes

This app uses marimo's prebuilt `0.21.1-sql` container image, which supports both `amd64` and `arm64`.

If you need a fully custom production image with your own build steps, follow marimo's upstream Docker deployment guide.
