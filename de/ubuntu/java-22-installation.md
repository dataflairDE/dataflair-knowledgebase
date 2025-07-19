## Sie möchten Java 22 auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

Java 22 installieren
``` bash
wget https://download.oracle.com/java/22/archive/jdk-22_linux-x64_bin.deb
```

``` bash
sudo dpkg -i jdk-22_linux-x64_bin.deb
```

Überprüfung der Java-Version
``` bash
java -version
```

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.