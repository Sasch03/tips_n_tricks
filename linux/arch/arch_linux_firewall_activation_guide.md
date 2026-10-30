# Activating the Firewall<br>
Install the `firewalld` package:

```
sudo pacman -S firewalld
```

Enable and start the firewalld.service:

```
sudo systemctl enable firewalld.service
sudo systemctl start firewalld.service
```

To verify whether it was enabled and started correctly, you may run: 

```
sudo systemctl status firewalld.service
```

For further documentation see the [firewalld](https://wiki.archlinux.org/title/Firewalld) page in the Arch Wiki.