# Documentation for Knuckles Ate 3000 Grapes

**Note: This file is meant to be viewed within GitHub. If your text viewer doesn't support Markdown, some things may not appear as intended.**

To start, add this to your mod's main.lemon:
```
#if !KNUX_ATE_3K_GRAPES
	include ../../../../knux_ate_3k_grapes.lemon
#endif
```

**IMPORTANT!** While you're developing a mod, you'll most likely have the mod as a uncompressed folder (path goes like `/mods/coolmod01/...`), so you'll need to remove one `../` from the include line. This is because it will be looking at the wrong folder. Remember to add it back when compressing your mod to upload it on any file hosting platform!

The preprocessor check is there so the mod doesn't load the file if there's already a mod that is using it.

Now, with the basic stuff out of the way, let's get into what this single file offers:

## Constants

You can identify each zone with a name instead of numbers.
Examples: `CNZ2`, `LRZ3`, `SSZK`, `BONUS_ITEMBALL`

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

BONUS_ITEMBALL, BONUS_SPHERES and BONUS_SLOT
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

`u32 findObjectSlotWithUpdateAddress(u32 address)`
- Searches through 90 object slots starting from `0xffffb128` until it finds an object with its update address set to the desired one.

`u8 loadExternalPaletteDataToAtex(string key, u8 line, u16 atex, bool nonfading, bool underwater)`
- Loads a palette file to memory in one of the palette indexes.
- Parameters:
	- `key` is the palette's filename (without .png).
	- `line` is the line to load from.
	- `atex` works the same as `Renderer.drawSprite`.
	- If `nonfading` is true, the palette will be loaded to the non-fading palette location (used when fading in from black or white)
	- If `underwater` is true, the palette will be loaded to the secondary palette location.
- Returns the number of colors loaded.

`void YeetPlayer2()`
- Throw the second character into the distance.
- Tails hates you.
