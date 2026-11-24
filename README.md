# ML4W Wallpaper Collection (llawn fork)

A trimmed fork of the [ML4W wallpaper collection](https://github.com/mylinuxforwork/wallpaper) by Stephan Raabe: wallpapers that fit tiling window managers well. It is used as the `images/ml4w` git submodule of [llawn/wallpaper](https://github.com/llawn/wallpaper), and works just as well on its own.

![image](https://github.com/user-attachments/assets/9f94272d-7278-4599-801c-8b104ca746c8)

## At a glance

- **207 images**: 153 `.jpg`, 3 `.jpeg`, 50 `.png` and one animated `.gif` (`street2.gif`), about 685 MB in total.
- **Mostly high resolution**: of the 206 images listed in `wallpapers.toml`, 136 are 4K wide or larger, 48 are around 1440p, 20 are around 1080p and 2 are smaller (the smallest is 1366×768).
- **Mostly 16:9**: 157 of them are 16:9 and 11 are 16:10. 25 have a clearly different shape: 3:2, ultrawide or square.
- Everything sits flat in the repository root, so you can point a wallpaper picker (Waypaper, Noctalia, …) straight at the folder.

## Differences from upstream

- **13 wallpapers removed**: `Solitary-Glow.png`, `ai-machine.png`, `gdtography.jpg`, `honkadaloonga.png`, `hyprland.jpg`, `kath.jpg`, `retro-truck.png`, `solitary-peaks.jpg`, `space-bullet.jpg`, `spaceship-start.jpg`, `sunset-01.png`, `the-sphere.png`, `winter-is-here.png`.
- **`wallpapers.toml` added**: a metadata file with one `[[wallpaper]]` entry per image (the GIF is not listed).

## `wallpapers.toml`

Every entry has these fields:

| Field | Content |
|---|---|
| `file` | File name in this folder |
| `title` | Readable title, taken from the file name |
| `artist` | `Unknown (ML4W collection)`: the original authors are not recorded |
| `license`, `license_detail` | `all-rights-reserved`, see [Licensing](#licensing) |
| `source` | The upstream repository |
| `download` | Raw GitHub URL of the file in this fork |
| `sha256` | Checksum of the file |
| `resolution` | `[width, height]` in pixels |

The first line points to the JSON schema in the parent repository (`../../wallman/schema/wallpapers.schema.json`), so editors with [taplo / Even Better TOML](https://taplo.tamasfe.dev/) check the file as you type, and `just validate` in the parent repository enforces it.

## Licensing

The repository is under GPL-2.0 (see `LICENSE`), but that license does **not** cover the images. Upstream gathered them from [r/wallpapers](https://www.reddit.com/r/wallpapers/), [4kwallpapers.com](https://4kwallpapers.com) and [wallsbyjfl](https://buymeacoffee.com/wallsbyjfl/posts/11032), and their authors keep their rights. The wallsbyjfl images are AI-generated (Midjourney). This is why the parent repository's "human-made art only" rule and its size rules do not apply to this external collection.

## Installation

On its own:

```sh
cd ~/Pictures   # or any other location
git clone --depth=1 https://github.com/llawn/ml4w.git
```

As part of [llawn/wallpaper](https://github.com/llawn/wallpaper):

```sh
git clone --recurse-submodules https://github.com/llawn/wallpaper.git
# or, in an existing clone:
git submodule update --init images/ml4w
```

If you use the ML4W Dotfiles for Hyprland, select the folder with Waypaper.

## Updating

Get the latest version of this fork:

```sh
cd ~/Pictures/ml4w
git pull
```

To bring in new wallpapers from upstream (maintainers only), add the upstream remote once with pushing disabled, then merge:

```sh
git remote add upstream https://github.com/mylinuxforwork/wallpaper.git
git remote set-url --push upstream DISABLED
git fetch upstream
git merge upstream/main
```

New upstream images also need a `wallpapers.toml` entry.

## Wallpaper resources

Great places to find more wallpapers:

- https://www.reddit.com/r/wallpapers/
- https://4kwallpapers.com
- https://buymeacoffee.com/wallsbyjfl/posts/11032
