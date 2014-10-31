parsec
======

PARSEC Benchmark at http://parsec.cs.princeton.edu/

This is the benchmakr used by CMU for the cache partition experiments

======
wiki
http://wiki.cs.princeton.edu/index.php/PARSEC
======
How to run the benchmark?
Refer to http://parsec.cs.princeton.edu/parsec3-doc.htm

[user@host ~]$ source env.sh

[user@host ~]$ parsecmgmt -a build -p streamcluster
  ...
[PARSEC] Copying source code of package parsec.streamcluster.
[PARSEC] Running 'env version=pthreads /usr/bin/make':
  ...

[user@host ~]$ parsecmgmt -a run -p streamcluster
  ...
[PARSEC] [---------- Beginning of output ----------]
PARSEC Benchmark Suite Version 3.0
read 10 points

real	0m0.016s
user	0m0.002s
sys	0m0.001s
[PARSEC] [----------    End of output    ----------]
  ...

[user@host ~]$ parsecmgmt -a fulluninstall -p streamcluster
[PARSEC] Removing all installed files:
[PARSEC] parsec.streamcluster - [Removing installation directory]

=====
How to customize the input for the streamcluster benchmark?
Read the streamcluster's main function, it has the usage description. 
You can generate the random point for streamcluster to cluster.

vim pkgs/kernels/streamcluster/src/streamcluster.cpp

'parsecmgmt' actually run the following command. The input parameter is described in streamcluster.cpp 
'time /home/pennpanda/github/parsec/parsec-3.0/pkgs/kernels/streamcluster/inst/i686-linux.gcc/bin/streamcluster 2 5 1 10 10 5 none output.txt 1':
