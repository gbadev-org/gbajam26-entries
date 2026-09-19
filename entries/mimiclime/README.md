# mimiclime

mimiclime is a top-down exploration game demo for the Game Boy Advance,\
where you play as a slime who becomes a monster it devours.


## Setup

### Setting up build environment

1. Setup dependencies for Butano with [devkitARM](https://gvaliente.github.io/butano/getting_started.html) or [Wonderful Toolchain](https://gvaliente.github.io/butano/getting_started_wt.html).
   * Butano itself is included as a submodule, so you don't need to manually download it.
1. **Recursively** clone this repo.
1. `pip install -r libs/butano-ldtk/requirements.txt`
1. That's it, you can now run `make -j$(nproc)` to build the project.

### Finding include paths with VSCode C/C++ extension

[See this gist.](https://gist.github.com/copyrat90/eee49d92846ca3585a69d5bea001710d)

* Change the `"cppStandard"` to `"c++26"`.

### Setting up debugger

[See this guide.](https://felixjones.co.uk/mgba_gdb/vscode.html)

### Using stats viewer

Open [`tools/mc_dev_stats.lua`](tools/mc_dev_stats.lua) with `Debug > Script Window` in [MesenCE](https://github.com/nesdev-org/MesenCE).


## Edit

### Editing levels

To edit the levels, open [`levels/mimiclime.ldtk`](levels/mimiclime.ldtk) with [LDtk](https://ldtk.io/) v1.5.3

Just saving the LDtk project is enough, the build process automatically takes care of the importing.

### Editing sprite datas

To edit the sprite datas, build the [`tools/mcedit/`](tools/mcedit/) with CMake and a C++ compiler that supports C++26 reflection.\
(As of writing, [GCC 16](https://gcc.gnu.org/gcc-16/changes.html#cxx) supports [C++26 reflection](https://cppreference.com/cpp/compiler_support/26).)

Open the mimiclime root directory with `File > Open mimiclime directory`, and start editing things with `Window > ...`

Just saving the changes is enough, the build process automatically takes care of the importing.

#### Adding combo entries

If you want to add an entry for combos, add the entry in `defs/*.txt`.\
(e.g. Adding an entry in `defs/projectile_kind.txt` will expand the list of available projectiles).

Note that these are included in C++ sources on the GBA side, so don't do anything weird with it!


## Licenses

### Source code

The source code of this project is licensed under the [zlib License](LICENSE).

### Sprites

* GBA Jam 2026 logo
  * made by GBA Jam 2026 Organizers, licensed under [CC BY-NC](https://creativecommons.org/licenses/by-nc/4.0/).
  * logo text font - [H. H. Samuel by deFharo](https://fontlibrary.org/en/font/h-h-samuel), licensed under [OFL](https://openfontlicense.org/).
* Sprites
  * [`wood_fence.bmp`](graphics/spr/wood_fence.bmp) and [`sign.bmp`](graphics/spr/sign.bmp)
    * made by copyrat90, licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
  * [All other sprites](graphics/spr/)
    * made by fixx, licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

### Others

Check out [`licenses/`](licenses/) for all the licenses, including ones not mentioned here.
