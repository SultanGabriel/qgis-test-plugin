# BiometrixTest QGIS Plugin

**BiometrixTest** is a QGIS plugin developed as part of the Biometrix land classification workflow. It demonstrates basic interaction with QGIS layers, geometry creation, and plugin UI integration.

---

## Features

- Lists all vector layers and displays their features (geometry + attributes).
- Exports selected layers as GeoJSON.
- Draws an example layer with polygon geometries.

---

## Usage

1. Copy the plugin folder `biometrixtest/` into your QGIS plugin directory:  
    `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/` (Windows: `C:\Users\USER\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins`)
2. Open QGIS.
3. Load some layers (raster or vector).
4. Enable the plugin via Plugin Manager.
5. Click the plugin icon in the toolbar or use the menu entry.
6. View the loaded layer info in the dialog.
7. Click "Draw Example Layer" to show a polygon message.
8. Export vector layers as GeoJSON via button.

---


## File Structure
```
biometrixtest/
├── BiometrixTest.py               # Main plugin logic
├── BiometrixTest_dialog.py       # Dialog class with UI logic
├── BiometrixTest_dialog_base.ui  # Qt Designer UI file
├── icon.png                      # Plugin icon
├── metadata.txt                  # Plugin metadata
├── plugin_upload.py              # For plugin repo deployment
├── README.md / README.txt        # QGis Generated Docs
├── resources.qrc / resources.py  # Icons and assets
├── __init__.py                   # Required for QGIS plugin loader
├── help/                         # 
├── scripts/                      # Utilities
└── test/                         # Optional test framework
```

---

## Development Setup

### Dependencies
- QGIS 3.x
- PyQt5 (included with QGIS)
- Plugin Builder / pb_tool (optional)

### Manual Resource Compilation
If `pyrcc5` is not in your path:
```bash
sudo apt install qt5-qmake qttools5-dev-tools
pyrcc5 resources.qrc -o resources.py
```

### pb_tool Support
This plugin includes a `pb_tool.cfg` file that allows you to automate compilation and installation tasks:

```bash
# Install pb_tool
pip install pb_tool

# Compile resources and UI
pb_tool compile

# Deploy plugin to QGIS plugin directory
pb_tool deploy

# Clean up build artifacts
pb_tool clean
```

See [pb_tool documentation](https://g-sherman.github.io/plugin_build_tool/) for details.


