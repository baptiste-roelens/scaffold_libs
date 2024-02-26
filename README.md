# Libraries of scaffold for fold-conditioning [RFdiffusion](https://github.com/RosettaCommons/RFdiffusion) designs

## Baker_lab_fc_libraries:
Baker_lab_fc_libraries contains multiple libraries derived from the miniprotein scaffolds published in [Cao *et al.*, 2022](https://rdcu.be/doRco).
The initial library was generated by clustering the miniprotein scaffold structures at 80% homology using [Foldseek](https://www.nature.com/articles/s41586-023-06510-w) to filter out redundant folds and the helper script from RFDiffusion was then used to generate the secondary structure and adjacency pt files.
The 'select' version of the library uses the list of scaffolds in the recommended_library.list of the Cao *et al* and clustering at 90% homology.

### fold specific libraries
As some folds seemed to perform significantly better in specific campaigns, custom libraries were generated on these folds: HHH, HHH, folds with beta-sheets and no loop shorter than 2 residues, and folds with a "long" helix. These libraries have overall performed pretty poorly and in particular generate designs with high rate of "type I" failure (as defined in [Bennett *et al.*, 2023](https://rdcu.be/doS2w))

## Viroxis library
The Viroxis libraries were obtained by semi-random generation of secondary structure and adjacency information and test of this fold-conditioning template by diffusion of designs that are then tested for type I failure using ProteinMPNN/AlphaFold2 predicition.

The February 2024 version of the library also includes an additional step, checking whether the diffused designs of the fold-conditioning template have a Tm lower than 0.45 to all designs diffused with templates already in the library. This is to promote as much diversity as possible in the library.
