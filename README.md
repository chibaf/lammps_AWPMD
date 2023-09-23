# lammps_AWPMD
AWPMD of lammps

# installation of lammps

## fftw

tar -xf fftw-3.3.10.tar.gz 

 1933  cd fftw-3.3.10

  1935  ./configure --enable-threads --enable-openmp
  
 1936  make -j 24
 
 1937  make check
 
 1938  sudo make install

git clone -b release https://github.com/lammps/lammps.git /DATA/lammps20230802

cd lammps20230802

mkdir build; cd build

make -D PKG_KSPACE=yes -D PKG_AQPMD=yes -D FFT_FFTW_THREADS=on  ../cmake

# UO2 in 1000K

python3 fcc111.py > data.fcc111

mpirun -np 12 /DATA/lammps20230802/build/lmp < in.1000
