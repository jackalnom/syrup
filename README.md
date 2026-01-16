# Syrup 🍯

A browser-based real-time physics simulation where uploaded PNG images become height maps, and viscous fluids flow over the terrain in beautiful, layered patterns.

## Features

- 🏔️ **Height Map Terrain**: Upload any PNG image - its brightness values become elevation
- 💧 **Viscous Fluid Physics**: High-viscosity, non-mixing colored liquids that flow realistically
- 🎨 **Image-Based Colors**: The colors from your uploaded image automatically become flowing liquid
- 🎛️ **Real-Time Controls**: Adjust all parameters with interactive sliders while the simulation runs
- 🖱️ **Interactive**: Click anywhere on the canvas to add more fluid (fluid color matches the uploaded image's pixel color)

## Usage

1. Open `index.html` in a modern web browser
2. Upload a PNG image - it will automatically become flowing liquid over the terrain based on brightness
3. Watch as the image colors flow down like syrup based on the height map
4. Click on the canvas to add more fluid particles (optional)
5. Use the sliders to adjust:
   - **Height Scale**: Controls how dramatic the terrain elevation is
   - **Smoothness**: Smooths out the terrain (0 = no smoothing)
   - **Viscosity**: How thick/slow the fluid flows
   - **Gravity**: Strength of gravitational force
   - **Flow Rate**: How fast fluid moves down slopes
   - **Fluid Amount**: How many particles spawn per click
   - **Terrain Brightness**: Visual brightness of the terrain

## How It Works

The simulation uses a particle-based approach where:
- Each pixel's brightness in the uploaded PNG determines terrain elevation
- When an image is uploaded, its colors are sampled and converted to fluid particles
- Fluid particles start at their image positions and flow downhill based on terrain slopes
- Particles calculate local gradients and flow downhill
- High viscosity is simulated through velocity damping
- Particles can stack on top of each other to create layers
- Colors remain separate (non-mixing) by maintaining particle identity

## Technical Details

- Pure HTML5 Canvas and JavaScript
- No external dependencies
- Real-time physics simulation at 60 FPS
- Gradient-based slope calculation for fluid flow
- Spatial particle interaction for stacking behavior