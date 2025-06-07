# Dr. Mario 64 Sticky Garbage Mod

This mod changes how garbage works in multiplayer gamemodes. In the original game, players can attack opponents by sending them garbage (single pieces falling in random columns onto the gamemap). Garbage is sent when a player clears more than one line at once (e.g. 2-line combos or more; combos must be cleared with a single capsule).

In this version, AI players continue to receive normal garbage, but human players receive garbage attached to their upcoming capsule (which they can rotate and move around; the garbage will disconnect and fall from capsule once it has landed on the map).

### Known Issues

- Ghost capsule preview doesn't display sticky garbage additions

### Based On

This project builds on the [matching decomp of Dr. Mario 64](https://github.com/AngheloAlf/drmario64) by AngheloAlf. Please refer to their repository for additional information.

### Compatibility Note

Any modifications to the ROM will make it incompatible with certain emulator video plugins; this includes GLideN64 and Project64's default plugin. More accurate plugins like ParaLLEI-RDP seem to work fine (mods also seem to work well with flash cartridges running on the original console).

## Quick Setup

### System Dependencies
Install the following packages (Ubuntu / WSL2 recommended):

```
sudo apt update
sudo apt install make git build-essential clang binutils-mips-linux-gnu gcc-mips-linux-gnu python3 python3-pip python3-venv
```

### Python Environment
```
python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -U -r requirements.txt
```

### Rust and Extra Tools
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
cargo install pigment64 --version ">=0.3.0,<1.*"
```

## Build (Condensed)
Copy your big-endian Dr Mario 64 ROM (renamed as `baserom.us.z64`) into the repository's `./config/us/` directory. Then run:

```
make setup
make lib
make extract
make
```

If successful, the final ROM will be located at:
```
./build/us/drmario64.us.z64
```
