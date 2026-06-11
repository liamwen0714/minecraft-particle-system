# minecraft-particle-system

Custom Minecraft particle effects built with Beet, Bolt, and Python. This project uses parametric equations, animated timers, and Minecraft datapack functions to create visual effects such as fireworks, spirals, blooms, waves, and geometric particle shapes.

## Showcase

### Lotus Bloom
![Lotus Bloom](Minecraft%20gifs/lotus_bloom.gif)

### Aurora Curtain
![Aurora Curtain](Minecraft%20gifs/aurora_curtain.gif)

### Firework Burst
![Firework Burst](Minecraft%20gifs/firework_burst.gif)

### Mega Firework
![Mega Firework](Minecraft%20gifs/mega_firework.gif)

### Galaxy Spiral
![Galaxy Spiral](Minecraft%20gifs/galaxy_spiral.gif)

### Rainbow Ring
![Rainbow Ring](Minecraft%20gifs/rainbow_ring.gif)

### Flower
![Flower](Minecraft%20gifs/flower.gif)

## Features

- Custom Minecraft particle animations
- Parametric equation-based visual effects
- Reusable datapack functions
- Animated color-changing effects
- Large-scale command block particle displays
- Beet and Bolt workflow automation
- Effects designed for Minecraft Java Edition datapacks

## Example Effects

All included functions:

```mcfunction
function effects:circle1
function effects:circle2
function effects:sphere1
function effects:sphere2
function effects:sphere3
function effects:sphere4
function effects:sphere5
function effects:sphere6
function effects:sphere7
function effects:torus1
function effects:torus2
function effects:star
function effects:cylinder
function effects:heart
function effects:cube
function effects:cone
function effects:helix
function effects:flower
function effects:rainbow_ring
function effects:double_helix
function effects:firework_burst
function effects:mega_firework
function effects:galaxy_spiral
function effects:aurora_curtain
function effects:lotus_bloom
function effects:butterfly
function effects:wave_grid
```

## Technologies

- Minecraft Java Edition Datapack
- Beet
- Bolt
- Python

## Project Structure

```text
minecraft-particle-system/
├── beet.json
├── Minecraft gifs/
│   ├── lotus_bloom.gif
│   ├── aurora_curtain.gif
│   ├── firework_burst.gif
│   ├── mega_firework.gif
│   ├── galaxy_spiral.gif
│   ├── rainbow_ring.gif
│   └── flower.gif
└── src/
    └── data/
        └── graphics/
            └── modules/
                └── main.bolt
```

The main source file is:

```text
src/data/graphics/modules/main.bolt
```

## Requirements

Before using this project, make sure you have:

- Minecraft Java Edition
- Python
- Beet
- Bolt

You can check whether Beet is installed by running:

```powershell
beet --version
```

## Build Instructions

Open a terminal in the project folder:

```powershell
cd path\to\minecraft-particle-system
```

Build the datapack:

```powershell
beet build
```

This generates the Minecraft datapack files.

## Link To A Minecraft World

To link the generated datapack directly to a Minecraft world, run:

```powershell
beet link "Your World Name"
beet build
```

Replace `"Your World Name"` with the name of your Minecraft world folder.

After building, open Minecraft and run:

```mcfunction
/reload
```

## Running Effects In Minecraft

To run an effect from chat, include the slash:

```mcfunction
/function effects:lotus_bloom
```

To run an effect inside a command block, leave off the slash:

```mcfunction
function effects:lotus_bloom
```

## Recommended Command Block Settings

For animated effects, use these command block settings:

```text
Repeat
Unconditional
Always Active
```

Good effects to try with a repeating command block:

```mcfunction
function effects:lotus_bloom
function effects:mega_firework
function effects:galaxy_spiral
function effects:aurora_curtain
function effects:rainbow_ring
function effects:flower
```

For one-time burst effects, use these command block settings:

```text
Impulse
Unconditional
Needs Redstone
```

Good one-time effect:

```mcfunction
function effects:firework_burst
```

## Customization

Most effect logic is inside:

```text
src/data/graphics/modules/main.bolt
```

Common values to modify:

- `spawn_height`: changes where effects appear vertically
- `radius`, `spread`, or `bloom`: changes effect size
- `points`, `steps`, or `rays`: changes particle density
- RGB color values: changes particle color
- Timer values: changes animation speed
- Particle names: changes the particle style

Example dust particle color:

```bolt
particle dust{color:[1.0, 0.5, 0.2],scale:1.2} ~x ~y ~z
```

RGB values range from `0.0` to `1.0`.

Color examples:

```text
[1.0, 0.0, 0.0] = red
[0.0, 1.0, 0.0] = green
[0.0, 0.0, 1.0] = blue
[1.0, 1.0, 1.0] = white
[0.2, 0.1, 0.5] = dark purple
[1.0, 0.6, 0.1] = orange/gold
```

For animation speed, lower timer numbers make effects faster and higher timer numbers make effects slower.

Example:

```bolt
execute if score #lotus_tick timer matches 5 run scoreboard players add #lotus_phase timer 1
```

Changing `5` to `3` makes the animation faster. Changing `5` to `10` makes it slower.

## What I Learned

This project helped me understand Minecraft datapack development, mathematical animation logic, particle systems, command block workflows, and how tools like Beet and Bolt can automate Minecraft function generation.
