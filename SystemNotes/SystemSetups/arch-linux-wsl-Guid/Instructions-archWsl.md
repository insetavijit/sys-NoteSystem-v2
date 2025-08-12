## 1 . Download Wsl Setup form official Store 

 -  You can download official  `.msi`  [here](https://geo.mirror.pkgbuild.com/wsl/latest/)
	
	You will see something like this and you need to pick  `archlinux.wsl`

 ```
../
archlinux-2025.08.01.138229.wsl                     01-Aug-2025 10:06
archlinux-2025.08.01.138229.wsl.SHA256              01-Aug-2025 10:06
archlinux-2025.08.01.138229.wsl.bundle              01-Aug-2025 10:06> 

> archlinux.wsl                01-Aug-2025 10:06            139564808

archlinux.wsl.SHA256           01-Aug-2025 10:06                   80
archlinux.wsl.bundle           01-Aug-2025 10:06                 7332
```

After download move it to `C:\custom` This dir is responsible for all wsl related contents

---
## Install vis PowerShell

> “Create a new WSL distro named `xyz`, store it in `D:\WSL\Arch`, unpack it from the tarball at `D:\Downloads\ArchLinux.tar.gz`, and run it using WSL 2.”

```
wsl --import xyz C:\Custom\Arch C:\Custom\ArchLinux.wsl  --version 2
```

## **Command** `wsl --import`  
This tells Windows Subsystem for Linux to **import** a Linux distribution from a root filesystem tarball instead of installing from the Microsoft Store.
## **First argument (re-name distro ): `xyz`**
- This is the **name** you’re giving to the distro inside WSL.
- It’s **your label** — you can pick anything (no spaces, keep it simple).
- You’ll use this name to start the distro:

    ```powershell
    wsl -d xyz
    ```
## **Second argument:** `D:\WSL\Arch`
- This is the **install folder** where WSL will store the distro’s files.
- WSL keeps all system files, your Linux home, etc., in this folder.
- If you delete this folder, the distro is gone.
- You can put it on **any drive** (e.g., `C:\`, `D:\`, `E:\`).
## **Third argument:** `D:\Downloads\ArchLinux.tar.gz`
- This is the **path to the root filesystem tarball** you’re importing.
- Inside this tarball are all the Linux OS files for Arch.
- It’s usually downloaded from projects like **ArchWSL** or built yourself with `tar`.
## **Option:** `--version 2`
- This tells WSL to create the distro using **WSL 2** (faster, full Linux kernel, better compatibility).
- If you used `--version 1`, it would be WSL 1 (lighter, but less compatible).

---
# 4. Configure new [[Linux-user]] for customization

Got it! To create a new user named **avijit** with sudo access and set its password, run these commands:

```bash
sudo useradd -m -G wheel -s /bin/bash avijit
sudo passwd avijit
```

After setting the password, double-check sudo permission for the `wheel` group by running:

```bash
sudo EDITOR=vim visudo


sudo visudo
```

Make sure this line is **uncommented** (no `#`):

```bash
%wheel ALL=(ALL) ALL
```

```bash
su - avijit
sudo pacman -Syu
```

sudo nano /etc/wsl.conf


[user]
default=avijit



# 4. install [[Basic dev tools ]] as root


```bash

pacman -Syu sudo vim curl which reflector pacman-contrib zsh --noconfirm

```

```bash

sudo cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.backup && \

sudo reflector --country India --protocol https --sort rate --fastest 10 --connection-timeout 10 --download-timeout 10 --save /etc/pacman.d/mirrorlist
# OR TRY THis ..
sudo reflector --verbose --latest 10 --sort rate --save /etc/pacman.d/mirrorlist


```

#### Here’s a single command to install all those packages on Arch Linux:

```bash
sudo pacman -S --needed ca-certificates base-devel htop wget curl fzf bat exa jq ripgrep tmux neovim unzip tree ncdu git docker zsh docker-compose 

```

***Next Step >***   [[Neovim Setup with NvChad]] + [[ Oh My Zsh  ]] > ONLY AFTER PERSONALISATION

---

```bash

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" && \
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions && \
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting

```

zsh-syntax-highlighting zsh-autosuggestions

Run this in your terminal. After it finishes:
- Open `~/.zshrc` and add the plugins as I showed before.
- Then `source ~/.zshrc` or restart your terminal.

---
# 5. setup eves
[[DDEV]] →  upGrade . 

```bash
sudo systemctl start docker && \
sudo systemctl enable docker && \
docker run hello-world
```

```bash
curl -fsSL https://ddev.com/install.sh | bash
```


sudo usermod -aG docker avijit
