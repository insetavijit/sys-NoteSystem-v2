
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y sudo vim curl which zsh htop wget fzf bat jq ripgrep tmux unzip tree ncdu git
```


```bash
sudo apt update
sudo apt install -y zsh vim curl ca-certificates git docker-ce docker-compose containerd.io

```
# Detailed conversation summary

Below is a thorough, step-by-step summary of everything we covered, what you ran, the results, and the final state — so you have a single reference to pick up from.

---

## 1) Context & goal

- You’re using **WSL (Debian)** on Windows and working as user **avijit**.
    
- Main tasks: fix WSL startup behavior (start in home), pick a fast Debian mirror, test real download speed by installing packages, install shells/tools (zsh / Oh My Zsh), install Docker & [[DDEV]].
    

---

## 2) WSL default user & starting directory

- Diagnosis:
    
    - WSL can start in `C:\Windows\System32` (mapped to `/mnt/c/Windows/System32`) if launched from that Windows CWD or if the distro starts as `root`.
        
    - Your WSL distro is named **`ddev`**, not `Debian`, so distro-specific commands differ.
        
- Recommendations given:
    
    - Set default user in `/etc/wsl.conf`:
        
        ```ini
        [user]
        default=avijit
        ```
        
    - Change Windows Terminal profile `"startingDirectory"` to `\\wsl$\ddev\home\avijit`.
        
    - As fallback, add `cd ~` to `~/.bashrc` so shell always lands in your home.
        
- You implemented fixes/checked behavior; confirmed problem and fixes were discussed.
    

---

## 3) Mirror testing (latency + download)

- Ping tests you ran (results captured):
    
    - `mirrors.iitd.ac.in` → avg **~48 ms**
        
    - `mirror.nitc.ac.in` → avg **~79 ms**
        
    - `deb.debian.org` (fastly DNS) → avg **~3.6 ms**
        
- `curl` download tests:
    
    - IIT Delhi: `curl` finished → `IIT Delhi: 0.286375s`
        
    - NIT Calicut: `NIT Calicut: 0.392293s`
        
    - `deb.debian.org` `curl` hung for you (you aborted with Ctrl+C)
        
- You ran `netselect-apt` and it reported the fastest 10 mirrors (excerpt):
    
    ```
    http://ftp.es.debian.org/debian/
    http://mirror.coganng.com/debian/
    http://mirror.xeonbd.com/debian/
    http://mirrors.iitd.ac.in/debian/
    http://mirror.sg.gs/debian/
    http://ftp.cn.debian.org/debian/
    http://ftp.debianclub.org/debian/
    http://mirror.unair.ac.id/debian/
    ```
    
    - `netselect-apt` chose **`http://ftp.es.debian.org/debian/`** as the fastest valid HTTP mirror and wrote a `sources.list`.
        

---

## 4) `/etc/apt/sources.list`

- I suggested and provided a recommended `sources.list` using the fast mirror plus security and updates:
    

```text
# Primary Debian mirror (fastest found)
deb http://ftp.es.debian.org/debian/ stable main contrib non-free
deb-src http://ftp.es.debian.org/debian/ stable main contrib non-free

# Security updates
deb http://security.debian.org/debian-security stable-security main contrib non-free
deb-src http://security.debian.org/debian-security stable-security main contrib non-free

# Stable updates
deb http://ftp.es.debian.org/debian/ stable-updates main contrib non-free
deb-src http://ftp.es.debian.org/debian/ stable-updates main contrib non-free
```

- You ran installs that used `ftp.es.debian.org`, so the new sources effectively got applied.
    

---

## 5) Real-world package tests (download + install)

- `htop`:
    
    - First install (downloaded from `mirrors.iitd.ac.in`): fetched 171 KB; `real 0m5.415s` (initial download + install).
        
    - Subsequent installs were cached and very fast (`~0.8s`).
        
