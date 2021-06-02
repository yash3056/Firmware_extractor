# Requirements
- protobuf
- LZMA
- 7z
- lz4
## Linux
```bash
apt install unace unrar zip unzip p7zip-full p7zip-rar sharutils rar uudeview mpack arj cabextract rename
apt install liblzma-dev python-pip brotli lz4
pip install backports.lzma protobuf pycrypto
```
## Arch
```bash
pacman -S unace unrar zip unzip p7zip sharutils uudeview arj cabextract
pacman -S python python-pip brotli lz4
pip install backports.lzma protobuf pycrypto
sudo pip3 install --upgrade protobuf
```
### For "rename" and "mpack" you need to manually clone and install the packages
```bash
for package in mpack rename; do
    git clone https://aur.archlinux.org/"${package}"
    cd "${package}" || continue
    makepkg -si --skippgpcheck
    cd - || break
    rm -rf "${package}"
done
```
## Mac
```bash
brew install protobuf liblzma-dev brotli lz4
pip install backports.lzma protobuf pycrypto
```
Also install [mono](https://www.mono-project.com/docs/getting-started/install/mac/)  

### Windows
Install cygwin, and select

```Latest python and pip packages, arj, brotli, cabextract, dos2unix, lz4, p7zip, renameutils, sharutils, unace, unzip and zip```

If you get syntax errors run dos2unix on extractor.sh

# How to use
## Download
```
git clone --recurse-submodules https://github.com/yashlearnpython/Firmware_extractor.git
```

## Extract images from firmware URL
Example: Extracting images from OnePlus 8 Hydrogen OS ob4:
```
cd Firmware_extractor
wget https://td.brainded.workers.dev/0:/OnePlus8Hydrogen_15.Y.20_OTA_0200_all_2105072228_21bc.zip -O firmware.zip
./extractor.sh firmware.zip
```
output will be on "Firmware_extractor/out"
