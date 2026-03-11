# Delaunay POP v1.0

A POP plugin for TouchDesigner that generates **2D Delaunay triangulation** from a point input.

![Delaunay Triangulation](A-Delaunay.png)
![Delaunay Wireframed](B-Delaunay.png)
![Network Example](C-NetworkExample.png)

## What It Does

- Reads points from the input POP's `P` attribute
- Projects points onto the `XY`, `YZ`, or `ZX` plane
- Generates Delaunay triangles reliably, even with degenerate inputs
- Supports both `Sync` and `Async` modes through the `Async` toggle
  - `Async` mode is recommended for animated or continuously changing inputs because it allows non-blocking computation
  - For static inputs, `Sync` mode is recommended to ensure immediate and deterministic results
- Passes point attributes through to the output like a standard POP operator

## Libraries Used

- TouchDesigner POP C++ API
- Delaunator C++ (header-only)

## Requirements
- Touchdesigner 2025+ (If you just use the plugin elsewhere)
- TouchDesigner 2025.32440+ (If you open the examples, due the Trace POP)

## How Download This Repo
On Mac, if you download the .plugin file as a zip or zip it yourself, this removes the momentary signature.
I suggest you simply clone it directly from the GitHub repository using the git clone command in your system terminal in a folder of your choice to avoid this problem.

The "Git Clone" procedure for those who don't know how to do it:

- Click on Code on the repository and copy the url

![Copy_the_Url](https://github.com/user-attachments/assets/8b09796e-8b3f-4df2-9f74-748ae9817c2b)

- Open your terminal in a folder you wish and digit 'git clone theUrlYouCopiedBefore'

![git_clone](https://github.com/user-attachments/assets/f0a322c9-e29e-41c9-82d8-e4173e39b9ef)

## Installation

- Copy the plugin into your project and load it through the `CPlusPlus POP` operator, as shown in the examples provided in `Delaunay Example/MAC` or `Delaunay Example/WINDOWS`
- Alternatively, install it directly in TouchDesigner like any other Custom OP so that it becomes available from the **Custom** panel in the **OP Create Dialog**

Custom OPs can be installed by placing the plugin in the correct location on disk. TouchDesigner will detect it automatically at startup.

- On Windows, a plugin is a `.dll` file, possibly accompanied by additional files
- On macOS, a plugin is a `.plugin` folder

### Plugin Locations

#### Windows

`Documents/Derivative/Plugins`

Typical path:

`C:/Users/<username>/Documents/Derivative/Plugins`

#### macOS

`/Users/<username>/Library/Application Support/Derivative/TouchDesigner099/Plugins`

## Distribution

- Plugin format: `.plugin` (macOS bundle), `.dll` (Windows)
- Operator name: `Delaunay`
- Version: `1.0`
- License: `MIT`
- Author: [Edwin Lucchesi](https://www.edwinlucchesi.com/)

## Possible Issues
The Delaunator library can become unstable with nearly collinear, near-duplicate, extremely thin, or otherwise degenerate point sets,
so users should avoid feeding it points that collapse to an almost 1D or numerically ambiguous distribution.
If that happens, you'll see stalling or a freeze in the plugin or TD itself.
A trick that i introduced in the examples toe is using a little Random POP Noise on P attribute that seems help to avoid that freezing/stalling behaviour

## Share Your Results

If you use this plugin, feel free to tag me.
I'll be happy to see your results!

Instagram: [@Alaghast](https://www.instagram.com/alaghast/)

Want support me and this project? [Click Here!](https://ko-fi.com/alaghast)

2025-26
