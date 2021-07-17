# spotify-install-headless-ubuntu
Install spotify client on headless ubuntu server

This tutorial assumes you have installed Ubuntu Server, and are logged in as root.

1- Add spotify repo to your lists

```
curl -sS https://download.spotify.com/debian/pubkey_0D811D58.gpg | sudo apt-key add -
echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
sudo apt-get update && sudo apt-get install spotify-client
```

2- Install dependencies

```
sudo apt-get install xvfb at-spi2-core pavucontrol alsa-utils alsa-oss pulseaudio jackd2 alsa-utils dbus-x11 libcanberra-gtk-module libcanberra-gtk3-module
```

3- Edit /etc/asound.conf & /root/.asoundrc

```
pcm.card0 {
    type hw
    card 0
}
ctl.card0 {
    type hw
    card 0
}
```
