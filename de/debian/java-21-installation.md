## Sie möchten Java 21 auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

Java 21 installieren
``` bash
wget https://download.oracle.com/java/21/latest/jdk-21_linux-x64_bin.deb
```

``` bash
sudo dpkg -i jdk-21_linux-x64_bin.deb
```

Überprüfung der Java-Version
``` bash
java -version
```

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.