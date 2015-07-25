SUMMARY
-------
The interactive.cc is the sample application to perform impersonated and non-impersonated operations using C-APIs against MapR-DB interactively.

INSTRUCTIONS
------------
In order to compile and run the example binary, follow these instructions:  

* Ensure $JAVA_HOME is exported and set correctly. Ex: /usr/lib/jvm/java-1.7.0-*/ OR  
   Ensure $JRE_LIB points to the directory containing the jvm library.
* Ensure $MAPR_HOME is exported and set correctly. Default: /opt/mapr  
* Run 'make'. If compilation succeeds, 'interactive' binary will be created.  
* On non-Windows machine,  
      export LD_LIBRARY_PATH pointing to MAPR_LIB and JRE_LIB, typically '/opt/mapr/lib' and '$JAVA_HOME/jre/lib/amd64/server' respectively.  
      export MAPR_IMPERSONATION_ENABLED=true if you want to run impersonation operations.  
      Without this environment variable, all operations will be performed using process user's credentials.  
   On windows machine, append the following directories to PATH:  
   * directory including MapRClient.dll($MAPR_HOME/lib)  
   * directory including jvm.dll($JAVA_HOME/bin/server).  
* Run './interactive'.  
