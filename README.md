<div align="center">

<img src="snap/gui/tabiew.png" alt="Tabiew logo" width="128" />

# Tabiew

**View and query CSV, Parquet, JSON, Excel and SQLite files in the terminal.**

[![tabiew](https://snapcraft.io/tabiew/badge.svg)](https://snapcraft.io/tabiew)
[![Base: core26](https://img.shields.io/badge/Base-core26-2C8C3C?logo=canonical&logoColor=white)](https://snapcraft.io/core26)
![Confinement: strict](https://img.shields.io/badge/Confinement-strict-2C8C3C)
[![Maintainer: sidaliteir](https://img.shields.io/badge/Maintainer-sidaliteir-2C8C3C?logo=snapcraft&logoColor=white)](https://snapcraft.io/publisher/sidaliteir)
![Architectures: amd64, arm64](https://img.shields.io/badge/Architectures-amd64%20%7C%20arm64-2C8C3C?logo=linux&logoColor=white)

[Getting Started](#getting-started) · [Configure](#configure) · [Limitations](#limitations) · [Build](#build) · [Support](#support) · [License](#license)

Unofficial snap packaging for [Tabiew](https://github.com/shshemi/tabiew), a terminal viewer for tabular data with sorting, filtering, fuzzy search and SQL queries.

</div>

---

## Getting Started

<a href="https://snapcraft.io/tabiew"><img alt="Get it from the Snap Store" src="https://snapcraft.io/en/dark/install.svg" width="180"></a>

```bash
sudo snap install tabiew
tabiew.tw data.csv
```

For the shorter upstream command, create the alias if `tw` is not already available:

```bash
sudo snap alias tabiew.tw tw
```

Tabiew detects the format from the file extension; override it with `-f`, for example `tw data.txt -f parquet`. Use `tw ctl ps` to list running instances and `tw ctl --help` to control them.

## Configure

There are no `snap set` options. Tabiew saves its settings and theme from inside the application to `~/snap/tabiew/current/.config/tabiew`.

For files on removable storage:

```bash
sudo snap connect tabiew:removable-media
```

## Limitations

- Files must be in a normal folder under your home directory or on connected removable storage. Hidden folders directly under your home directory are not accessible.
- Settings from a host installation in `~/.config/tabiew` are not read.
- `tw ctl` reaches instances started from this snap only. The snap renames Tabiew's shared-memory channel to `snap.tabiew.*`, which strict confinement requires.

## Build

```bash
git clone https://github.com/sidalit/tabiew-snap.git
cd tabiew-snap
sudo snap install snapcraft --classic
snapcraft pack
```

## Support

- **Installation or snap issues:** [open a packaging issue](https://github.com/sidalit/tabiew-snap/issues).
- **Application bugs:** [report them upstream](https://github.com/shshemi/tabiew/issues).

## License

Snap packaging: [MIT](LICENSE).
