# p53
Simulation data and python scripts for the manuscript on "Markov State Modeling analysis captures changes in the temperature sensitive N-terminal and β-turn regions of the p53 DNA binding domain"

 

Extract the MD_inputs.zip and MSM_python_notebooks.zip

    unzip MD_inputs.zip
    unzip MSM_python_notebooks.zip

# MD_inputs
The folder structure for the input files to be given for performing heating, equilibration and production run for the apo-p53 and DNA-bound p53 systems.
```
├── MD_inputs
|   ├── LowTemp-Dataset-I
│   |   ├── apo-p53.prmtop
│   |   ├── apo-p53.minrst
│   |   ├── heat_solv_300K.in
│   |   ├── heat_all_300K.in
│   |   ├── equi_300K.in
│   |   ├── prod_300K.in
```
Heating the solvent to 300 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_solv_300K.in -o heat_solv_300K.out -r heat_solv_300K.rst -p apo-p53.prmtop -c apo-p53.minrst -ref apo-p53.minrst -x heat_solv_300K.crd -v heat_solv_300K.vel -inf heat_solv_300K.info
    
Heating the system to 300K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_all_300K.in -o heat_all_300K.out -r heat_all_300K.rst -p apo-p53.prmtop -c heat_solv_300K.rst -ref heat_solv_300K.rst -x heat_all_300K.crd -v heat_all_300K.vel -inf heat_all_300K.info
    
Equilibrating the system at 300K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i equi_300K.in -o equi_300K.out -r equi_300K.rst -p apo-p53.prmtop -c heat_all_300K.rst -ref heat_all_300K.rst -x equi_300K.crd -v equi_300K.vel -inf equi_300K.info
    
Production run of 1 microseconds at 300 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system
    
    mpirun -np num_procs pmemd.MPI -O -i prod_300K.in -o prod_300K.out -r prod_300K.rst -p apo-p53.prmtop -c equi_300K.rst -ref equi_300K.rst -x prod_300K.crd -v prod_300K.vel -inf prod_300K.info
    

```
├── MD_inputs
|   ├── HighTemp-Dataset-I
│   |   ├── apo-p53.prmtop
│   |   ├── apo-p53.minrst
│   |   ├── heat_solv_310K.in
│   |   ├── heat_all_310K.in
│   |   ├── equi_310K.in
│   |   ├── prod_310K.in
```
Heating the solvent to 310 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_solv_310K.in -o heat_solv_310K.out -r heat_solv_310K.rst -p apo-p53.prmtop -c apo-p53.minrst -ref apo-p53.minrst -x heat_solv_310K.crd -v heat_solv_310K.vel -inf heat_solv_310K.info
    
Heating the system to 310K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_all_310K.in -o heat_all_310K.out -r heat_all_310K.rst -p apo-p53.prmtop -c heat_solv_310K.rst -ref heat_solv_310K.rst -x heat_all_310K.crd -v heat_all_310K.vel -inf heat_all_310K.info
    
Equilibrating the system at 310K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system

    mpirun -np num_procs pmemd.MPI -O -i equi_310K.in -o equi_310K.out -r equi_310K.rst -p apo-p53.prmtop -c heat_all_310K.rst -ref heat_all_310K.rst -x equi_310K.crd -v equi_310K.vel -inf equi_310K.info
    
Production run of 1 microseconds at 310 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the apo-p53 system
    
    mpirun -np num_procs pmemd.MPI -O -i prod_310K.in -o prod_310K.out -r prod_310K.rst -p apo-p53.prmtop -c equi_310K.rst -ref equi_310K.rst -x prod_310K.crd -v prod_310K.vel -inf prod_310K.info
    
```
├── MD_inputs
|   ├── LowTemp-Dataset-II
│   |   ├── DNA-bound-p53.prmtop
│   |   ├── DNA-bound-p53.minrst
│   |   ├── heat_solv_300K.in
│   |   ├── heat_all_300K.in
│   |   ├── equi_300K.in
│   |   ├── prod_300K.in
```
Heating the solvent to 300 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_solv_300K.in -o heat_solv_300K.out -r heat_solv_300K.rst -p DNA-bound-p53.prmtop -c DNA-bound-p53.minrst -ref DNA-bound-p53.minrst -x heat_solv_300K.crd -v heat_solv_300K.vel -inf heat_solv_300K.info
    