- `fastfetch` (selected because `neofetch` not in your repo):
    
    - `sudo apt install -y fastfetch`
        
    - Downloaded `632 kB` total (libyyjson0 + fastfetch), fetched **632 kB in ~1s** → observed **~792 kB/s**.
        
    - Install completed successfully.
        
- Conclusion: mirror(s) are performing well in practice; `ftp.es.debian.org` used and returned good throughput.
    

---

## 6) Tools & packages discussion / corrections

- Clarified that `pacman` commands you posted are for **Arch**, not Debian — provided `apt` equivalents.
    
- Noted `reflector` and `pacman-contrib` are Arch-specific (no direct Debian equivalents).
    
- Suggested `netselect-apt`, `apt-spy` (less maintained), and manual `curl/wget` tests for download speed.
    
- Advised enabling `stable-backports` if you want newer packages.
    

---

## 7) Shell setup (zsh & Oh My Zsh)

- Commands suggested to install `zsh`:
    
    ```bash
    sudo apt update
    sudo apt install -y zsh
    chsh -s $(which zsh)
    ```
    
- Oh My Zsh install (official script):
    
    ```bash
    sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
    ```
    
    — recommended to inspect script before running if security-conscious.
    
- Plugins: instructions given for `zsh-autosuggestions` and `zsh-syntax-highlighting`:
    
    ```bash
    git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
    git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
    # then add to plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
    ```
    

---

## 8) Docker & DDEV

- You tried `sudo usermod -aG docker $USER` (added user to docker group).
    
- Docker:
    
    - We discussed the recommended Docker CE install via Docker’s official repo (keyring, apt source, install `docker-ce`, `containerd.io`).
        
- DDEV:
    
    - You preferred an updated community method rather than old piped commands.
        
    - We reviewed three modern methods:
        
        - Homebrew (`brew install ddev/ddev/ddev`) — easy if you use Homebrew.
            
        - APT repo (official `pkg.ddev.com` with keyring) — recommended for Debian/WSL.
            
        - Manual binary from GitHub releases.
            
    - You wanted the `install.sh` approach — you downloaded:
        
        ```bash
        curl -LO https://raw.githubusercontent.com/drud/ddev/main/scripts/install_ddev.sh
        chmod +x install_ddev.sh
        ```
        
    - The script must be run as non-root. You ran `./install_ddev.sh` (without sudo) and reported **installation completed successfully**.
        
    - Verified `ddev` availability — if `ddev` not found, we checked `$PATH` and suggested adding `/usr/local/bin` to `~/.zshrc` if needed.
        
    - Final state: **DDEV installed and ready**.
        

---

## 9) Final status — what is in place now

- WSL distro named **`ddev`**; you know how to set default user in `/etc/wsl.conf` and how to set Windows Terminal start dir.
    
- Fast mirror chosen by `netselect-apt`: **`ftp.es.debian.org`**; sources list updated to use it + security updates.
    
- Successful package installs:
    
    - `htop` installed (cached later).
        
    - `fastfetch` installed; measured good real throughput (~792 kB/s).
        
- `zsh` / Oh My Zsh steps provided; plugin install instructions provided.
    
- Docker prerequisites discussed; user added to `docker` group.
    
- **DDEV installed via official `install_ddev.sh` script** (ran without sudo successfully).
    

---

## 10) Actionable next steps you can pick from

- I can produce a ready-to-save file for `/etc/apt/sources.list` (I previously provided it; I can write it to a file and give download instructions).
    
- Verify Docker is running and `docker --version` and run `ddev --version` to confirm.
    
- Walk through adding `/usr/local/bin` to your PATH (if `ddev` is not found).
    
- Set Windows Terminal `startingDirectory` for your `ddev` profile.
    
- Configure Oh My Zsh themes / enable the plugins you want and tweak `~/.zshrc`.
    
- Run a larger package install (e.g., `git`) to stress-test the mirror and network.
    

---

If you want, I’ll now:  
A) generate the final `/etc/apt/sources.list` file and show exact commands to write it, **or**  
B) verify `ddev --version` and Docker status with the commands for you to run and help interpret results.

Which one should I do next?