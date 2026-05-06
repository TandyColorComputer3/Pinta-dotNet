
# Pinta.NET

**Pinta.NET** is a community fork of [Pinta](http://pinta-project.com/), with distinct branding and a reimagined user interface.  
It is **not** the official Pinta application — **please do not report Pinta.NET bugs or ask for support on [upstream Pinta](https://github.com/PintaProject/Pinta)**.

Project home / issues / discussions: [github.com/TandyColorComputer3/Pinta-dotNet](https://github.com/TandyColorComputer3/Pinta-dotNet)

Upstream badges (official Pinta only — omit or replace if you distribute this fork):

[![Translation status](https://hosted.weblate.org/widget/pinta/pinta/287x66-grey.png)](https://hosted.weblate.org/engage/pinta/)
[![Build Status](https://github.com/PintaProject/Pinta/workflows/Build/badge.svg)](https://github.com/PintaProject/Pinta/actions)

Copyright (C) 2010 Jonathan Pobst <monkey AT jpobst DOT com>

Pinta is a GTK clone of [Paint.Net 3.0](http://www.getpaint.net/), with support for Linux, Windows, and macOS.

Original Pinta code is licensed under the MIT License:
See `license-mit.txt` for the MIT License

Code from Paint.Net 3.36 is used under the MIT License and retains the
original headers on source files.

See `license-pdn.txt` for Paint.Net's original license.


## Icons are from:

- [Paint.Net 3.0](http://www.getpaint.net/)
Used under [MIT License](http://www.opensource.org/licenses/mit-license.php)

- [Silk icon set](https://github.com/markjames/famfamfam-silk-icons)
Used under [Creative Commons Attribution 3.0 License](http://creativecommons.org/licenses/by/3.0/)

- [Fugue icon set](https://p.yusukekamiyamane.com)
Used under [Creative Commons Attribution 3.0 License](http://creativecommons.org/licenses/by/3.0/)

- Pinta contributors, under the same license as the project itself
(see `Pinta.Resources/icons/pinta-icons.md` for the list of such icons)

## Building on Windows

First, install the required GTK-related dependencies:
- Install [MSYS2](https://www.msys2.org)
- From the CLANG64 terminal, run `pacman -S mingw-w64-clang-x86_64-libadwaita mingw-w64-clang-x86_64-webp-pixbuf-loader`.
  - For ARM64 Windows, use the `CLANGARM64` terminal and replace `clang-x86_64` with `clang-aarch64`.

Pinta can then be built by opening `Pinta.sln` in [Visual Studio](https://visualstudio.microsoft.com/).
Ensure that .NET 8 is installed via the Visual Studio installer.

For building on the command line:
- [Install the .NET 8 SDK](https://dotnet.microsoft.com/).
- Build:
  - `dotnet build`
- Run:
  - `dotnet run --project Pinta`

## Building on macOS

- Install .NET 8 and GTK4
  - `brew install dotnet-sdk libadwaita adwaita-icon-theme gettext webp-pixbuf-loader`
  - For Apple Silicon, set `DYLD_LIBRARY_PATH=/opt/homebrew/lib` in the environment so that Pinta can load the GTK libraries
  - For Intel, you may need to set `DYLD_LIBRARY_PATH=/usr/local/lib` when using .NET 9 or higher
- Build:
  - `dotnet build`
- Run:
  - `dotnet run --project Pinta`

## Building on Linux

- Install [.NET 8](https://dotnet.microsoft.com/) following the instructions for your Linux distribution.
- Install other dependencies (instructions are for Ubuntu 22.10, but should be similar for other distros):
  - `sudo apt install autotools-dev autoconf-archive gettext intltool libadwaita-1-dev`
  - Minimum library versions: `gtk` >= 4.18 and `libadwaita` >= 1.7
  - Optional dependencies: `webp-pixbuf-loader`
- Build (option 1, for development and testing):
  - `dotnet build`
  - `dotnet run --project Pinta`
- Build (option 2, for installation):
  - `./autogen.sh`
    - If building from a tarball, run `./configure` instead.
    - Add the `--prefix=<install directory>` argument to install to a directory other than `/usr/local`.
  - `make install`

## Building and Debugging in Docker

Follow the instructions of the corresponding [pinta-virtual-dev-environment](https://github.com/janrothkegel/pinta-virtual-dev-environment) project

## Getting help / contributing (Pinta.NET)

Use **this repository** only for Pinta.NET support:

- Questions and discussion: [Pinta.NET discussions](https://github.com/TandyColorComputer3/Pinta-dotNet/discussions)
- Bugs / issues: [Pinta.NET issues](https://github.com/TandyColorComputer3/Pinta-dotNet/issues)

The [legacy user guide](https://pinta-project.com/user-guide) still describes core features inherited from upstream Pinta; behavior in Pinta.NET may differ.

- To contribute translations upstream (original **Pinta** project): [Weblate — Pinta](https://hosted.weblate.org/engage/pinta/)
- IRC: `#pinta` on irc.gnome.org historically targets **upstream** Pinta developers.
- For changes in **this fork**, see [CHANGELOG.md](CHANGELOG.md) in this repo and `patch-guidelines.md`.

## Code signing policy
- Free code signing on Windows provided by [SignPath.io](https://about.signpath.io/), certificate by [SignPath Foundation](https://signpath.org/).
- Committers and approvers: [Pinta Maintainers](https://github.com/orgs/PintaProject/people)
- Privacy policy: this program will not transfer any information to other networked systems unless specifically requested by the user or the person installing or operating it.
