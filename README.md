# Lagrange

Lagrange is a desktop GUI client for browsing Geminispace. It offers modern conveniences familiar from web browsers, such as smooth scrolling, inline image viewing, multiple tabs, visual themes, Unicode fonts, bookmarks, history, and page outlines.

Like Gemini, Lagrange has been designed with minimalism in mind. It depends on a small number of essential libraries. It is written in C and uses [SDL](https://libsdl.org/) for hardware-accelerated graphics. [OpenSSL](https://openssl.org/) is used for secure communications.

![Lagrange window open on URL "about:lagrange"](lagrange_about.png)

## Features

* Beautiful typography using Unicode fonts
* Autogenerated page style and Unicode icon for each Gemini domain
* Smart suggestions when typing the URL — search bookmarks, history, identities
* Sidebar for page outline, managing bookmarks and identities, and viewing history
* Multiple tabs
* Identity management — create and use TLS client certificates
* And more! Open `about:help` in the app, or see [help.gmi](https://git.skyjake.fi/skyjake/lagrange/raw/branch/release/res/about/help.gmi)

## Downloads

Prebuilt binaries for Windows and macOS can be found in [Releases][rel].

## How to compile

This is how to build Lagrange in a Unix-like environment. The required tools are a C11 compiler (e.g., Clang or GCC), CMake and `pkg-config`.

1. Download and extract a source tarball from [Releases][rel]. (If you just clone this Git repository, [the_Foundation][tf] is expected to be already available on the system.)
2. Check that you have the dependencies installed: SDL2, OpenSSL, libpcre, zlib, libunistring. For example, on macOS this would do the trick (using Homebrew): ```brew install sdl2 openssl@1.1 pcre libunistring``` Or on Ubuntu: ```sudo apt install libsdl2-dev libssl-dev libpcre3-dev zlib1g-dev libunistring-dev```
3. Create a build directory.
4. In your empty build directory, run CMake: ```cmake {path_of_lagrange_sources}```
5. Built it: ```cmake --build .```
6. Now you can run `lagrange`, `lagrange.exe`, or `Lagrange.app`.

### Installing to a directory

To install to "/dest/path":

1. `cmake {path_of_lagrange_sources} -DCMAKE_INSTALL_PREFIX=/dest/path`
2. `cmake --build . --target install`

This will also install an XDG .desktop file for launching the app.

[rel]: https://git.skyjake.fi/skyjake/lagrange/releases
[tf]:  https://git.skyjake.fi/skyjake/the_Foundation
