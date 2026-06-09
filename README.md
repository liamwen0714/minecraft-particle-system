# minecraft-particle-system

Custom Minecraft particle effects built with Beet, Bolt, and Python. This project uses parametric equations, animated timers, and Minecraft datapack functions to create visual particle effects such as fireworks, spirals, blooms, waves, and other geometric shapes.

## Showcase

GIFs can be added to a `media/` folder and displayed here.

![Lotus Bloom](media/lotus-bloom.gif)
![Mega Firework](media/mega-firework.gif)
![Galaxy Spiral](media/galaxy-spiral.gif)
![Aurora Curtain](media/aurora-curtain.gif)

## Features

- Custom Minecraft particle animations
- Parametric equation-based visual effects
- Reusable datapack functions
- Animated color-changing effects
- Large-scale command block particle displays
- Beet and Bolt workflow automation

## Example Effects

Some included functions:

```mcfunction
function effects:lotus_bloom
function effects:mega_firework
function effects:firework_burst
function effects:galaxy_spiral
function effects:aurora_curtain
function effects:double_helix
function effects:rainbow_ring
function effects:butterfly
function effects:wave_grid
function effects:cube
function effects:cone
function effects:helix
function effects:flower
Technologies
Minecraft Java Edition Datapack
Beet
Bolt
Python
Project Structure
minecraft-particle-system/
├── beet.json
└── src/
    └── data/
        └── graphics/
            └── modules/
                └── main.bolt
Requirements
Before using this project, install or have access to:

Minecraft Java Edition
Python
Beet
Bolt
You can check whether Beet is installed by running:

beet --version
Build Instructions
Open a terminal in the project folder:

cd path\to\minecraft-particle-system
Build the datapack:

beet build
This generates the Minecraft datapack files.

Link To A Minecraft World
To link the generated datapack directly to a Minecraft world, run:

beet link "Your World Name"
beet build
Replace "Your World Name" with the name of your Minecraft world folder.

After building, open Minecraft and run:

/reload
Running Effects In Minecraft
To run an effect from chat, include the slash:

/function effects:lotus_bloom
To run an effect inside a command block, leave off the slash:

function effects:lotus_bloom
Recommended Command Block Settings
For animated effects, use:

Repeat
Unconditional
Always Active
Good effects to try with a repeating command block:

function effects:lotus_bloom
function effects:mega_firework
function effects:galaxy_spiral
function effects:aurora_curtain
For one-time burst effects, use:

Impulse
Unconditional
Needs Redstone
Good one-time effect:

function effects:firework_burst
Customization
Most effect logic is inside:

src/data/graphics/modules/main.bolt
Common values to modify:

spawn_height: changes where effects appear vertically
radius, spread, or bloom: changes effect size
points, steps, or rays: changes particle density
RGB color values: changes particle color
Timer values: changes animation speed
Particle names: changes the particle style
Example dust particle color:

particle dust{color:[1.0, 0.5, 0.2],scale:1.2} ~x ~y ~z
RGB values range from 0.0 to 1.0.

Examples:

[1.0, 0.0, 0.0] = red
[0.0, 1.0, 0.0] = green
[0.0, 0.0, 1.0] = blue
[1.0, 1.0, 1.0] = white
[0.2, 0.1, 0.5] = dark purple
