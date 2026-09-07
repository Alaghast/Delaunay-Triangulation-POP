# Delaunay POP

A POP plugin for TouchDesigner that generates **2D Delaunay triangulation** from a point input.

![Delaunay Triangulation](assets/A-Delaunay.png)
![Delaunay Wireframed](assets/B-Delaunay.png)
![Network Example](assets/C-NetworkExample.png)

## What It Does

- Reads points from a connected POP (`P` and other point attributes) or from a **CHOP Reference**
  - CHOP Reference uses Array layout (one sample per point)
  - Named `P` channels are used when present; otherwise the first two or three channels become X, Y, and Z (missing Z is 0)
- Projects points onto the `XY`, `YZ`, or `ZX` plane; the unused axis is set to 0 in output `P`
- Builds a 2D Delaunay triangulation with robust integer predicates
- **Output Mode:** `Triangles` (filled faces), `Edges` (a closed outline per triangle), or `None` (the input points with no mesh; with Circumcircle On, each point is a triangle circumcenter)
- Supports both `Sync` and `Async` modes through the `Async` toggle
  - `Async` is recommended for animated or continuously changing inputs (non-blocking, about one frame of delay)
  - For static inputs, `Sync` is recommended for immediate, deterministic results
- Optional attributes (all default Off): `PrimCenter`, `PrimArea`, `Color`, `Circumcenter` + `Circumradius`, `NeighborCount` — see [Attributes](#attributes)
- **Delete Input Attributes:** On keeps only positions from the input (plus any attributes you enable). Off (default) also keeps the other input point attributes
- Passes point attributes through to the output like a standard POP operator

## Attributes

All toggles default Off. When On, the value is written on the output.

**Primitive Center** (`PrimCenter`) — center of each triangle.

https://github.com/user-attachments/assets/94099707-808a-43f8-873c-9897bb27d29c

**Primitive Area** (`PrimArea`) — area of each triangle.

https://github.com/user-attachments/assets/7fa85e56-4e81-4095-b020-f7f986c802c4

**Primitive Color** (`Color`) — flat color per triangle, taken from point Color.

![Primitive Color](assets/primitivecolor.jpg)

**Circumcircle** (`Circumcenter`, `Circumradius`) — center and radius of the circle through each triangle's three vertices.

https://github.com/user-attachments/assets/9f391a5e-89e2-4fac-93bf-04222e5935fb

**Neighbor Count** (`NeighborCount`) — how many triangles meet at each point.

https://github.com/user-attachments/assets/43eb4804-d970-4b35-8554-9ef9f3642aef

## Libraries Used

- TouchDesigner POP C++ API
- [delaunay32](https://github.com/morishuz/delaunay32)

## Requirements

- TouchDesigner 2025.33070 or later
- macOS (Apple Silicon) or Windows

The example `.toe` included in the release zip requires the same TouchDesigner build.

## How to Download this Repo

Download the latest release for your operating system (do not clone this repository to install the plugin):

- [Latest Release](https://github.com/Alaghast/Delaunay-Triangulation-POP/releases/latest)
- macOS: `Delaunay-1.9.4-MAC.zip`
- Windows: `Delaunay-1.9.4-WIN.zip`

Unzip the archive fully into a folder (for example `Delaunay-1.9.4/`) **before** running Uninstall or the installer. Do not launch `.app`, `.pkg`, `.cmd`, or `.exe` files from inside the still-zipped archive.

## Installation

1. Unzip the release as described above.
2. **Uninstall first** to remove older copies (including previous drop-in plugins):
   - macOS: open `Delaunay Uninstall.app`
   - Windows: run `Delaunay_Uninstall.cmd`
3. Run the installer like a normal application:
   - macOS: open `Delaunay-TouchDesigner-1.9.4.pkg`
   - Windows: run `Delaunay-TouchDesigner-1.9.4-win64.exe`
4. Fully quit and restart TouchDesigner.
5. When TouchDesigner shows the plugin scan dialog, click **Allow**. Clicking **Deny** will prompt again on every restart until the plugin is accepted.
6. Add a **Delaunay** POP from the **Custom** family in the OP Create Dialog.

The unzipped folder also contains `MANUAL.md` and `Delaunay_Example_2025.33070.toe`.

### Plugin Locations

The installer places the plugin in the standard TouchDesigner Plugins directory, inside **AlaghastPOP**:

#### macOS

`/Users/<username>/Library/Application Support/Derivative/TouchDesigner099/Plugins/AlaghastPOP/`

#### Windows

`C:/Users/<username>/Documents/Derivative/Plugins/AlaghastPOP/`

## Distribution

- Installer: `.pkg` (macOS), `.exe` (Windows)
- Operator name: `Delaunay`
- Version: `1.9.4`
- License: `MIT`
- Author: [Edwin Lucchesi](https://www.edwinlucchesi.com/)

## Share Your Results

If you use this plugin, feel free to tag me.
I'll be happy to see your results!

Instagram: [@Alaghast](https://www.instagram.com/alaghast/)

2025-26
