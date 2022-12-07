# Quality Control of WGS

Welcome to the repo for GA4GH Quality Control of Whole Genome Sequencing metrics and reference implementations (QC of WGS workgroup).

## Motivation & Mandate

Robust quality control (QC) of results is key for the successful delivery of population-scale sequencing efforts, even more so when the scope of such efforts includes clinical diagnostic testing. Multiple studies have discussed the need to evaluate the performance of variant calling pipelines prior to introducing them in production, and consortia like Genome in a Bottle (GIAB) and the Sequencing Quality Control 2 Study have provided practical guidelines on how to achieve such evaluations using well-characterized cell lines (i.e. reference materials, or RMs). However, cell-line based RMs do not fully represent the heterogeneity and diversity of primary samples derived from research or clinical samples, nor give metrics for every sample run, and it is thus important to continue to monitor the quality of results beyond initial methods validation.

For development and production samples, QC of Whole Genome Sequencing (WGS) results can be achieved through a range of tools that compute metrics from FASTQ, BAM, and/or VCF files. Recommendations on which metrics to include in routine QC have been discussed in published guidelines and continue to be actively developed. Nonetheless, contrary to the situation encountered when discussing best practices for benchmarking, standardized definitions and implementations of recommended QC metrics have yet to be addressed. For example, guidelines will often refer to the need to track genome coverage, and multiple tools exist to directly report this metric or to produce intermediate outputs that can be used to calculate it (i.e. picard, samtools, sambamba, indexcov, mosdepth). Yet the interpretation and comparison of results require an accurate understanding of how the metric was calculated, e.g. does it include all chromosomes or autosomes only, are unknown or unspecified bases (N bases) masked, does the metric exclude duplicates and portions of the reads that do not align to the genome from end to end (soft-clipped bases), does it include any base quality or mapping quality filters, what is the window size used, etc. Even though such details can have a substantial effect on the results, they are often not reflected in the documentation of the tool, and it is necessary to inspect the source code to retrieve them.

Given the increase in the number of population-scale studies and clinical genome testing, we believe that creating a common framework for QC of WGS results is needed to ensure that data generation adheres to published guidelines, in turn establishing confidence in the data quality and facilitating the exchange of results across initiatives. We propose to engage with GA4GH/NI contributors and relevant tool developers to work on a reference implementation that would provide practical recommendations on this matter. In particular, such work would complement existing guidelines by providing (i) standardized definitions for key QC metrics, (ii) a new file format/schema to make it easier to report QC metric outputs, (iii) tools for calculating them, and (iv) benchmarking resources that would aid in the interpretation and monitoring of results.

## Documentation

The core documentation can be found in [docs](https://github.com/ga4gh/quality-control-wgs/tree/main/docs).
Other Links of Interest:

- [Roadmap Document](https://docs.google.com/document/d/1T2Ls5HRz5xR9sQkH6YnktFWfjEEmSBchA6twHbfGJ_o/edit?usp=sharing)
- [Meeting Minutes](https://docs.google.com/document/d/1gjJ_C2OK8aTEbAOBpWn9ygk9VRUPTP0AICa86DBqOOo/edit?usp=sharing)
- [Landscape Analysis](https://docs.google.com/spreadsheets/d/1SKy1p38RJf3YNJ33XPIS8qLY5exF93pxdfozaiMnJqQ/edit?usp=share_link)
- [Original Proposal](https://docs.google.com/document/d/1yrvByDgRdE4WPT1MDfKpF7cbDT6oXLAX6gnlQkud5_I/edit?usp=share_link)

## Mailing List / Google Group

This project has a Google Group/mailing list for those interested in contributing to development of the stadard or following akong with progress. Please reach out to lindsay.smith@ga4gh.org for more information.
