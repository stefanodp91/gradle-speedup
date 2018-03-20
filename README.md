# Decrease Gradle build time

## Assumptions

The following configurations vary depending on your hardware.

Successfully tested with MacBook Pro with TouchBar (15-inch, 2016) with the following configurations:

- CPU : 2,6 GHz Intel Core i7
- RAM : 16 GB 2133 MHz LPDDR3
- GPU : Intel HD Graphics 530 1536 MB
- SSD : APPLE SSD SM0512L 512 GB


## Don’t use dynamic dependency 

use 

```
compile 'com.android.support:appcompat-v7:27.0.2' 
```

instead of

```
compile 'com.android.support:appcompat-v7:27.+'
```


## gradle.properties

```
#Enable daemon
org.gradle.daemon=true

# Try and findout the best heap size for your project build.
org.gradle.jvmargs=-Xmx3096m -XX:MaxPermSize=512m -XX:+HeapDumpOnOutOfMemoryError -Dfile.encoding=UTF-8

# Modularise your project and enable parallel build
org.gradle.parallel=true

# Enable configure on demand.
org.gradle.configureondemand=true

# Not needed for speedup. It prevents Aapt2Exception
android.enableAapt2=false
```
