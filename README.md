# hub75-pio-rs

A fork of [Krzysztof Jagiełło's excellent Rust HUB75
driver](https://github.com/kjagiello/hub75-pio-rs) for
[RP2040](https://www.raspberrypi.com/products/rp2040/) which adds
support for 64x64 HUB75E panels which have an additional address pin.

## Features

- Supports LED matrices up to 64x64 pixels with 1:16 scanline
- High refresh rate (approx. 2100 Hz with 24 bit color depth on a 64x32
  display)
- Does not utilize CPU for clocking out data to the display – all the work is
  done by the PIOs and the DMA controller
- Uses binary color modulation
- Double buffered
- Implements [embedded-graphics](https://github.com/embedded-graphics/embedded-graphics) traits

## Requirements

The current implementation assumes that the following groups of data outputs
are assigned to consecutive pins on the RP2040:

- R1, G1, B1, R2, G2, B2
- ADDRA, ADDRB, ADDRC, ADDRD, ADDRE
