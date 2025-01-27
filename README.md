<img src="data/icons/hicolor/scalable/apps/com.ranfdev.Geopard.svg" align="left" height="150px" vspace="10px">

Geopard
=======

Geopard is a GTK 4 Gemini client written in Rust.

<br>

![4-light](data/screenshots/4-light.png#gh-light-mode-only)
![4-dark](data/screenshots/4-dark.png#gh-dark-mode-only)

## Some notable features
- **Colors!**
  The browser will have a different color for each domain you visit.

- **Fast (async core + caching)**:
  Streams content by default. That means you can open pages even when you have
  connection speeds of Kb/s.
  It also caches pages in the history, so you can go back/forward in an instant

- **Can download binary files**:
  The download will start as soon as you open the corresponding link.
  You can always cancel it by opening another page.

- **It works.** <sup><sub>_Until I find another bug..._</sub></sup>

## Technical details
Under the hood, it uses GTK 4 and Rust. Everything related to IO is asynchronous.
To do that, it makes use of Rust's async/await capabilities and the `async-std` crate.

## How to change settings
You should find the configuration files in `~/.config/geopard/`
If you use flatpak, they are in `~/.var/app/com.ranfdev.Geopard/config/geopard/`.
In the future I will probably introduce a settings GUI.

## How to build

### With Flatpak
If you have `gnome-builder` installed, use it to the open the folder of the source
code and hit the run button.

### Build with Nix
If you have the [nix](https://nixos.org/) package manager and flakes enabled, you can simply do:

```sh
git clone https://github.com/ranfdev/Geopard.git
nix build
./result/bin/geopard
```

### General build instructions
Install these development packages:
- `gtk4`
- `glib`
- `rust` (with `cargo`)
- `openssl`
- `pkg-config`
- `meson`

Clone, compile, install.

```sh
git clone https://github.com/ranfdev/Geopard.git
cd Geopard
meson --prefix=/usr build
ninja -C build
sudo ninja -C build install
```

> **Note**
> You can use a `local-build.sh` script provided with project's repository to quickly rebuild and test your changes.

## License
<p>
<img src="https://www.gnu.org/graphics/gplv3-with-text-136x68.png" alt="GPLv3 logo" align="right">
This repository is licensed under the terms of the GNU GPLv3 license. You can find a copy of the license in the LICENSE file.
</p>

## Authors
Lorenzo Miglietta ([ranfdev](https://ranfdev.com))