Heating the system to 300K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_all_300K.in -o heat_all_300K.out -r heat_all_300K.rst -p DNA-bound-p53.prmtop -c heat_solv_300K.rst -ref heat_solv_300K.rst -x heat_all_300K.crd -v heat_all_300K.vel -inf heat_all_300K.info
    
Equilibrating the system at 300K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i equi_300K.in -o equi_300K.out -r equi_300K.rst -p DNA-bound-p53.prmtop -c heat_all_300K.rst -ref heat_all_300K.rst -x equi_300K.crd -v equi_300K.vel -inf equi_300K.info
    
Production run of 1 microseconds at 300 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system
    
    mpirun -np num_procs pmemd.MPI -O -i prod_300K.in -o prod_300K.out -r prod_300K.rst -p DNA-bound-p53.prmtop -c equi_300K.rst -ref equi_300K.rst -x prod_300K.crd -v prod_300K.vel -inf prod_300K.info

```
├── MD_inputs
|   ├── HighTemp-Dataset-II
│   |   ├── DNA-bound-p53.prmtop
│   |   ├── DNA-bound-p53.minrst
│   |   ├── heat_solv_310K.in
│   |   ├── heat_all_310K.in
│   |   ├── equi_310K.in
│   |   ├── prod_310K.in

```
Heating the solvent to 310 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_solv_310K.in -o heat_solv_310K.out -r heat_solv_310K.rst -p DNA-bound-p53.prmtop -c DNA-bound-p53.minrst -ref apo-p53.minrst -x heat_solv_310K.crd -v heat_solv_310K.vel -inf heat_solv_310K.info
    
Heating the system to 310K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i heat_all_310K.in -o heat_all_310K.out -r heat_all_310K.rst -p DNA-bound-p53.prmtop -c heat_solv_310K.rst -ref heat_solv_310K.rst -x heat_all_310K.crd -v heat_all_310K.vel -inf heat_all_310K.info
    
Equilibrating the system at 310K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system

    mpirun -np num_procs pmemd.MPI -O -i equi_310K.in -o equi_310K.out -r equi_310K.rst -p DNA-bound-p53.prmtop -c heat_all_310K.rst -ref heat_all_310K.rst -x equi_310K.crd -v equi_310K.vel -inf equi_310K.info
    
Production run of 1 microseconds at 310 K using pmemd.MPI from AMBER20 and with _num_procs_ number of processors for the DNA-bound p53 system
    
    mpirun -np num_procs pmemd.MPI -O -i prod_310K.in -o prod_310K.out -r prod_310K.rst -p DNA-bound-p53.prmtop -c equi_310K.rst -ref equi_310K.rst -x prod_310K.crd -v prod_310K.vel -inf prod_310K.info
    
After completing the simulations, extract only the p53 co-ordinates from the trajectories and perform the MSM-analysis using the scripts given below
# MSM_python_notebooks

```
├── MSM_python_notebooks
    ├── Dataset-I-Feature-Selection.ipynb
    ├── Dataset-II-Feature-Selection.ipynb
    ├── LowTemp-Dataset-I-MSM.ipynb
    ├── HighTemp-Dataset-I-MSM.ipynb
    ├── LowTemp-Dataset-II-MSM.ipynb
    ├── HighTemp-Dataset-II-MSM.ipynb
    ├── WT_ZAFF.pdb
```

## Dataset-I-Feature-Selection.ipynb
Python script for selection of features (16 Cα-Cα distances) for the apo-p53 simulations at 300 K and 310 K (Dataset-I).

## Dataset-II-Feature-Selection.ipynb
Python script for selection of features (32 Cα-Cα distances) for the DNA-bound p53 simulations at 300 K and 310 K (Dataset-II).

## LowTemp-Dataset-I-MSM.ipynb
Python script for MSM calculations performed on apo-p53 simulations at 300 K (LowTemp-Dataset-I) using the 16 Cα-Cα distances as feature set.

## HighTemp-Dataset-I-MSM.ipynb
Python script for MSM calculations performed on apo-p53 simulations at 310 K (HighTemp-Dataset-I) using the 16 Cα-Cα distances as feature set.

## LowTemp-Dataset-II-MSM.ipynb
Python script for MSM calculations performed on DNA-bound p53 simulations at 300 K (LowTemp-Dataset-II) using the 32 Cα-Cα distances as feature set.

## HighTemp-Dataset-II-MSM.ipynb
Python script for MSM calculations performed on DNA-bound p53 simulations at 310 K (HighTemp-Dataset-II) using the 32 Cα-Cα distances as feature set.

## WT_ZAFF.pdb 
Topology file used for MSM calculations

