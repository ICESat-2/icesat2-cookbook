<img src="https://www.nasa.gov/wp-content/uploads/2023/03/icesat2-logo_0.jpg" 
alt="thumbnail" width="300"/>

# ICESat-2 Cookbook

[![nightly-build](https://github.com/ICESAT-2HackWeek/icesat2-cookbook/actions/workflows/nightly-build.yaml/badge.svg)](https://github.com/ICESAT-2HackWeek/icesat2-cookbook/actions/workflows/nightly-build.yaml)
[![Binder](https://binder.projectpythia.org/badge_logo.svg)](https://binder.projectpythia.org/v2/gh/ICESAT-2HackWeek/icesat2-cookbook/main?labpath=notebooks)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.10519966.svg)](https://doi.org/10.5281/zenodo.10519966)

This Project Pythia Cookbook is a compilation of tutorials developed from 2019 
to present as part of the NASA / UW eScience hackweek program. The purpose of
the tutorials is to help people with data access and to demonstrate a variety
of disciplinary use cases.

## Motivation

The ICESat-2 mission provides valuable data for measuring changes in glaciers, 
ice sheets, sea ice, clouds and land surface systems. There are numerous data
products and methods for accessing and analyzing data. The goal of these 
tutorials is to streamline data access, reduce duplication of effort and 
build an open science community around ICESat-2 algorithms and software.

## Authors

[Ben Smith](@smithb), 
[Michalea King](@michaleaking), 
[Tyler Sutterley](@tsutterley),
[Anthony Arendt](@aaarendt),
[Jessica Scheick](@JessicaS11),
[Mark Welden-Smith](@markweldensmith)

more to be added

### Contributors

<a href="https://github.com/ICESAT-2HackWeek/icesat2-cookbook/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=ICESAT-2HackWeek/icesat2-cookbook" />
</a>

## Structure

This cookbook is broken up into two main sections - "Foundations" 
and "Example Workflows."

### Section 1: Foundations

* Mission Overview
* Data Access
* Filtering
* Geospatial Transforms
* Integration
* Cloud Computing
* Machine Learning
* Visualization

### Section 2: Example Workflows for Specific Disciplines

* Land Ice
* Sea Ice
* Inland Hydrology
* Bathymetry
* Snowdepth

## Running the Notebooks

You can either run the notebook using [Binder](https://binder.projectpythia.org/) or on your local machine.

### Running on Binder

The simplest way to interact with a Jupyter Notebook is through
[Binder](https://binder.projectpythia.org/), which enables the execution of a
[Jupyter Book](https://jupyterbook.org) in the cloud. The details of how this works are not
important for now. All you need to know is how to launch a Pythia
Cookbooks chapter via Binder. Simply navigate your mouse to
the top right corner of the book chapter you are viewing and click
on the rocket ship icon, (see figure below), and be sure to select
“launch Binder”. After a moment you should be presented with a
notebook that you can interact with. I.e. you’ll be able to execute
and even change the example programs. You’ll see that the code cells
have no output at first, until you execute them by pressing
{kbd}`Shift`\+{kbd}`Enter`. Complete details on how to interact with
a live Jupyter notebook are described in [Getting Started with
Jupyter](https://foundations.projectpythia.org/foundations/getting-started-jupyter.html).

Note, not all Cookbook chapters are executable. If you do not see
the rocket ship icon, such as on this page, you are not viewing an
executable book chapter.


### Running on Your Own Machine

If you are interested in running this material locally on your computer, 
you will need to follow this workflow:


1. Clone the `https://github.com/ProjectPythia/icesat2-cookbook` repository:

   ```bash
    git clone https://github.com/ProjectPythia/icesat2-cookbook.git
   ```

1. Move into the `icesat2-cookbook` directory
   ```bash
   cd cookbook-example
   ```
1. Create and activate your conda environment from the `environment.yml` file
   ```bash
   conda env create -f environment.yml
   conda activate icesat2-cookbook
   ```
1. Move into the `notebooks` directory and start up Jupyterlab
   ```bash
   cd notebooks/
   jupyter lab
   ```

### Running with Pixi

Alternatively, you can use [Pixi](https://pixi.sh/) for a more streamlined environment management experience:

1. Install Pixi following the [installation instructions](https://pixi.sh/latest/#installation)

2. Clone the `https://github.com/ProjectPythia/icesat2-cookbook` repository:

   ```bash
    git clone https://github.com/ProjectPythia/icesat2-cookbook.git
   ```

3. Move into the `icesat2-cookbook` directory

   ```bash
   cd icesat2-cookbook
   ```

4. Install dependencies and start JupyterLab with a single command:

   ```bash
   pixi run start
   ```

This will automatically create the environment, install all dependencies, and launch JupyterLab in the `notebooks` directory.

#### Exporting Conda Environment with Pixi

If you're using pixi and want to generate a conda-compatible `environment.yml` file for sharing or reproducibility:

```bash
pixi run export-env
```

This command will export the pixi workspace to a conda environment file (`environment.yml`) that can be used with conda or mamba.
