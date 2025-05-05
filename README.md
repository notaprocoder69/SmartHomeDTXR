# SmartHome - Interactive 3D Visualization

## Overview
This is a Three.js web application that provides an interactive 3D visualization of a smart home system, allowing users to explore and control virtual home automation directly in their web browsers.

## Features
- Interactive 3D home environment with realistic lighting and shadows
- Control smart home devices (lights, thermostats, security cameras, etc.)
- Cross-platform compatibility (desktop and mobile devices)
- Responsive design that adapts to different screen sizes
- Loading progress indicator
- Fullscreen support
- Automatic handling of different device pixel ratios
- Memory management with scene unloading functionality

## Requirements
- A modern web browser with WebGL support
- JavaScript enabled
- Internet connection to load the application

## File Structure
- `index.html` - Main entry point for the application
- `TemplateData/` - Contains styling and UI resources
  - `style.css` - CSS styling for the WebGL container
  - Various image assets (logo, progress bar, etc.)
- `Build/` - Contains the compiled Three.js application files
  - `smarthome.loader.js` - WebGL loader script
  - `smarthome.data` - Application data and assets
  - `smarthome.framework.js` - Framework JavaScript
  - `smarthome.wasm` - WebAssembly binary for performance-critical operations
- `StreamingAssets/` - Contains runtime 3D models and textures
- `.gitattributes` - Git configuration for handling large WebAssembly files

## Setup Instructions
1. Host all files on a web server (local or remote)
2. Ensure all files maintain their relative paths
3. Access the application by opening `index.html` in a web browser

## Usage
- **Desktop**: The application will open in a 960x600 pixel window with options to go fullscreen
- **Mobile**: The application will automatically fill the entire screen
- Navigate the 3D environment using mouse or touch controls:
  - Click/tap to interact with smart devices
  - Drag to rotate the camera
  - Scroll/pinch to zoom in/out
  - Right-click and drag (or two-finger drag) to pan
- Access the control panel by clicking the menu button in the top-right corner
- Use the "Unload" button to completely remove the application from memory when finished

## Development Notes
- Built with Three.js for 3D rendering and WebGL support
- Implements custom shaders for realistic lighting effects
- Includes WebSocket integration for potential connection to real smart home systems
- Product name is set to "SmartHome" (version 0.1)
- Large WebAssembly (.wasm) files are handled with Git LFS as specified in .gitattributes

## Browser Compatibility
- Compatible with modern desktop browsers (Chrome, Firefox, Edge, Safari)
- Compatible with mobile browsers on iOS and Android devices
- Some features may not be available on older browsers that don't fully support WebGL

## Performance Notes
- Mobile devices use optimized rendering settings for better performance
- Level-of-detail (LOD) system automatically adjusts model complexity based on device capabilities
- The application dynamically manages render quality to maintain smooth framerates
- For improved performance on lower-end devices, consider enabling the devicePixelRatio option in the config
- Scene complexity automatically adjusts based on available system resources

## Troubleshooting
- If you see error messages in a red banner, check browser console for more details
- Warning messages appear in yellow and will automatically disappear after 5 seconds
- Make sure your browser has WebGL enabled and is up to date
- If experiencing performance issues:
  - Try reducing the quality settings in the application menu
  - Close other resource-intensive browser tabs
  - Update your graphics drivers
- If smart device controls are not responding, check the connection settings in the application menu

## Smart Home Integration
- The application can be configured to connect to compatible smart home systems
- Edit the `config.js` file to set up API endpoints for your smart home hub
- Supported systems include:
  - Home Assistant
  - SmartThings
  - Philips Hue
  - Custom REST API endpoints
- Refer to the API documentation for details on establishing secure connections