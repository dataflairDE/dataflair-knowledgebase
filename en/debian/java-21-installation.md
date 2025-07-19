## Do You Want to Install Java 21 on Your Server?


Update the Server Package List
``` bash
apt update && apt upgrade -y
```

Install Java 21
``` bash
wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb
```

``` bash
sudo dpkg -i jdk-21_linux-x64_bin.deb
```

Verify the Java Installation
``` bash
java -version
```

© dataflair – Republishing this guide on external websites is not permitted.