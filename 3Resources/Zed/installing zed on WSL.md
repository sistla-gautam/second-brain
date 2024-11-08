### Steps
- install zed using the normal linux command
```bash
curl -f https://zed.dev/install.sh | sh
```
found on the official website of [zed](https://zed.dev/download)
- download the libvulkan package
```bash
sudo apt-get install libvulkan-dev
```
- run the following updates
```bash
sudo add-apt-repository ppa:kisak/kisak-mesa
sudo apt update
sudo apt upgrade
```
- we can finally run zed using
```bash
WAYLAND_DISPLAY='' zed --foreground
```