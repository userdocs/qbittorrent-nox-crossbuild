# qbittorrent-nox crossbuilds

Multiarch crossbuilds to use with Debian based platforms.

Deb packages are created and published as releases.

[<img alt="Follow the white rabbit" width="100px" src="black-rabbit.png" />](https://github.com/userdocs/qt6-crossbuild)
[<img alt="Follow the white rabbit" width="100px" src="white-rabbit.png" />](https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/latest)

The crossbuilds are built as part of a chain of modular shared builds using current dependencies as a proof of concept.

```bash
zlib-ng > openssl > libtorrent > qt6 > qbittorrent-nox
zlib-ng > openssl > libtorrent > qt5 > qbittorrent-nox
```

Qt6 builds:

Supported OS and arch : Debian Buster/Bullseye Ubuntu Bionic/Focal amd64 arm64 armhf

Download them using these commands:

```bash
wget "https://github.com/userdocs/zlib-ng-crossbuild/releases/latest/download/$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-zlib-ng-$(dpkg --print-architecture).deb"
wget "https://github.com/userdocs/openssl-crossbuild/releases/latest/download/$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-openssl-$(dpkg --print-architecture).deb"
wget "https://github.com/userdocs/libtorrent-crossbuild/releases/latest/download/$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-libtorrent-$(dpkg --print-architecture).deb"
wget "https://github.com/userdocs/qt6-crossbuild/releases/latest/download/$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-qt6-$(dpkg --print-architecture).deb"
wget "https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/latest/download/$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-qbittorrent-nox-$(dpkg --print-architecture).deb"
```

Qt 5 builds here as prereleases:

Debian Buster/Bullseye Ubuntu Bionic/Focal - [4.3.9](https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/tag/4.3.9)

Debian Stretch - [4.3.2](https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/tag/4.3.2)

Install a required system dependency.

```bash
sudo apt install libgeoip1
```

Install the packages.

```bash
sudo dpkg -i "$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-zlib-ng-$(dpkg --print-architecture).deb"
sudo dpkg -i "$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-openssl-$(dpkg --print-architecture).deb"
sudo dpkg -i "$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-libtorrent-$(dpkg --print-architecture).deb"
sudo dpkg -i "$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-qt6-$(dpkg --print-architecture).deb"
sudo dpkg -i "$(. /etc/os-release && printf '%s' "$ID")-$(. /etc/os-release && printf '%s' "$VERSION_CODENAME")-qbittorrent-nox-$(dpkg --print-architecture).deb"
```

Add the binary location to your path:

```bash
export PATH="/opt/local/bin:$PATH"
```

Update library paths

```bash
ldconfig
```

Run the program:

```bash
qbittorrent-nox
```