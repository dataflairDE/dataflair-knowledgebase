## Do You Want to Install Java 8 on Your Server?


Update the Server Package List
``` bash
apt update && apt upgrade -y
```

Install Java 8
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

Verify the Java Installation
``` bash
java -version
```

© dataflair – Republishing this guide on external websites is not permitted.