# LD-3D-TFM
Large Deformation Traction Force Microscopy 

This repositry contains the Matlab m-files to run our LD 3D TFM algorithm. The first part of the package includes the FIDVC algorithm, which is how the 3D displacement fields are calculated. The second part of the code package includes converting those displacement fields into 3D surface tractions as described in [Toyjanova, Bar-Kochba et al., PloS One, 2014](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0090976).

Depending on the geometry of the problem at hand, the included surface normal finder algorithm might need additional modification for traction calculation in fully embedded systems or on arbitrary geometries. Alternatively, the user can supply the his/her own point-by-point surface normals to calculate the surface tractions (e.g., Matlab has several already existing image processing options for extracting surface normals from rendered surfaces).


### Important pages
* [Download latest version v1.1!](https://github.com/FranckLab/LD-3D-TFM/releases)
* [Example data](https://app.globus.org/file-manager?origin_id=86401693-5974-4013-b498-eb4484e08eb4&origin_path=%2FFranckLab%2FLD-3D-TFM_example%2F)
* [FAQ](https://github.com/FranckLab/LD-3D-TFM#faq)
* [Questions/Issues](https://github.com/FranckLab/LD-3D-TFM/issues)
* [Bug Fixes/history](https://github.com/FranckLab/LD-3D-TFM/wiki/Bug-Fixes!)
* [Cite](https://github.com/FranckLab/LD-3D-TFM#cite)
* [Franck Lab](http://franck.engin.brown.edu)
 
## Running 3D-VTFM

### C Compiler
To run you need a compatible C compiler. Please see
(http://www.mathworks.com/support/compilers/R2015a/index.html)

### Input 3D Image Stack Requirements
* To check if the 3D image stack have the required speckle pattern and intensity values for correlation please use our [DVC simulator](https://github.com/FranckLab/DVC-Simulator).
* The 3D image stack need to be saved in a 3 dimensional matrix (intensity values are stored at x, y and z position) in **vol*.mat** files.  
* We recommend that the input image stack at each dimension should have at least 1.5 times of the subset size as the number of pixels. The default subset size is 128x128x64, so we recommend that the minimum input volume size should be 192x192x96.
* The size of the input image stack should be divisible by 0.5 times the size of the subset. 

### Running included example case
1. Make sure that the main files and the supplemental m files (from file exchange) are added to the path in Matlab.
2. Download and save the [example volume data](https://drive.google.com/folderview?id=0ByhZqlrbo5srdFhWampiT0g4Xzg&usp=sharing) in the example folder. 
3. Run the exampleRunFile.m file

### Health warning!
FIDVC in the 3D-VTFM requires a 3D stack to be read in, which depending on the volume size can require a **large amount of RAM** in Matlab.

## Files
* Main files
 - calculateNormals.m
 - calculateSurfaceUi.m
 - findSurface.m
 - fun3VDTFM.m
 - removeOutliers.m

* Supplement m files from the MATLAB file exchange:
 - gridfit.m
 - inpaint_nans.m
 - inpaint_nans3.m

* Example Run files
 - exampleRunFile.m
 - [example volume data](https://app.globus.org/file-manager?origin_id=86401693-5974-4013-b498-eb4484e08eb4&origin_path=%2FFranckLab%2FLD-3D-TFM_example%2F) (vol00.mat, vol01.mat).

## FAQ
**What are the requirements for the input 3D image stack?**

Please refer to [input 3D Image Stack Requirements](https://github.com/FranckLab/FIDVC/blob/master/README.md#input-3d-image-stack-requirements).


## Cite
If used please cite:
[Toyjanova J., Bar-Kochba E., López-Fagundo C., Reichner J., Hoffman-Kim D, Franck, C. (2014) High Resolution, Large Deformation 3D Traction Force Microscopy. PLoS ONE 9(4): e90976. doi:10.1371/journal.pone.0090976](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0090976)

```bibtex
@article{toyjanova2014high,
  title={High resolution, large deformation 3D traction force microscopy},
  author={Toyjanova, Jennet and Bar-Kochba, Eyal and Lopez-Fagundo, Cristina and Reichner, Jonathan and Hoffman-Kim, Diane and Franck, Christian},
  journal={PloS one},
  volume={9},
  number={4},
  pages={e90976},
  year={2014},
  publisher={Public Library of Science}
}
}
```

## Contact and support
For questions, please first refer to [FAQ](https://github.com/FranckLab/LD-3D-TFM#faq) and [Questions/Issues](https://github.com/FranckLab/LD-3D-TFM/issues). Add a new question if similar issue hasn't been reported. We shall help you at the earliest. The author's contact information can be found at [Franck Lab](http://franck.engin.brown.edu).

