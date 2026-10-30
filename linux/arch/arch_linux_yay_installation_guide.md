# Installing `yay` for AUR-Access<br>
I usually install [yay](https://github.com/Jguer/yay) as a mean to access and install packages from the [AUR](https://aur.archlinux.org/).

The installation command from source as of the time of my last installation: 

```
sudo pacman -S --needed git base-devel && git clone https://aur.archlinux.org/yay.git && cd yay && makepkg -si
```

For further documentation see the referenced GitHub repository of `yay` above.