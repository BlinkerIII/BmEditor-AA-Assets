# BmEditor-AA-Assets



## Goal



This project aims to convert/preserve assets from Batman Arkham Asylum for use in the Arkham City BmEditor. With the goal being a very "plug and play" workflow, where maps and packages work immediately upon opening them and BmEditor users can freely edit maps/replace assets as they please. This means absolute, or close to absolute, visual parity with Arkham Asylum.

Assets will not be updated/upgraded for any reason. Aside from possible bug fixes or asset fixes, to ensure they work properly and look/function as intended.



##### Supported Assets

* Unreal Packages
* Static Meshes/Static Mesh Actors
* Materials
* Textures
* Particles









## Conversion Scope

You only really need to read this if you plan on contributing. As this lays out what is expected, and some basic terminology so it's easier to communicate.



##### Terminology

"Package" will be referring to any .UPK, which house assets that can be used within levels for level design. "Map" will be referring to any .UMAP within Asylum or City (despite City naming their map files .UPKs).
In Arkham, maps are usually structured with a map file referencing several other map files. "Main Level"/"Level" will be referring to the map file that is usually referencing the other map files. "Sub Level" will refer to any maps referenced by the main level to complete an entire level.



For example. Medical\_A will load most, if not all Medical\_A prefixed levels, such as Medical\_A\_Static\_Art. Medical\_A is in this case a "Main Level".





## Conversion Rule of Thumb



##### Naming/Prefixing

All packages will need to be renamed to start with AA\_ as a prefix. This is to make sure they are compatible with AC packages, and easier to find/see within the editors content browser. This also means any cross package references will need to be made sure to reference AA\_ packages.



##### Cross Package References

For now, it's paramount that references to packages with assets for the purpose of being used by multiple objects. Such as FX\_Noise for example, despite being near identical to AC's FX\_Noise, continue referencing the newly made/renamed AA\_FX\_Noise, this is just to prevent any issues where someone assumes an AC version of an asset is identical to one in AA, and causing a mismatch/inaccuracy without having to manually check the AC version of an asset to be sure that it matches the AA version of said asset or the time it'd take to correct if such.



##### Conversion Methods

So far, the main method for converting packages is as follows

1. Open the package you want to convert (if not downloaded from this repo it should be renamed with an AA\_ prefix)
2. In the content browser, find the package and fully load it then save it
3. Right click the package at it's root, and click bulk export. Export as single file. This should produce a .T3DPKG
4. Right click the package at it's root and click unload. Then delete the package file/remove it from the editor completely.
5. In the content browser, press the Import button, find where you saved the .T3DPKG file and import it. This will produce a new package with all the objects and materials in their original file structure, but avoids any conflicting data that the editor doesn't like which can at times cause crashes.



The caveat to this method is it strips any meshes of their verts, however if you avoid saving the package immediately. You can import the meshes back into the package. Just ensure you import it back with the same name and root. If you do this before you save, it will retain any material references (aside from broken ones) as the original mesh. If you do save, you'll have to manually assign the materials. I would recommend having the meshes exported from UPKE as an FBX, exporting from umodel produces a .pskx, which is not supported by the editor and converting it to .psk using blender, will strip important data such as extra UVs or vert colors.

