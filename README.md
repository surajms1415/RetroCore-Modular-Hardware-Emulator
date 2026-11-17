# RetroCore — 8-Bit Console Emulator

### About the Project

RetroCore is a Rust-based systems programming project that brings the classic Game Boy hardware environment to modern computers. It recreates the internal operations of an 8-bit gaming console, allowing compatible ROMs to execute through software-based hardware simulation.

Rather than relying on physical console components, RetroCore processes machine instructions, manages memory access, generates graphics and audio, and handles player input through a modular emulation engine.

## Key Capabilities

- **Instruction Processing:** Executes Sharp LR35902 CPU instructions with register operations, interrupts, and timing management.
- **Hardware Simulation:** Connects memory, timers, graphics, audio, and cartridge controllers through a shared system bus.
- **Visual Rendering:** Reconstructs classic Game Boy graphics using scanline-based background, window, and sprite rendering.
- **Sound Generation:** Simulates four hardware audio channels for real-time sound output.
- **ROM Compatibility:** Supports homebrew Game Boy ROMs with ROM-only, MBC1, and MBC3 cartridge configurations.
- **Interactive Controls:** Maps keyboard inputs to the original console's directional and action buttons.

## Getting Started

**Prerequisites:** Rust, Cargo, and a compatible `.gb` ROM.

Build:

```bash
cargo build --release
```

Run:

```bash
cargo run --release -- <path-to-rom.gb>
```

## Controls

| Action | Key |
|---|---|
| Movement | Arrow Keys |
| A / B | Z / X |
| Start / Select | Enter / Right Shift |
| Exit | Escape |

## Testing

RetroCore supports serial-based diagnostic output from compatible Game Boy test ROMs, helping validate CPU execution and hardware behavior.

## Technical Notes

The emulator prioritizes practical ROM compatibility over perfect hardware timing. Some advanced behaviors involving graphics timing, DMA transfers, timers, and audio are simplified.

## Learning Outcomes

This project explores core systems engineering concepts such as CPU architecture, instruction decoding, memory-mapped I/O, interrupt processing, hardware abstraction, and modular software development in Rust.
