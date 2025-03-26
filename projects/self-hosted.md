# Self-Hosted Services in My Home Network

## Hardware & Software
A Dell Wyse 3040 with the following specifications:
- **CPU:** Intel Atom x5-Z8350
- **RAM:** 2 GB
- **Storage:** 16 GB Flash

**OS:** Debian 12 (minimal, no GUI)

### Debian 12

- Advanced options ... enter expert graphical install
- Force grub-efi installation to the removable media path (enter in expert mode)
- Leave the root password empty; the first user receives sudo rights.
- No disk encryption
- Additional software: only 'SSH server' and 'standard system utilities'

#### Boot issue

    - Follow the instructions from [this guide](https://binarypatrick.dev/posts/linux-on-dell-wyse-3040/#boot-issues) to resolve boot issues.

#### Set up static IP
ip link show
sudo nano /etc/network/interfaces
Edit the file
sudo systemctl restart networking

#### Set Up UFW
Set up ufw firewall with only ssh enabled

#### Docker and Docker Compose

https://docs.docker.com/engine/install/debian/

Run docker as non-root: add user to docker group
(https://docs.docker.com/engine/install/linux-postinstall/)
```
sudo groupadd docker
sudo usermod -aG docker $USER
```

#### AdGuard

https://www.frasermclean.com/p/2024/04/secure-your-entire-home-network-with-adguard-home/

#### Homepage

sudo ufw allow 3000

... set up docker / docker proxy / ufw

5. **Additional Configuration:**
    - Configure static IP if necessary.
    - Set up any additional software or services as needed.

## Planned

- Home Assistant OS
- AdGuard
    - \+ Snort ?
- Firewall configuration
- VLAN ?
- Backup NAS ?
- ESPhome ?
    - Weather station
- DuckDNS (dynamic dns) ?