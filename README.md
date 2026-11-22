# DME+KLR lite

Prebuilt packages of the 944 Turbo DME + KLR simulator and its dashboard:
live mode, the code debugger, snapshots and the regression tests, from a
compiled simulator. No Verilator, Icarus Verilog or C++ compiler needed.

This repository holds only the releases, the Windows installer and the
user manual. The simulator's source is not published.

## License

Free for personal, non-commercial use; no redistribution or reverse
engineering. See [LICENSE.txt](LICENSE.txt). The packages include no ECU
firmware: you supply your own DME and KLR ROM images, which belong to
their owners (Bosch, Porsche and others) and are not covered by it.
Third-party components are listed in [NOTICE.txt](NOTICE.txt).

## Getting it

Download from the [Releases page](https://github.com/whalenlg/dmeklr-lite/releases):

| Platform | Archive |
|---|---|
| macOS (Apple Silicon) | `dmeklr-lite-<version>-macos-arm64.tar.gz` |
| Linux x86_64: Arch, Ubuntu 22.04 or newer, Debian 12, Fedora, and any other with glibc 2.35+ | `dmeklr-lite-<version>-linux-x86_64.tar.gz` |
| Windows x86_64 | `dmeklr-lite-<version>-windows-x86_64.zip` |

There is one Linux package for every distribution; each release is
tested on a clean Arch Linux and a clean Ubuntu. You need Node.js 18 or
newer, Python (for the annotated listings and the MAPS tabs' graphs), and
ROM images of your own.

## ROM images

The packages ship no ROM images. Put dumps of your DME and KLR EPROMs in
the package's `bin_images/dme` and `bin_images/klr` folders (a `.bin`,
Intel HEX or `.mem`, any name), or load them from the dashboard. Images
are shared in the [944 Turbo ROM thread on carpokes](https://carpokes.com/viewtopic.php?t=4424).
When your image is one of the standard ones ('86, '89 and Performance DME;
'86, '87 and '89 KLR) it is recognized by its contents, and its annotated
disassembly (labels and comments) is made from it on your computer. A
1986 DME chip is 4 KB: put a full 8 KB DME image beside it and the package
combines them (see the user manual).

On Windows, one command (PowerShell, a normal window) installs Node.js and
Python if they are missing, the latest release, and a desktop shortcut:

```powershell
irm https://raw.githubusercontent.com/whalenlg/dmeklr-lite/main/install/install_lite_windows.ps1 | iex
```

The [user manual](docs/USER_MANUAL.md) covers setup on each platform and
how to use the dashboard.

_This repository's files are updated by the release workflow; changes made
here directly are overwritten at the next release._
