## Do You Want to Install Java 23 on Your Server?


Update the Server Package List
``` bash
apt update && apt upgrade -y
```

Install Java 23
``` bash
wget https://download.oracle.com/java/23/archive/jdk-23.0.2_linux-x64_bin.deb
```

``` bash
sudo dpkg -i jdk-23.0.2_linux-x64_bin.deb
```

Verify the Java Installation
``` bash
java -version
```

© dataflair – Republishing this guide on external websites is not permitted.