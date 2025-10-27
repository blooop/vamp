# VAMP Pixi Setup

This repository has been configured with **Pixi** to provide an easy way to manage dependencies and run VAMP examples with visualization enabled.

## Quick Start

1. **Get Help & Overview**
   ```bash
   pixi run help      # Setup instructions
   pixi run summary   # Overview of what's available
   ```

2. **Build VAMP**
   ```bash
   pixi run build     # Automated build
   # OR if build fails:
   pixi run build-manual  # Manual build instructions
   ```

3. **Test Installation**
   ```bash
   pixi run test-vamp
   ```

4. **Run Examples**
   ```bash
   pixi run list-examples  # See all available examples
   pixi run run-sphere-cage  # Run first example
   ```

## Available Example Tasks

### Core Examples (with visualization)
- `pixi run run-sphere-cage` - Panda robot planning through sphere obstacles
- `pixi run run-attachments` - Planning with objects attached to end-effector  
- `pixi run run-flying-sphere` - Flying sphere planning over heightfield
- `pixi run run-random-dance` - Random valid configuration sampling

### Robot-Specific MBM Visualizations
- `pixi run visualize-panda` - Visualize Panda robot MBM problems
- `pixi run visualize-ur5` - Visualize UR5 robot MBM problems
- `pixi run visualize-fetch` - Visualize Fetch robot MBM problems
- `pixi run visualize-baxter` - Visualize Baxter robot MBM problems

### Benchmarks (no visualization)
- `pixi run benchmark-sphere-cage`
- `pixi run benchmark-flying-sphere`

### Variations
- `pixi run sphere-cage-small/large` - Small/large sphere radius
- `pixi run attachments-small/large` - Different attachment sizes
- `pixi run flying-sphere-small/large` - Different sphere sizes and spaces

### Build & Development
- `pixi run build` - Build VAMP
- `pixi run build-debug` - Debug build
- `pixi run check-env` - Check environment setup
- `pixi run build-examples` - Build C++ examples

## Environment Details

The pixi environment includes:
- **Python**: 3.10-3.12 (compatible with OMPL)
- **Build tools**: clang, cmake, ninja
- **Core deps**: numpy, pandas, pybullet, fire, tabulate
- **Visualization**: PyBullet with rendering enabled
- **Platform support**: Linux, macOS, Windows

## Troubleshooting

- **Build issues**: Try `pixi run check-env` and `pixi run build-manual`
- **Missing dependencies**: Check `pixi.toml` for platform-specific deps
- **Visualization not working**: Ensure PyBullet GUI is enabled in your environment

## All Tasks

Run `pixi task list` to see all 30+ available tasks.