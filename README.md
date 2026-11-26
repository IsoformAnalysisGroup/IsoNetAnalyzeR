# IsoNetAnalyzeR

<!-- badges: start -->
[![Bioconductor platforms](https://bioconductor.org/shields/availability/release/IsoNetAnalyzeR.svg)](https://bioconductor.org/packages/IsoNetAnalyzeR)
[![Bioconductor devel build](https://bioconductor.org/shields/build/devel/bioc/IsoNetAnalyzeR.svg)](https://bioconductor.org/checkResults/devel/bioc-LATEST/IsoNetAnalyzeR/)
[![R CMD check on Linux](https://img.shields.io/github/check-runs/IsoformAnalysisGroup/IsoNetAnalyzeR/main?nameFilter=R-CMD-check%20%28ubuntu-latest%29&label=R%20CMD%20check%20Linux)](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/actions/workflows/R-CMD-check.yaml)
[![R CMD check on Windows](https://img.shields.io/github/check-runs/IsoformAnalysisGroup/IsoNetAnalyzeR/main?nameFilter=R-CMD-check%20%28windows-latest%29&label=R%20CMD%20check%20Windows)](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/actions/workflows/R-CMD-check.yaml)
[![R CMD check on macOS](https://img.shields.io/github/check-runs/IsoformAnalysisGroup/IsoNetAnalyzeR/main?nameFilter=R-CMD-check%20%28macos-latest%29&label=R%20CMD%20check%20macOS)](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/actions/workflows/R-CMD-check.yaml)
[![Bioconductor devel check](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/actions/workflows/bioc-check.yaml/badge.svg?branch=main)](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/actions/workflows/bioc-check.yaml)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE.md)
<!-- badges: end -->

IsoNetAnalyzeR is a [Bioconductor package](https://bioconductor.org/packages/IsoNetAnalyzeR) that compares the predicted protein-interaction neighbourhoods of transcript isoforms. Given isoforms whose usage goes up and isoforms whose usage goes down, for example from a differential transcript usage analysis, it expands each set in an isoform-resolved predicted interaction network and compares the resulting neighbourhoods per gene and across genes. It also provides connected-component analysis, network diagnostics, plots and enrichment analysis.

## Installation

IsoNetAnalyzeR requires R 4.6 or later. Install it from Bioconductor:

```r
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("IsoNetAnalyzeR")
```

IsoNetAnalyzeR is available from Bioconductor 3.24, the release for R 4.6. If BiocManager warns that the package is not available for an older Bioconductor version, update with `BiocManager::install(version = "3.24")` first.

The development version is on GitHub:

```r
BiocManager::install("IsoformAnalysisGroup/IsoNetAnalyzeR")
```

## Getting started

The vignette walks through a complete analysis of isoform switches between obese type 2 diabetic and lean adipose tissue (GEO GSE141432), using example data shipped with the package. Read it [on Bioconductor](https://bioconductor.org/packages/release/bioc/vignettes/IsoNetAnalyzeR/inst/doc/IsoNetAnalyzeR.html) or from R:

```r
library(IsoNetAnalyzeR)
vignette("IsoNetAnalyzeR", package = "IsoNetAnalyzeR")
```

For your own data, prepare a table with `gene_id`, `isoform_id` and `direction` (`"up"` or `"down"`) and follow the [user instructions](inst/INSTRUCTIONS.md). Statistical seed selection happens upstream; network differences are predictions to interpret alongside independent biological evidence.

## Documentation

- [Vignette](https://bioconductor.org/packages/release/bioc/vignettes/IsoNetAnalyzeR/inst/doc/IsoNetAnalyzeR.html) ([source](vignettes/IsoNetAnalyzeR.Rmd))
- [User instructions](inst/INSTRUCTIONS.md)
- [Runnable synthetic example](inst/examples/full_workflow.R)
- [Network eligibility rationale](inst/NETWORK_ELIGIBILITY.md)
- [Data provenance](inst/PROVENANCE.md) and [data scripts](inst/scripts/README.md)
- [Version history](NEWS.md)

Function reference: `help(package = "IsoNetAnalyzeR")`.

## Getting help

Ask usage questions on the [Bioconductor support site](https://support.bioconductor.org/tag/IsoNetAnalyzeR/) with the tag `IsoNetAnalyzeR`. Report bugs and request features in [GitHub issues](https://github.com/IsoformAnalysisGroup/IsoNetAnalyzeR/issues).

## Citation

Run `citation("IsoNetAnalyzeR")` in R. The Bioconductor DOI is [10.18129/B9.bioc.IsoNetAnalyzeR](https://doi.org/10.18129/B9.bioc.IsoNetAnalyzeR).

## Licence

MIT; see [LICENSE.md](LICENSE.md). The bundled interaction network is derived from STRING physical interactions, which STRING distributes under CC BY 4.0; see [inst/PROVENANCE.md](inst/PROVENANCE.md) for the attribution.
