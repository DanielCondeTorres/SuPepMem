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

The program is written in Python language so Python version 3 or higher is required. Also, for python programs to work properly the following libraries are needed:
- [Os](https://docs.python.org/3/library/os.html)
- [Re](https://docs.python.org/3/library/re.html)
- [Sys](https://docs.python.org/3/library/sys.html)
- [Json](https://docs.python.org/3/library/json.html)
- [Time](https://docs.python.org/3/library/time.html)
- [Argparse](https://docs.python.org/3/library/argparse.html)
- [Subprocess](https://docs.python.org/3/library/subprocess.html)
- [Pandas](https://pandas.pydata.org/)
- [MDAnalysis](https://www.mdanalysis.org/) 
- [mpl_toolkits.axes_grid1](https://matplotlib.org/stable/tutorials/toolkits/axes_grid.html)
- [Numpy](https://numpy.org)
- [Matplotlib](https://matplotlib.org)
-[Supepdex]*

To be able to use these libraries, it is recommended to work with anaconda environment.

In case the user wishes to see trajectories, the use of the [VMD](https://www.ks.uiuc.edu/Research/vmd/) program is recommended.


If you are working in an anaconda environment
```
conda install module
```

or, if you have pip installed:

```
conda install pip
```
```
pip install module
```


### Required files :computer: 📋


<!-- Usage -->
## Usage ⚙️
In order to run this program, the following command has to be used:
```
python supepmem_analysis.py
         -tpr SYSTEM_STRUCTURE.tpr
         -xtc TRAJECTORY.xtc
         -f   $PATH/TO/FILES
         -o   $PATH/TO/OUTCOME
         -dt  SIMULATION_TIMESTEP
         -it  INITIAL_TIME_SIMULATION
         -lt  LAST_TIME_SIMULATION
         -st  SKIP_TIME_BETWEEN_FRAMES
         -ait INITIAL_TIME_AVERAGES
         -alt LAST_TIME_AVERAGES
         -ast SKIP_TIME_BETWEEN_FRAMES_AVERAGING
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
Project coordinator: Ángel Piñeiro, M.Bastos and Rebeca García-Fandino

- Main program (Python program): Fabián Suarez-Leston
- Collaborators: G.F Tolufashe, A.Muñoz, U.Veleiro, M.Calvelo
- Creation of the SuPepMem website: C.Porto
-GitHub Designer: Daniel Conde Torres and Álejandro Seco

The joint work tasks will be carried out (to a greater extent) by those members who are more advanced in their corresponding tasks.

<!-- FAQs -->
## FAQs

### What is that paralel file? Wasn't the program a serie algorithm?

Paralel directory is a program that uses mpi, so you have a paralelize version of the program in this file.


<!-- CONTRIBUTING -->
## Contributing 🖇️
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.


