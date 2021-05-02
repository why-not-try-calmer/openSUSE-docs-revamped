### What is pipewire?

### Installing
Install the packages:
```
sudo zypper in pipewire-alsa pipewire-pulseaudio pipewire-tools
```
Then enable the pipwire audio socket: 
```
systemctl --user enable --now pipewire.{service,socket} pipewire-pulse.{service,socket}
```
Start the service:
```
systemctl --user start --now pipewire-media-session.service
```
Finally reboot your system:
```
systemctl reboot
```

### For KDE Plasma users
After rebooting, enable pipewire service making pipewire available to Plasma:
```
systemctl --user enable --now pipewire-media-session.service
```
