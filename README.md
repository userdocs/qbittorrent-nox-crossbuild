# qbittorrent-nox crossbuilds

Multiarch crossbuilds to use with Debian based platforms.

Deb packages are created and published as releases.

[<img alt="Follow the white rabbit" width="100px" src="white-rabbit.png" />](https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/latest)

The crossbuilds are built as part of a chain of modular shared builds using current dependencies as a proof of concept.

```bash
zlib-ng > openssl > libtorrent > qt6 > qbittorrent-nox
zlib-ng > openssl > libtorrent > qt5 > qbittorrent-nox
```

Download them using `amd64` as the example arch.

```bash
wget https://github.com/userdocs/zlib-ng-crossbuild/releases/latest/download/debian-bullseye-zlib-ng-amd64.deb
wget https://github.com/userdocs/openssl-crossbuild/releases/latest/download/debian-bullseye-openssl-amd64.deb
wget https://github.com/userdocs/libtorrent-crossbuild/releases/latest/download/debian-bullseye-libtorrent-amd64.deb
wget https://github.com/userdocs/qt6-crossbuild/releases/latest/download/debian-bullseye-qt6-amd64.deb
wget https://github.com/userdocs/qbittorrent-nox-crossbuild/releases/latest/download/debian-bullseye-qbittorrent-nox-amd64.deb
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
sudo dpkg -i debian-bullseye-zlib-ng-amd64.deb
sudo dpkg -i debian-bullseye-openssl-amd64.deb
sudo dpkg -i debian-bullseye-libtorrent-amd64.deb
sudo dpkg -i debian-bullseye-qt6-amd64.deb
sudo dpkg -i debian-bullseye-qbittorrent-nox-amd64.deb
```

Add the binary location to your path:

```bash
export PATH="/opt/local/bin:$PATH"
```

Run the program:

```bash
qbittorrent-nox
```