# GenomicDataCommons

Provide _R_ access to the NCI [Genomic Data Commons][] portal.

This package is under development.

```{r}
library(GenomicDataCommons)
endpoints()    # what can you do? See help page for each endpoint
status()       # is the service up?
experiments()  # available experiments
```

Accessing restricted data requires an [authentication token][]. This
in turn requires eRA and dbGAP access. Provide the token as a
character string (or, for `manifest()`, a file path).

```{r}
slicing("df80679e-c4d3-487b-934c-fcc782e5d46e", symbols=c("BRCA1", "BRCA2"),
        token=token)
```

## TODO

- [x] `manifest()` endpoint
- [x] `transfer()`: download manifest files via GDC Data Transfer Tool
- [x] Authentication
- [x] `slicing()` endpoint
- [ ] filters
- [ ] `gdcdata()` (data endpoint) download md5sums validation
- [ ] validate slicing 'regions' argument
- [ ] Rename as 'gdc' -- accessing gdc portal, without _Bioconductor_
  dependencies
- [ ] Develop `GenomicDataCommons` -- _Bioconductor_ API supporting
  [GenomicRanges][], [GenomicAlignments][], [VariantAnnotation][].

## WON'T DO

- [ ] implement submission

[Genomic Data Commons]: https://gdc-portal.nci.nih.gov/
[GenomicRanges]: https://bioconductor.org/packages/GenomicRanges
[GenomicAlignments]: https://bioconductor.org/packages/GenomicAlignments
[VariantAnnotation]: https://bioconductor.org/packages/VariantAnnotation
[authentication token]: https://gdc-docs.nci.nih.gov/API/Users_Guide/Authentication_and_Authorization/
