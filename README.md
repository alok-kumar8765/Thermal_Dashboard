# Kelvin

A lightweight, visualization-first hardware sensor monitor for Windows 10/11 built with C# 12, .NET 8, and WPF.

## Features

- **Glanceable Thermal Dashboard**: Custom-drawn 270° arc gauges, 120-second dual-series sparklines, per-core load/clock heat-bar grid, and radial fan bars.
- **Metrics Monitored**:
  - **CPU**: Package temperature, total & per-core usage, average & per-core clock, package power (W), core voltage (V), and current (A).
  - **GPU**: Temperature, core usage, core clock, power, voltage, current, and VRAM usage.
  - **RAM**: Used / total capacity, usage %, configured clock, voltage, and temperature.
  - **Fans**: Live RPM per detected fan header.
- **Always-on-Top Overlay**: Borderless, draggable HUD with Mini, Standard, and Custom modes, adjustable opacity/scale, horizontal/vertical orientation, and click-through recovery from the system tray.
- **Themes**: Windows 11 Mica/Acrylic dark and light themes with customizable accent colors.

## Building from Source

Requires the [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0) on Windows.

```powershell
dotnet publish -c Release -r win-x64 -o .\publish
```

This produces a standalone, self-contained single-file executable at `.\publish\Kelvin.exe`.

## Command-Line Flags

- `Kelvin.exe --demo` — Runs with simulated hardware telemetry (no administrator rights or physical sensors required).
- `Kelvin.exe --dump-sensors` — Writes a full diagnostic sensor report to `sensors-dump.txt` beside the executable and exits.
