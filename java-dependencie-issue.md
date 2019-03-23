# rJava Package loading Issue 

- If loading library(rJava) giving error like this. 
	``` .library(rJava)
	Error: package or namespace load failed for .rJava.:
	 .onLoad failed in loadNamespace() for 'rJava', details:
	  call: dyn.load(file, DLLpath = DLLpath, ...)
	  error: unable to load shared object '/opt/nfs01/r-libs/3.4.1/rJava/libs/rJava.so':
	  libjvm.so: cannot open shared object file: No such file or directory
	.
	``` 
- Then the issue is with Java dependencies in Linux side.
- Most common solution is to create a system link of java file .libjvm.so. to R  under .lib. directory.
 
- Solution 
	```  ln -s /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.141-2.b16.el7_4.x86_64/jre/lib/amd64/server/libjvm.so  /opt/microsoft/ropen/3.4.3/l            ib64/R/lib/libjvm.so ```
