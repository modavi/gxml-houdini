# GXML-Houdini

Houdini integration for the GXML geometric layout library. Provides rendering capabilities and Houdini Digital Assets (HDAs) for working with GXML layouts.

## Features

- **Houdini rendering context** - Render GXML layouts directly in Houdini
- **Custom HDAs** - Pre-built tools for layout manipulation
- **Geometry generation** - Create Houdini geometry from GXML panel layouts
- **Interactive tools** - Viewer states and handles for editing layouts

## Requirements

- SideFX Houdini 19.5+ (tested with Houdini 20.5)
- Python 3.9+ (matching Houdini's Python version)
- GXML library (automatically installed)

## Installation

### Using pip (recommended)

```bash
# In Houdini's Python environment
pip install gxml-houdini
```

### Manual installation

1. Clone this repository
2. Add to Houdini's Python path in `houdini.env`:

```bash
PYTHONPATH = "C:/path/to/gxml-houdini/src;$PYTHONPATH"
```

## Quick Start

### In Houdini Python Shell

```python
from gxml import GXMLParser
from gxml_houdini.render_context import HoudiniRenderContext

# Parse layout
parser = GXMLParser()
root = parser.parse_file("layout.xml")

# Create Houdini geometry
ctx = HoudiniRenderContext(hou.node("/obj/geo1"))
ctx.render_layout(root)
```

### Using HDAs

1. Import the GXML Layout HDA from the toolbar
2. Point to your XML layout file
3. Adjust parameters to control rendering

## Package Structure

```
gxml-houdini/
├── src/gxml_houdini/         # Python integration code
│   ├── render_context.py      # Houdini rendering
│   └── utils.py                # Helper functions
├── otls/                       # Houdini Digital Assets
│   └── *.hda                   # Layout manipulation tools
├── toolbar/                    # Shelf tools
└── viewer_states/              # Custom viewer states
```

## Development

```bash
# Clone repository
git clone https://github.com/yourusername/gxml-houdini.git
cd gxml-houdini

# Install in development mode
pip install -e .

# Set up Houdini environment
# Add to houdini.env:
# HOUDINI_PATH = "/path/to/gxml-houdini;&"
```

## Houdini Environment Setup

Add to your `houdini.env` file:

```bash
# GXML-Houdini integration
HOUDINI_PATH = "C:/path/to/gxml-houdini;&"
PYTHONPATH = "C:/path/to/gxml-houdini/src;$PYTHONPATH"
```

## License

MIT License - see LICENSE file for details

## Links

- [GXML Core Library](https://github.com/yourusername/gxml)
- [Documentation](https://github.com/yourusername/gxml-houdini/docs)
- [Issues](https://github.com/yourusername/gxml-houdini/issues)
