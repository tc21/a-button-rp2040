### Hardware

This creates a keyboard, from a rp2040, where _one single pin_ is shorted to ground upon keypress.

### Setup

You will need the cross compilation toolchain:
```sh
rustup target install thumbv6m-none-eabi
```

stack overflow protection:
```sh
cargo install flip-link
```

and (a) either [Picotool](https://github.com/raspberrypi/pico-sdk-tools/releases) (default) for generating uf2 files, or flashing over USB (without debugging), or (b) [probe-rs](https://probe.rs/docs/getting-started/installation/) for flashing and debugging via debug probe.
### Config
Update the config in source code: `src/main.rs`: Lines 30 to 34. You can set which pin to use, and which keycode to emit.

### Build
By default this package is configured to build a uf2 file. Change the build command in `.cargo/config.toml`

```sh
cargo run <output-file.uf2>
```
