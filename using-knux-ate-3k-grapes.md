# Documentation for Knuckles Ate 3000 Grapes

**Note: This file is meant to be viewed within GitHub. If your text viewer doesn't support Markdown, some things may not appear as intended.**

To start, add this line inside your mod's main.lemon:
`include ../../../../knux_ate_3k_grapes.lemon`

**IMPORTANT!** While you're developing a mod, you'll most likely have the mod as a uncompressed folder (path goes like `/mods/coolmod01/...`), so you'll need to remove one `../` from the include line. This is because it will be looking at the wrong folder. Remember to add it back when compressing your mod to upload it on any file hosting platform!

Now, with the basic stuff out of the way, let's get into what this single file offers:

## Constants

You can identify each zone with a name instead of numbers.
Examples: `CNZ2`, `LRZ3`, `SSZK`, `BONUS_GUMBALL`

You can also use `ACT1` and `ACT2` instead of 0x00 and 0x01.

<details>
<summary>Full List of Zone constants</summary>

```
ACT1 and ACT2

AIZ, AIZ1 and AIZ2

HCZ, HCZ1 and HCZ2

MGZ, MGZ1 and MGZ2

CNZ, CNZ1 and CNZ2

ICZ, ICZ1 and ICZ2

LBZ, LBZ1 and LBZ2

MHZ, MHZ1 and MHZ2

FBZ, FBZ1 and FBZ2

SOZ, SOZ1 andSOZ2

LRZ (Does not include the boss act), LRZ1, LRZ2 and LRZ3

HPZ and EMERALD_ALTAR (Hidden Palace Zone when entered through a Special Ring)

SSZ, SSZS and SSZK

DEZ (Does not include the boss act), DEZ1, DEZ2 and DEZ3

DDZ and ENDING

ALZ, BPZ, CGZ, DPZ and EMZ

BONUS_GUMBALL, BONUS_SPHERES and BONUS_SLOT
```

</details>

## Variables and defines

`u8 mhz.season` - Variable made to tell what's the current season in MHZ2. It's set to `season.SUMMER` in MHZ1.
- `season.SUMMER`
- `season.FALL` or `season.AUTUMN`
- `season.WINTER`

`bool fbz.isOutdoors` - Define made to tell if you're outside the ship in Flying Battery Zone.
- Important note: This does not cover the boss area in FBZ2. Use `camera.position.x.u16 + getScreenWidth() > 0x2c80` to check for that specific area.

## Functions

Looks empty here... seems like no functions that return anything have been added.
