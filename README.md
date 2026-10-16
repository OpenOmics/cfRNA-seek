<div align="center">
   
  <h1>cfRNA-seek 🔬</h1>
  
  **_cell-Free RNA-sequencing pipeline_**

  [![tests](https://github.com/OpenOmics/cfRNA-seek/workflows/tests/badge.svg)](https://github.com/OpenOmics/cfRNA-seek/actions/workflows/main.yaml) [![docs](https://github.com/OpenOmics/cfRNA-seek/workflows/docs/badge.svg)](https://github.com/OpenOmics/cfRNA-seek/actions/workflows/docs.yml) [![GitHub issues](https://img.shields.io/github/issues/OpenOmics/cfRNA-seek?color=brightgreen)](https://github.com/OpenOmics/cfRNA-seek/issues)  [![GitHub license](https://img.shields.io/github/license/OpenOmics/cfRNA-seek)](https://github.com/OpenOmics/cfRNA-seek/blob/main/LICENSE) 
  
  <i>
    This is the home of the pipeline, cfRNA-seek. Its long-term goals: simplify cell-free RNA-seq processing, quantify gene expression, and provide comprehensive quality assessments to support downstream analyses!
  </i>
</div>

## Overview

Welcome to cfRNA-seek! Before getting started, we highly recommend reading through [cfRNA-seek's documentation](https://openomics.github.io/cfRNA-seek/).

The **`./cfRNA-seek`** pipeline is composed several inter-related sub commands to setup and run the pipeline across different systems. Each of the available sub commands perform different functions: 

 * [<code>cfRNA-seek <b>run</b></code>](https://openomics.github.io/cfRNA-seek/usage/run/): Run the cfRNA-seek pipeline with your input files.
 * [<code>cfRNA-seek <b>unlock</b></code>](https://openomics.github.io/cfRNA-seek/usage/unlock/): Unlocks a previous runs output directory.
 * [<code>cfRNA-seek <b>install</b></code>](https://openomics.github.io/cfRNA-seek/usage/install/): Download reference files locally.
 * [<code>cfRNA-seek <b>cache</b></code>](https://openomics.github.io/cfRNA-seek/usage/cache/): Cache software containers locally.

**cfRNA-seek** is a comprehensive cell-free RNA sequencing (cfRNA-seq) pipeline designed to streamline the analysis of paired-end sequencing data, from raw reads to gene expression quantification. It accommodates different library preparation strategies, including those using unique molecular identifiers (UMIs), and integrates read preprocessing, alignment, duplicate removal, and gene-level counting. Consolidated quality reports assess sequencing performance, library characteristics, and potential biases across samples and study groups, providing a foundation for downstream analysis and biological discovery. It relies on technologies like [Singularity<sup>1</sup>](https://singularity.lbl.gov/) to maintain the highest-level of reproducibility. The pipeline consists of a series of data processing and quality-control steps orchestrated by [Snakemake<sup>2</sup>](https://snakemake.readthedocs.io/en/stable/), a flexible and scalable workflow management system, to submit jobs to a cluster.

As input, it accepts a set of FastQ files and can be run locally on a compute instance or on-premise using a cluster. A user can define the method or mode of execution. The pipeline can submit jobs to a cluster using a job scheduler like SLURM (more coming soon!). A hybrid approach ensures the pipeline is accessible to all users. Before getting started, we highly recommend reading through the [usage](https://openomics.github.io/cfRNA-seek/usage/run/) section of each available sub command.

For more information about issues or trouble-shooting a problem, please checkout our [FAQ](https://openomics.github.io/cfRNA-seek/faq/questions/) prior to [opening an issue on Github](https://github.com/OpenOmics/cfRNA-seek/issues).

## Dependencies

**Requires:** `singularity>=3.5`  `snakemake<=7.32.4`

At the current moment, the pipeline uses a mixture of enviroment modules and docker images; however, this will be changing soon! In the very near future, the pipeline will only use docker images. With that being said, [snakemake](https://snakemake.readthedocs.io/en/stable/getting_started/installation.html) and [singularity](https://singularity.lbl.gov/all-releases) must be installed on the target system. Snakemake orchestrates the execution of each step in the pipeline. To guarantee the highest level of reproducibility, each step of the pipeline will rely on versioned images from [DockerHub](https://hub.docker.com). Snakemake uses singularity to pull these images onto the local filesystem prior to job execution, and as so, snakemake and singularity will be the only two dependencies in the future.

## Installation

Please clone this repository to your local filesystem using the following command:
```bash
# Clone Repository from Github
git clone https://github.com/OpenOmics/cfRNA-seek.git
# Change your working directory
cd cfRNA-seek/
# Add dependencies to $PATH
# Biowulf users should run
module load snakemake singularity
# Get usage information
./cfRNA-seek -h
```

## Contribute

This site is a living document, created for and by members like you. cfRNA-seek is maintained by the members of [OpenOmics](https://openomics.github.io) and is improved by continous feedback! We encourage you to contribute new content and make improvements to existing content via pull request to our [GitHub repository](https://github.com/OpenOmics/cfRNA-seek).


## Cite

If you use this software, please cite it as below:  

<details>
  <summary><b><i>@BibText</i></b></summary>
 
```text
Citation coming soon!
```

</details>

<details>
  <summary><b><i>@APA</i></b></summary>

```text
Citation coming soon!
```

</details>

## References

<sup>**1.**  Kurtzer GM, Sochat V, Bauer MW (2017). Singularity: Scientific containers for mobility of compute. PLoS ONE 12(5): e0177459.</sup>  
<sup>**2.**  Koster, J. and S. Rahmann (2018). "Snakemake-a scalable bioinformatics workflow engine." Bioinformatics 34(20): 3600.</sup>  
