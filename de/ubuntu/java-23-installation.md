## Sie möchten Java 23 auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

Java 23 installieren
``` bash
wget https://download.oracle.com/java/23/archive/jdk-23.0.2_linux-x64_bin.deb
```

``` bash
sudo dpkg -i jdk-23.0.2_linux-x64_bin.deb
```

Überprüfung der Java-Version
``` bash
java -version
```

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.