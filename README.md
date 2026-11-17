# Modular Hardware Rust

# RetroCore — Game Boy Emulator in Rust

RetroCore is a modular emulator for the original Nintendo Game Boy (DMG), developed using Rust. It recreates essential hardware components, including the CPU, memory system, graphics, audio, and input controls, to execute compatible Game Boy ROMs.

## Features

- **CPU:** Sharp LR35902 instruction execution, CB-prefixed opcodes, interrupts, and instruction timing.
- **Memory Bus:** Centralized memory mapping and communication between hardware components.
- **Graphics (PPU):** Scanline-based rendering of backgrounds, windows, and sprites at 160 × 144 resolution.
- **Audio (APU):** Four-channel sound emulation with PCM audio output.
- **Cartridge Support:** ROM loading with ROM-only, MBC1, and MBC3 memory banking.
- **Joypad:** Keyboard-based controls with interrupt handling.
- **Timers:** Emulation of DIV, TIMA, TMA, and TAC registers.

## Tech Stack

- **Language:** Rust
- **Build Tool:** Cargo
- **Concepts:** Systems Programming, CPU Emulation, Memory Management, Computer Architecture

## Installation and Usage

**Requirements:** Rust, Cargo, and a compatible `.gb` ROM file.

Build the project:

```bash
cargo build --release
```

Run the emulator:

```bash
cargo run --release -- <path-to-rom.gb>
```

## Keyboard Controls

| Game Boy Button | Keyboard |
|---|---|
| Directional Pad | Arrow Keys |
| A / B | Z / X |
| Start | Enter |
| Select | Right Shift |
| Quit | Escape |

## Project Structure

```text
src/
├── main.rs        # Application initialization
├── cpu.rs         # CPU instruction execution
├── bus.rs         # Memory mapping and timers
├── ppu.rs         # Graphics rendering
├── sound.rs       # Audio processing
├── cartridge.rs   # ROM loading and banking
└── joypad.rs      # Controller input
```

## Testing

Supports Blargg-style diagnostic ROMs using serial registers (`0xFF01` and `0xFF02`). Test messages are displayed in the terminal to assist with debugging and hardware validation.

## Limitations

The emulator focuses on compatibility with standard homebrew ROMs rather than complete cycle accuracy. Certain hardware-specific behaviors, including pixel-level PPU timing, DMA transfer delays, timer glitches, and advanced audio quirks, are simplified.

## Purpose

RetroCore demonstrates practical applications of **Rust, low-level systems programming, instruction execution, memory-mapped I/O, and modular hardware simulation**.
