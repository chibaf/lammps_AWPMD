# lammps_AWPMD
AWPMD of lammps

# UO2 in 1000K

python3 fcc111.py > data.fcc111

mpirun -np 12 /DATA/lammps20230802/build/lmp < in.1000
