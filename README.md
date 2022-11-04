# SuPepMem
SuPepMem is an open-access repository containing Molecular Dynamics simulations of different natural and artificial peptides (antimicrobial, anticancer, antiviral, etc) interacting with membrane models for healthy mammal, bacteria, viruses, cancer or senescent cells. 

 Citation: F. Suarez-Leston, M. Calvelo, G. F Tolufashe, A. Muñoz, U. Veleiro, C. Porto, M. Bastos, Á. Piñeiro, R. Garcia-Fandino, SuPepMem: A database of innate immune system peptides and their cell membrane interactions, Comput. Struct. Biotechnol. J. 2022, 20, 874-881

In this repository you can find the scripts used to obtain the SuPepMem trajectory analysis.


<p align="center">
  <img src="https://user-images.githubusercontent.com/66941005/155822626-9a3d667d-cf97-44cb-b0a4-29d1b485c6d4.gif" alt="animated" />
</p>

<div align="center">
 
[![GitHub forks](https://img.shields.io/github/forks/Eines-Informatiques-Avancades/Project-II)](https://github.com/Eines-Informatiques-Avancades/Project-II/network)
[![GitHub issues](https://img.shields.io/github/issues/Eines-Informatiques-Avancades/Project-II)](https://github.com/Eines-Informatiques-Avancades/Project-II/issues)
![GitHub pull requests](https://img.shields.io/github/issues-pr/Eines-Informatiques-Avancades/Project-II)
[![GitHub stars](https://img.shields.io/github/stars/Eines-Informatiques-Avancades/Project-II)](https://github.com/Eines-Informatiques-Avancades/Project-II/stargazers)
![GitHub repo size](https://img.shields.io/github/repo-size/Eines-Informatiques-Avancades/Project-II)
[![GitHub license](https://img.shields.io/github/license/Eines-Informatiques-Avancades/Project-II)](https://github.com/Eines-Informatiques-Avancades/Project-II)
![GitHub language count](https://img.shields.io/github/languages/count/Eines-Informatiques-Avancades/Project-II)

![Fortran](https://img.shields.io/badge/Fortran-%23734F96.svg?style=for-the-badge&logo=fortran&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
</div>


<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#Pre-requirements">Pre-requirements</a></li>
    <li><a href="#Usage">Usage</a></li>
    <li><a href="#wiki">Wiki</a></li>
    <li><a href="#Distribution-of-tasks">Distribution of tasks</a></li>
    <li><a href="##FAQs">FAQs</a></li>
   <li><a href="#contributing">Contributing</a></li>
  </ol>
</details>


<!-- Pre-requirements -->
### General Pre-requirements 📋

In order to run the program it is necessary to have the following requirements installed:

The program is written in Fortran language so a compiler like [gfortran](https://gcc.gnu.org/wiki/GFortran) or equivalent is needed.

Python programs are used to perform statistical analysis of the obtained data. Therefore, Python version 3 or higher is required. Also, for python programs to work properly the following libraries are needed:

- [Numpy](https://numpy.org)
- [Matplotlib](https://matplotlib.org)
- [Sys](https://docs.python.org/3/library/sys.html)

To be able to use these libraries, it is recommended to work with anaconda environment.

In case the user wishes to see the trajectory generated in the simulation program, the use of the [VMD](https://www.ks.uiuc.edu/Research/vmd/) program is recommended.

<!-- Paralel Code -->
### Paralel Code Pre-requirements
In the [Paralel](https://github.com/Eines-Informatiques-Avancades/Project-II/tree/master/Paralel) folder there is a parallelized version of the code in order to have an optimized and faster version of the program. 

To be able to work with this code it is necessary to have the [Open MPI](https://www.open-mpi.org/) package installed, which can be downloaded and installed following the steps indicated on the official website.

If you are working in an anaconda environment, an easy way to install the [Open MPI](https://www.open-mpi.org/) package is to use the following command:
```
conda install mpi4py openmpi
```

<!-- Usage -->
## Usage ⚙️
In order to run this program, first one has to choose whether to work with the serial or parallel version. The necessary files are found in the Working_area of each version directory:

- Serial: [Working_area](https://github.com/Eines-Informatiques-Avancades/Project-II/tree/master/Serie/Working_Area)
- Paralel: [Working_area](https://github.com/Eines-Informatiques-Avancades/Project-II/tree/master/Paralel/Working_Area)

This directory contains the following files:

- **Makefile**: Compiles and executes the whole program. It is also designed to manage all the generated files for a more user-friendly experience.
- **parameters.txt**: Data file that contains all the parameters related to the system of study (Number of particles, geometry of the lattice (at the moment only sc available), density, mass,...), the data related to the simulation (Initial temperature, initial distribution, thermostat, integration method,...) and a final section where the names of the output data files are defined. Additionaly, this file contains the necessary parameters in order to run correctly the radial distribution function (g(r)) calculation. 

To start using the program, the following command has to be used:
```
make all
```
This will compile and execute the program and all the statistic calculations will also be performed. It is **important** to point out that in order to perform the whole program, the user is asked a couple of questions related to the statistical study, so keep an eye on this, otherwise the program will not reach completion.

Once the process has been completed, the unnecessary files are cleaned and the output files are sent to their corresponding directories (Results -> Data and Figures).

**Note**: Due to the modular nature of the program, it can be executed in parts (or modules) by using the following commands:

```
# Compilation of the Main and Gofr programs (Fortran programming language)
make compile

# Execution of the Main and Gofr programs (Fortran programming language)
make run

# Computes the statistical analysis and generates the corresponding figures as outputs (Python programming language)
make statistic

# Move data files and figures (outputs) to  the Results folder (Please, don't do it before the statistical analysis, the files to be analyzed must be in the working folder) 
make move

# Removes objects, executables and unnecessary .mod files
make clean

# If the user wants to return the repository to its original state (remove unnecessary files and results), the following command can be used
make clean_all
```
The program generates an .xyz file containing the trajectory of the system. It is highly recommended the use of [VMD](https://www.ks.uiuc.edu/Research/vmd/) in order to visualize the results.

## Wiki 📖

...Work in progress...


<!-- DISTRIBUTION OF TASKS -->
## Distribution of tasks ✒️ 
Project coordinator: Àlex Teruel

- Main program (Fortran program): Joint work
- Initial state (Fortran module): Oliver Loveday
- Boundary conditions (Fortran module): Adrià Calzada
- Forces (Fortran module): Daniel Conde
- Integration (Fortran module): Àlex Teruel
- Radial distribution function (Fortran program): Àlex Teruel
- Statistics (Python program): Daniel Conde
- Visualization of Results (Python program): Joint work
- Makefile: Joint work

The joint work tasks will be carried out (to a greater extent) by those members who are more advanced in their corresponding tasks.

<!-- FAQs -->
## FAQs

### What is that paralel file? Wasn't the program a serie algorithm?

Paralel directory is a program that uses mpi, so you have a paralelize version of the program in this file.


<!-- CONTRIBUTING -->
## Contributing 🖇️
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.


