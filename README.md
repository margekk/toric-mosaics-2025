# toric-mosaics-2025
Tools for working with toric knot mosaics.

## mosaic-gen
`mosaic-gen` is a `rust` program that generates all toric knot mosaics of a given size which are suitably connected, represented as base-11 numbers, and prints these codes to a file. To use, navigate to `mosaic-gen` and execute `cargo run`.

## toric.py
`toric.py` categorizes the lists of mosaics produced by `mosaic-gen` up to HOMFLY polynomial, as well as producing images of mosaics and performing the 1-braid algorithm to produce toric knot mosaics corresponding to torus knots.

### Dependencies
This program uses [`sage`](https://www.sagemath.org/) for its link utilities, as well as the python packages `pillow` for image processing and `ortools` for linear optimization.  
Use `sage --pip install pillow ortools` to import these packages.
### Usage
```
sage toric.py [option]
Valid options:
  -h, --help
      Print a help message and exit
  -i, --images
      Save image(s) of mosaic(s) to file. If used with -f, only an image of the first mosaic with a given HOMFLY polynomial will be saved. 
  -s, --string <mosaic string>
      Print PD code of mosaic for use with other knot software, as well as HOMFLY polynomial.
  -f, --file <input file> <output file>
      Create knot catalog describing mosaics from input file, print catalog to output file
  -r, --rapunzel <p> <q>
      Perform 1-braid algorithm to generate torus knot (p,q)
```
Images are saved in a folder called `images` in the same directory as `toric.py`. You may need to manually create this folder. 
Knot catalogs consist of a list of all unique HOMFLY polynomials corresponding to mosaics in the input file, along with the first mosaic found corresponding to each polynomial.
## Acknowledgement
This material is based upon work supported by the National Science Foundation under Grant No. MPS-2150299
## Disclaimer
Any opinions, findings, and conclusions or recommendations expressed in this material are those of the author(s) and do not necessarily reflect the views of the National Science Foundation.
