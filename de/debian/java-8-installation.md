## Sie möchten Java 8 auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

Java 8 installieren
``` bash
mkdir -p /etc/apt/keyrings
```

``` bash
wget -O - https://packages.adoptium.net/artifactory/api/gpg/key/public | tee /etc/apt/keyrings/adoptium.asc
```

``` bash
echo "deb [signed-by=/etc/apt/keyrings/adoptium.asc] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print$2}' /etc/os-release) main" | tee /etc/apt/sources.list.d/adoptium.list
```

``` bash
apt update
```

``` bash
apt install temurin-8-jdk
```

Überprüfung der Java-Version
``` bash
java -version
```

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.