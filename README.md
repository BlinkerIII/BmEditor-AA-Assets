# BmEditor-AA-Assets 



## Goal



This project aims to convert/preserve assets from Batman Arkham Asylum for use in the Arkham City BmEditor. With the goal being a very "plug and play" workflow, where maps and packages work immediately upon opening them and BmEditor users can freely edit maps/replace assets as they please. This means absolute, or close to absolute, visual parity with Arkham Asylum.

> [!NOTE]
> Assets will not be updated/upgraded for any reason. Aside from possible bug fixes or asset fixes, to ensure they work properly and look/function as intended.

### Supported Assets

| Asset Type   | Supported      |
|    :---:     |     :---:      |
|Maps          |:white_check_mark:|
|Packages      |:white_check_mark:|
|Static Meshes |:white_check_mark:|
|Textures      |:white_check_mark:|
|Materials     |:white_check_mark:|
|Particles     |:white_check_mark:|
|Cutscenes           |:x:|
|UnrealScript/Classes|:x:|
|Gameplay Objects    |:x:|
|Sounds              |:x:|

Gameplay Objects and Sounds may be considered in the future.

If you wish to contact me, I'm most active in [Arkham Workshop](https://discord.com/invite/arkhamworkshop).

Also big thanks to Bit for uncooking the packages to begin with and making BmEditor!


## Contributing

### General Notes

For now the unconverted packages will all be prefixed with AA_, just so if you use this as a place to install them for converting them. You don't have to rename them yourself. If it turns out to be better/easier if they remain their original name until being fully converted, let me know!

Below are lists of some important or unimportant packages.

<details>
<summary>Resource Packages</summary>
These are packages which contain commonly referenced assets, which will usually be referenced cross package. And will be converted already or as soon as possible.

```
Floor_Tiles
FX_BulletHits
FX_Combat
fx_decals
fx_exlosion
FX_Forensics
FX_Godrays
fx_Goo
FX_grapple
FX_Interactive
FX_Liquid
FX_Liquid
FX_Luminol
fx_misc
FX_molecules
FX_noise
fx_security
fx_smoke
FX_Sparks
FX_Trail
FX_Weather
Game_Grate_Wall
Game_Pickups
guard
LIGHTS_Int
LuminolGrenade_3p
Map
MAT_Glass
MAT_GrungeOverlay
MAT_Metal
Mental_Patient
MyPackage
OBJ_FireExtinguisher
OBJ_Gas_Dispenser
OBJ_LOCKER
SIGN_Interior
SIGN_Lift
```
This list can change.
 
</details>
<details>
<summary>Useless Packages</summary>
A great many packages are relatively useless/redundant. As their assets aren't usable in the editor, or aren't in scope for this project.

Mostly any packages with an EN prefix, or SFX in the name will only contain soundfiles.
</details>


### Recommended Tools

[UPKE](https://www.nexusmods.com/site/mods/587) is recommended for viewing, editing, and extracting assets from AA.

> [!IMPORTANT]
> Using [UModel](https://www.gildor.org/en/projects/umodel) is viable, however it exports static meshes as .pskx, which is only supported by an addon for Blender. The addon also does **NOT** support extra uvs, or vertex colors on export.


[BmEditor](https://github.com/etkramer/BmEditor) is needed for creating, viewing, and testing maps/packages that have been created or converted. (duh)


## Conversion Rule of Thumb

>[!NOTE]
>"Package" will be referring to any .UPK, which houses assets that can be used within levels for level design.
>
> "Map" will be referring to any .UMAP within Asylum or City (despite City naming their map files .UPKs).



In Arkham, maps are usually structured with a map file referencing several other map files. "Main Level"/"Level" will be referring to the map file that is usually referencing the other map files. "Sub Level" will refer to any maps referenced by the main level to complete an entire map.



For example. Medical\_A will load most, if not all Medical\_A prefixed levels, such as Medical\_A\_Static\_Art. Medical\_A is in this case a "Main Level".

### Naming
For now, it's paramount that **ALL** packages be renamed to include "AA_" as a prefix.

This is to avoid conflicts with AC Packages and make AA packages easily visible in the editor's content browser.



>[!NOTE]
>Maps and Objects are to retain their **ORIGINAL** name
>
>Cross package references will also need to account for the addition of the prefix 

### Conversion

This ensures the packages/maps are **FULLY** compatible and stable within the editor.
> [!CAUTION]
> Not converting can cause general instability or crashes!!!

Usually these crashes will occur when:

 You cook a map with an unconverted package
 
 You attempt to edit them in the editor 
 
 You open/edit an object within the map or package

#### Package Conversion

1. Fully load the package you want to convert in the content browser
   - Once fully loaded save the package
2. Right click package
    - Select "Bulk Export"
      - Tick "Export As One Object"
3. Once exported. Right click the package in the content browser
   - Select Unload
4. Delete the original package from your editor files
5. Finally in the content browser select "Import" near the bottom
   - Find the .T3DPKG from wherever you saved it and click Import
6. Finally, you now have a stable package to edit, correct, and use freely within the editor.

> [!CAUTION]
> This process will strip the vertices of mesh objects.

To avoid this you can reimport the meshes **BEFORE** saving the new package. Which will retain all material references.

 Therefore it is recommended to have all your meshes ready and extracted, before you import the .T3DPKG.
 

#### Correcting packages
Most uncooked AA packages will have some uncooking mistakes, or null references. If they aren't corrected upon importing a .T3DPKG, or end up mismatching because of the AA_ prefix addition. It is important that they're corrected.

Possible mismatches are
* Material references of a mesh object
* Texture references of a material
* Cross package references

> [!NOTE]
> it is important that any cross package references to packages that exist in AC are corrected to reference an AA converted package.
>
> AC Packages that do have similar names to AA Packages could have missing, updated, or completely different assets.






