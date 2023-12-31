# lammps_AWPMD
AWPMD of lammps

# installation of lammps

## clang-format

sudo apt install clang-format

## fftw3

tar -xf fftw-3.3.10.tar.gz 

 1933  cd fftw-3.3.10

  1935  ./configure --enable-threads --enable-openmp
  
 1936  make -j 24
 
 1937  make check
 
 1938  sudo make install

 ## lammps

git clone -b release https://github.com/lammps/lammps.git /DATA/lammps20230802

cd lammps20230802

mkdir build; cd build

cmake -D PKG_KSPACE=yes -D PKG_AQPMD=yes -D FFT_FFTW_THREADS=on  ../cmake

make -j24

# UO2 in 1000K

python3 fcc111.py > data.fcc111

mpirun -np 12 /DATA/lammps20230802/build/lmp < in.1000

UO2 at 1000K of a fcc 111 latice cut with a slant plane - YouTube

https://www.youtube.com/shorts/GqAvuTLb8YI
