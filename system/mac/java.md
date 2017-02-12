# JAVA

## unlimited strength JCE for Java 8 in OS X?

[osx - How to install unlimited strength JCE for Java 8 in OS X? - Stack Overflow](http://stackoverflow.com/questions/37741142/how-to-install-unlimited-strength-jce-for-java-8-in-os-x)

```
if you are macbook user, put the jars extracted from (http://www.oracle.com/technetwork/java/javase/downloads/jce8-download-2133166.html) jce_policy-8.zip (if your java version is 8.*) to following directory

/Library/Java/JavaVirtualMachines/< jdk_version_of_your_pc >/Contents/Home/jre/lib/security
```

```
/Library/Java/JavaVirtualMachines/jdk1.8.0_121.jdk/Contents/Home/jre/lib/security
```

