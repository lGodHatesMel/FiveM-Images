# FiveM-Images

Public asset CDN for FiveM resources, served through [jsDelivr](https://www.jsdelivr.com/)'s
GitHub-backed CDN rather than `raw.githubusercontent.com` (which is rate-limited and not
intended for this).

Repo: https://github.com/lGodHatesMel/FiveM-Images

Base URL:

```
https://cdn.jsdelivr.net/gh/lGodHatesMel/FiveM-Images@main/<Folder>/<file>
```

Folder names are capitalized (`Animations`, `Vehicles`, `Clothing`) and jsDelivr paths are
case-sensitive — match the case exactly or the request 404s.

Pin to a tag instead of `@main` once a folder's contents are stable — jsDelivr caches `@main`
aggressively, so a tagged version is the reliable way to force a refresh after replacing files.

## Layout

```
FiveM-Images/
  Animations/   preview images for ghm-animations (see naming below)
  Vehicles/
  Clothing/
```

## Animations/

Fallback tier for ghm-animations' preview images, one step below the Bablo CDN
(`assets.babloresources.com`) it normally pulls from and one step above the resource's own
local `web/custom_previews/` copy.

Two files per animation, flat, no subfolders:

```
Animations/<name>.webp            animated hover preview
Animations/<name>_preview.webp    static poster
```

`<name>` is the bare animation name ghm-animations itself uses (`Main:playAnimation`'s
argument) — the same id the ghm-animations provider in
[FiveM-Animation-Recorder](https://github.com/Jarvis095/FiveM-Animation-Recorder) uses as its
output filename, so a captured file can be copied in here unrenamed.

## Vehicles/ and Clothing/

Not wired up to anything yet. Layout to be decided before first use — vehicle previews will
likely need a model-hash-based key, clothing likely component+drawable+texture, neither of
which is the flat name-based scheme Animations/ uses.
