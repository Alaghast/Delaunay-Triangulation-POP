# Delaunay POP v.1.0

POP plugin for TouchDesigner that generates 2D Delaunay triangulation from a point input.

## What It Does
	•	Reads points from the P attribute of the input POP.
	•	Projects points onto the XY, YZ, or ZX plane.
	•	Generates Delaunay triangles with robust output, even for degenerate inputs.
	•	Supports Sync/Async modes (via the Async toggle)
	    Async mode is recommended for animated or continuously changing inputs, as it allows non-blocking computation.
        For static or non-changing inputs, Sync mode is preferred to ensure immediate and deterministic results
	•	Passes point attributes to the output like a standard POP operator

## Libraries Used
	•	TouchDesigner POP C++ API
	•	Delaunator C++ (header-only)

## Requirements
	•	TouchDesigner 2025+

## Installation
	•	You can copy the plugin into your project and load it through the CPlusPlus POP operator, as shown in the provided examples in “Delaunay Example/MAC” or “Delaunay Example/WINDOWS”.
	•	Alternatively, you can install it directly in TouchDesigner like other any Custom OPs so it can be accessed from the Custom panel in the OP Create Dialog.

Custom OPs are used by simply placing the plugins in the correct location on disk. They will be detected automatically when TouchDesigner starts.
On Windows, a plugin is a .dll file (possibly accompanied by additional files). On macOS, a plugin is a .plugin folder.

Plugin Locations in:
# Windows
Documents/Derivative/Plugins
Usually:
C:/Users/<username>/Documents/Derivative/Plugins

#macOS:
/Users/<username>/Library/Application Support/Derivative/TouchDesigner099/Plugins

Distribution
	•	Plugin format: .plugin (macOS bundle), .dll (Windows)
	•	Operator name: Delaunay
	•	Version: 1.0
	•	License: MIT
	•	Author: Edwin Lucchesi (https://www.edwinlucchesi.com/)

If you use this plugin, please tag me!
I'll be happy to see your results!
IG: @Alaghast

2025-26
