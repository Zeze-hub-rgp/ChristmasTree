# Christmas Tree

#### A Delphi Firemonkey Cross-Platform App

A silly little program that simply displays a Christmas tree with various decorative bulbs and gingerbread men that, when you click on them, fall to the ground and break.


## What it does

- **Display a Christmas Tree**: Beautiful Christmas tree with star on top, set in someone's house in front of a fireplace
- **Interactive Ornaments**: 30 clickable bulbs and gingerbread men in various colors
- **Physics Simulation**: Bulbs fall with gravity when clicked, rotating and fading as they fall
- **Sound Effects**: Breaking sound when bulbs hit the floor
- **Multi-Platform**: Supports Windows, Mac, Android, and iOS

## Code

- Written in Delphi 13 Florence, initially with Claude Code, polished manually
- Uses the Firemonkey framework but no third-party components

#### Main Classes

- **TMainForm**: Main form displaying the tree and bulbs and runs animation logic
- **TChristmasBulb**: Represents an interactive ornament with states (Normal, Broken, Falling)

#### Animation System

- Timer-based animation loop running at ~60 FPS
- Delta-time calculations for smooth, frame-rate independent animation
- Physics simulation using velocity and gravity constants

## Adding Custom Sound Effects

Included are 5 sample "glass-break" sounds. To add additional ones:

1. Windows: add `.wav` files (e.g., `glass-break-6.wav`) to the `audio\Windows` folder
2. Android: add `.mp3` files (e.g., `glass-break-6.mp3`) to the `audio\Android` folder
3. Mac/iOS: add `.caf` files (e.g., `glass-break-6.caf`) to the `audio\iOS` folder

All files in the form `glass-break-*.<platform-extension>` will be found and loaded; a random one is selected each time a bulb falls.

Remember: When you add custom sound files, you have to add them to the project's deployed files for platforms other than Windows (*Project* > *Deployment*). 

## Adding Custom Ornaments

Included are 4 types of ornaments (blue, red, gold, and gingerbread). From these, 30 ornaments are created and placed over the image of the tree.

To change the number of bulbs created, adjust the value in `CreateBulbs`. To add additional bulb types, add two `.png` files for each bulb type in the form:

- `ornament-<new_type>.png` which depicts an ornament hanging on the tree
- `ornament-<new_type>-broken.png` which depicts the broken ornament laying on the floor.

For example, to add a green ornament, you would add `ornament-green.png` and `ornament-green-broken.png`.

All image files should be placed in the `images\` folder.

Remember: When you add custom image files, you have to add them to the project's deployed files for platforms other than Windows (*Project* > *Deployment*). 

The bulk of this program was written with Claude Code and actually ran on Windows before I touched a line of code. To get it to work on other platforms required significantly more work (mostly configuration, not more code), especially when learning where to store and how to access the various image and sound files on Android and iOS devices. It's the main reason this program exists: to serve as a reminder and tutorial of how to write one Delphi program that accesses external files on multiple platforms.

To understand more about why this app was written (rather than just a silly past-time) and the lessons it taught, read the [Blog](https://corneliusconcepts.tech/simple-christmas-tree-app) and learn about the journey this seemingly simple app took.

## License

Free to use and modify for personal and educational purposes.
