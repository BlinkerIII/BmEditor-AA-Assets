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


## Contributing



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
>Cross package references will also need to account for the addition of the prefix 

### Conversion Process of packages

This ensures the packages are **FULLY** compatible and stable within the editor.
> [!CAUTION]
> Not converting can cause crashes when:
> 
> You cook a package using them
> 
> You attempt to edit them in the editor
> 
> Or otherwise general instability

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
> This process will strip the vertices of mesh objects. However if you export all meshes that the package carries, in the editor or UPKE. You can then import said meshes over the .T3DPKG's mesh assets.
>
> Saving the package **BEFORE** reimporting the mesh objects will cause material references to become null.
>
> Therefore it is recommended to have all your meshes ready and extract, before you import the .T3DPKG.
 

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






