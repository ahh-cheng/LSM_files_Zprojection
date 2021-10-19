# LSM_files_Zprojection
ImageJ macro for converting Zeiss LSM files to Zprojections

The macro template to process multiple images in a folder is from https://forum.image.sc/t/batch-processing-several-folder/6636

`script_subtract_bleedthrough.txt` uses FIJI image calculator to subtract C1 signal from C2 and C4, and then output the final max. z-projection as `.tif` files. Parameters can be modified to subtract the signals using different channels and/or output the image in different formats (e.g., z-stack instead of z-projection, .png instead of `.tif`).

`auto_max_lsm510_2tiles.txt` uses `Bio-Formats Importer` in FIJI to process `.lsm` files produced by the newer version of Zeiss LSM510 imaging software. Particularly useful when the `.lsm` file is a multidimensional scan (tile scan) of a sample. It outputs max. z-projection of the image as `.tif` files. `Bio-Formats Importer` cannot determine the spatial orientation of the image when the `.lsm` files contains only two tiles (due to metadata formatting problem?). Such files have to be handled differently using the `Combine` function.
