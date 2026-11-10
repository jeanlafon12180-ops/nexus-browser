# NEXUS BROWSER

**NEXUS BROWSER** is an experimental desktop browser project for Windows, macOS and Linux.

- **Project version:** 0.1.0-alpha
- **Rendering engine target:** Mozilla Gecko
- **JavaScript engine:** SpiderMonkey (through the Firefox platform)
- **Status:** Early planning and architecture stage

> This repository does not yet contain a working browser. The first milestone is to establish a maintainable Firefox-based desktop distribution with NEXUS branding.

## Product goals

- Familiar tabbed browsing experience inspired by Firefox.
- Address bar, navigation controls, bookmarks and history.
- Private browsing and clear privacy controls.
- Tracker protection and configurable content blocking.
- Optional NEXUS IA integration, designed with explicit privacy boundaries.
- Build and packaging targets for Windows, macOS and Linux.

## Technical direction

The project will investigate a **Firefox-based distribution**, not an Electron wrapper pretending to use Gecko. Gecko and SpiderMonkey are deeply integrated into Firefox; reusing them on desktop means adapting and building the Firefox codebase, then maintaining a controlled set of NEXUS patches and branding.

GeckoView is primarily an Android embedding technology and is not the desktop integration shortcut for this project.

## Repository layout

```text
docs/          Architecture, roadmap and development notes
branding/      NEXUS visual identity assets (to be added)
build/         Reproducible build configuration (to be added)
patches/       Small, documented Firefox patches (to be added)
```

## Current milestone

**0.1.0-alpha — Foundation**

1. Document the Firefox-based architecture.
2. Define the initial product scope and privacy principles.
3. Establish the development environment and build strategy.
4. Produce a first locally buildable prototype before adding product features.

## Upstream project

- Mozilla Firefox source: https://hg.mozilla.org/mozilla-central/
- Firefox source documentation: https://firefox-source-docs.mozilla.org/

## License

The project will preserve the licenses and notices of all upstream Mozilla components. Licensing and redistribution requirements must be reviewed before publishing binaries.
