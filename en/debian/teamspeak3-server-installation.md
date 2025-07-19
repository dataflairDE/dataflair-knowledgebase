## Do You Want to Install a TeamSpeak³ Server on Your Server?


Update the Server Package List
``` bash
apt update && apt upgrade -y
```

Create a Directory for TeamSpeak
``` bash
mkdir /home/teamspeak
```

Change into the Directory
``` bash
cd /home/teamspeak
```

Install the TeamSpeak³ Server
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

Start the TeamSpeak³ Server
``` bash
touch .ts3server_license_accepted
```

``` bash
./ts3server_startscript.sh
```

© dataflair – Republishing this guide on external websites is not permitted.