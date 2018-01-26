# GenArch

*GenArch* is pipeline written in Matlab able to compute whole genome high resolution 3D structure.



##Description

It has been conceived and developed to overcome common computational limitations typical of 3D modeling, especially in the context of single-cell Hi-C, enabling the calculation of the 3D architecture of an individual genome at a usually unattainable resolution.



## Table of Contents



## Prerequisites

*GenArch* is a Matlab script. Therefore it requires Matlab software.



## Download

The script *GenArch.m* can easily be download from this repository.







## Usage

1. Open the script and modify the initial parameters in the first section with the values adapted for your study. 
2. Upload in Matlab the necessary data.
3. Finally, run the script.

### 1. Initial parameters

In the first section there are 5 initial parameters to modify: *C*, *LowRes*, *TADsRes*, *MedRes* and *HiRes*.
Note that resolution values are expressed in *bp*, therefore *100000* indicates *100 kb*.

When opening *GenArch* for the first time, you will see the following:

```
% this section must be modified with the values adapted for the user's
% study case

C = 20; % chromosomes number
LowRes = 10000000; % enter the chosen low resolution (to compute whole-genome reference structure)
TADsRes = 2000000; % enter the chosen TADs-resolution (to identify TAD boundaries)
MedRes = 1000000; % enter the chosen medium resolution (to compute chromosomes structure)
HiRes = 100000; % enter the chosen high resolution (to compute TADs structure)

ResRatioT = TADsRes/HiRes; % scaling factor between the resolution used to identify TAD boundaries and the high resolution (used to compute TADs structure)
ResRatioM = MedRes/HiRes; % scaling factor between the medium resolution (used to compute chromosomes structure) and the high resolution (used to compute TADs structure)
```

- *C* is the number of chromosomes in the studied genome. Replace *20* with the actual number of chromosomes.
- *LowRes* is the resolution at the whole-genome level. It is the same resolution of the whole-genome Hi-C matrix (named *M_LowRes* in the script) and of the low resolution whole-genome 3D structure (called *XYZ_LowRes_gen*). Replace *10000000* with the actual chosen low resolution.
- *TADsRes* is the resolution used to identify TAD boundaries. It is the same resolution of the intra-chromosomal Hi-C matrixes (named *M_TADsRes_#c* in the script). Replace *2000000* with the actual chosen resolution.
- *MedRes* is the resolution at the chromosomal level. It is the same resolution of the chromosomal Hi-C matrixes (named *M_MedRes_#c* in the script) and of the medium resolution chromosomal 3D structures (called *XYZ_MedRes_chr#c*). Replace *1000000* with the actual chosen medium resolution.
- *HiRes* is the resolution at the TADs level. It is the same resolution of the TADs Hi-C matrixes (named *M_HiRes_#c* in the script) and of the high resolution TADs 3D structures (called *XYZ_HiRes_chr#c_TAD#t*). Replace *100000* with the actual chosen medium resolution.

