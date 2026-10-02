# wine-macports
## Requirements
* [MacPorts](https://www.macports.org/install.php)
* Xcode (macOS SDK)

## Setup
### 1. Setup repository
```
# force x86_64 build
echo "build_arch x86_64" | sudo tee -a /opt/local/etc/macports/macports.conf

# clone repository
sudo git clone --recursive https://github.com/fitudao3788/wine-macports /opt/wine-macports

# generate port index
sudo portindex /opt/wine-macports
```

### 2. Edit repository sources
Edit `/opt/local/etc/macports/sources.conf` and add the following line above the default `rsync://` entry
```
file:///opt/wine-macports [nosync]
rsync://rsync.macports.org/macports/release/tarballs/ports.tar.gz [default]
```

### 3. Sync repository
```
sudo port sync
```

## Credit
* Original repository: [Gcenx/macports-wine](https://github.com/Gcenx/macports-wine)
