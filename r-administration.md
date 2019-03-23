# R Update.

## Updating default R version to newer release, following step need to be done. 


- Notify downtime in MS Team, need to mention about the R update as well.
- Make a note of all servers default R version --> ``` ll /usr/bin/R ```
- Need to restore the default versions after R update. 

1. Check the active sessions.
1. Notify in MS Team that the downtime has started.
1. Suspend all the active sessions --> ``` rstudio-server suspend-all ```
1. Stop RStudio  --> ``` rstudio-server stop ```
1. Update R with --> ``` yum install --enablerepo="rhel-7-server-optional-rpms" R ```
1. Finally restart RStudio server --> ``` rstudio-server restart ```
1. Check the new R version  with --> ``` R ```


- After update make all server default R versions as previous.
- Open RStudio server and check new version is there or not.

# Compiling Vanilla R with OpenBLAS

## For compiling VanillaR with openBLAS, following steps are done.

1. Go to the following link https://sourceforge.net/projects/openblas/files/v0.3.3/OpenBLAS%200.3.3%20version.tar.gz 
1. Download the file and extract the file in /mnt (For ease of use, we are keeping it on /mnt)
1. Create a directory in /opt/OpenBLAS
1. Go to that extracted file and export the following.
- export OPENBLAS_NUM_THREADS=7
- export GOTO_NUM_THREADS=7
- export OMP_NUM_THREADS=7
1. sudo make
1. sudo make PREFIX=/opt/OpenBLAS install
1. Confirm that all files came in /opt/OpenBLAS
1. Next step is to rename libRblas.so for that,Go to /opt/vanillaR/R-3.4.3/lib64/R/lib and rename libRblas.so to libRblas.so_back
1. For renaming use mv libRblas.so libRblas.so_back command
1. Now we need to softlink, for that do, ln -s /opt/OpenBLAS/lib/libopenblas.so /opt/R-3.4.3/lib64/R/lib/libRblas.so 
1. Confirm whether the OpenBLAS is linked by benchmark test.
