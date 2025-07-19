## Sie möchten einen TeamSpeak³ Server auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

TeamSpeak-Verzeichnis erstellen
``` bash
mkdir /home/teamspeak
```

In das Verzeichnis wechseln
``` bash
cd /home/teamspeak
```

TeamSpeak³-Server installieren
``` bash
apt install bzip2 -y
```

``` bash
wget https://files.teamspeak-services.com/releases/server/3.13.7/teamspeak3-server_linux_amd64-3.13.7.tar.bz2
tar xfvj teamspeak3-server_linux_amd64-3.13.7.tar.bz2
```

``` bash
rm teamspeak3-server_linux_amd64-3.13.7.tar.bz2
```

``` bash
cd teamspeak3-server_linux_amd64
```

TeamSpeak³-Server starten
``` bash
touch .ts3server_license_accepted
```

``` bash
./ts3server_startscript.sh
```

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.