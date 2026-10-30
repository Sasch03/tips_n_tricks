# Activating multilib Repository

The multilib-library contains 32bit-packages. Follow these instructions to 

<br>
To activate multilib a configuration file must be edited:

```
sudo nano /etc/pacman.conf
```

<br>
Find the multilib section of the file. It should look like this: 

```
#[multilib]
#Include = /etc/pacman.d/mirrorlist
```

<br>
Comment it in to make it look like this: 

```
[multilib]
Include = /etc/pacman.d/mirrorlist
```

<br>
Exit and save by pressing these key combinations in the following order: 

```
CTRL+X
CTRL+Y
ENTER
```

<br>
To update your packages after this, run: 

```
sudo pacman -Syyu
```

You have activated the multilib library and can now install 32bit-packages. 