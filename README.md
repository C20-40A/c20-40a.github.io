# c20-40a.github.io

SvelteKit site for GitHub Pages deployment via GitHub Actions.

## Local development

```sh
bun install
bun run dev
```

## Build

```sh
bun run build
```

Static files are emitted to `build/`.

## GitHub Pages

The workflow is defined in `.github/workflows/deploy.yml`.

Repository settings:

1. Open GitHub repository `Settings` -> `Pages`.
2. Set `Source` to `GitHub Actions`.
3. Push to `main` to trigger deploy.

`svelte.config.js` is set so:

- repos ending with `.github.io` deploy at `/`
- other repos deploy under `/<repo-name>`
