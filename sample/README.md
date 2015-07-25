SUMMARY
-------
The 'sample.cc' is an example implementation to perform operations using C-APIs against MapR-DB.  

INSTRUCTIONS
------------
In order to compile and run the example binary, follow these instructions:  

* Ensure $JAVA_HOME is exported and set correctly. Ex: /usr/lib/jvm/java-1.7.0-*/ OR  
  Ensure $JRE_LIB points to the directory containing the jvm library.
* Ensure $MAPR_HOME is exported and set correctly. Default: /opt/mapr
* Run 'make'. If compilation succeeds, sample binary will be created.
* On non-Windows machine,  
  export LD_LIBRARY_PATH pointing to MAPR_LIB and JRE_LIB, typically '/opt/mapr/lib' and '$JAVA_HOME/jre/lib/amd64/server' respectively.  
   On windows machine, append the following directories to PATH:  
   * directory including MapRClient.dll($MAPR_HOME/lib)
   * directory including jvm.dll($JAVA_HOME/bin/server).
* Run './sample <table path> <CLDB IPs>'.  
   Defaults:  
    table path = /tmp/tempTable  
    CLDB IPs   = 127.0.0.1:7222  
